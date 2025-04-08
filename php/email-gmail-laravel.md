# Configure Laravel for sending emails with GMail

The Laravel Framework provides several drivers for sending emails, via SMTP, Mailgun, Postmark, Sendmail...

---

### Set Google Account

If we already have a Google account, then let's connect to this page **[Google Account](https://myaccount.google.com/)** and log in, in the **Security** section accessible from the menu on the left. We activate the **Two-step verification**, again from "Two-step verification" we scroll to the bottom of the page and go to the **App passwords** section passwords for apps. We generate a password for our app to which we give a name, the generated password is a **string**, we take note of this password because we will use it instead of that of our GMail account in the Laravel configuration.

---

### Edit file .env

```php
MAIL_MAILER=smtp
MAIL_HOST=smtp.gmail.com
MAIL_PORT=465
MAIL_USERNAME=example@gmail.com
MAIL_PASSWORD=password
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=example@gmail.com
MAIL_FROM_NAME="${APP_NAME}"
```
**example @gmail.com** is our GMail account email, **password** is the password we generated before in the "Two-Step Verification" section of our Google account, so we change these values ​​to ours.

---

### Edit config\mail.php

we also modify the **smtp** key of the config\mail.php file.

```php
  'smtp' => [
       'transport' => 'smtp',
       'host' => env('MAIL_HOST'),
       'port' => env('MAIL_PORT'),
       'encryption' => env('MAIL_ENCRYPTION'),
       'username' => env('MAIL_USERNAME'),
       'password' => env('MAIL_PASSWORD'),
       'timeout' => null,
       'local_domain' => env('MAIL_EHLO_DOMAIN'),
     ],
```

---

### Create class Email

We now generate the class to define the email settings via CLI using the php artisan command, we give a name to this class, in this example it is SendEmailGmail, then we launch the following command:

```bash
php artisan make:mail SendEmailGmail
```

a SendEmailGmail class will be generated in \App\Mail\ similar to this:

```php
<?php

namespace App\Mail;

use Illuminate\Bus\Queueable;
use Illuminate\Contracts\Queue\ShouldQueue;
use Illuminate\Mail\Mailable;
use Illuminate\Mail\Mailables\Content;
use Illuminate\Mail\Mailables\Envelope;
use Illuminate\Queue\SerializesModels;

class SendEmailGmail extends Mailable
{
    use Queueable, SerializesModels;

    /**
     * Create a new message instance.
     *
     * @return void
     */
    public function __construct()
    {
        //
    }

    /**
     * Get the message envelope.
     *
     * @return \Illuminate\Mail\Mailables\Envelope
     */
    public function envelope()
    {
        return new Envelope(
            subject: 'Send Email Gmail',
        );
    }

    /**
     * Get the message content definition.
     *
     * @return \Illuminate\Mail\Mailables\Content
     */
    public function content()
    {
        return new Content(
            view: 'view.name',
        );
    }

    /**
     * Get the attachments for the message.
     *
     * @return array
     */
    public function attachments()
    {
        return [];
    }
}
```
this default class is made up of three functions, in **envelope()** the subject of the email is defined, in **content()** the content of the email is defined and in **attachments()** any attachments of the email, for now we leave this class as it is then later we will make the appropriate changes.

---

## Create the views

Let's create the content of the email in **\resources\views\mail\email**.blade.php, the mail folder does not exist in the default Laravel application, so let's create it ourselves.

We also create the pages to display when the email is sent successfully or an error occurs, then in \resources\views\mail\ we create two files **success.blade.php** and **error.blade.php**.

---

## Indicate the correct content of the email in the content() function.

```php
    public function content()
    {
        return new Content(
            view: 'view.name',
        );
    }
```

---

## Create a path in \routes\web.php that will allow us to send the email

```php
<?php


   use Illuminate\Support\Facades\Route;
   use App\Mail\SendEmailGmail;
   use Illuminate\Support\Facades\Mail;

        ...................
        ...................
   
   Route::get('/send-email', function() {
    try {
        
        Mail::to('example@domain.com')->send(new SendEmailGmail());
        return view('mail.success');
    
    }catch (\Exception $e) {
        return view('mail.error');
    }
    
});
```

**example @domain.com** is the recipient of the email, now to send the email just open the URL /send-email of our Laravel application in the browser. If the email is sent correctly we will display the contents of the **success.blade.php** page.