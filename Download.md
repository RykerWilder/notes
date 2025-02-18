# Download MongoDB for MacOS with Homebrew

MongoDB is a powerful, flexible NoSQL database that is widely used for modern web applications. Installing MongoDB locally on your MacBook is straightforward, especially when using the Homebrew package manager.


**Install Homebrew**
Homebrew is a popular package manager for macOS that simplifies the installation of software. If you don’t have Homebrew installed, you can install it by running the following command in your Terminal:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Update Homebrew and Tap the MongoDB Formula**
MongoDB is included in the official Homebrew formulae, but it’s a good practice to ensure that your Homebrew is up-to-date. Additionally, you need to tap the MongoDB repository to get the latest versions:

```bash
brew update
```
```bash
brew tap mongodb/brew
```

**Install MongoDB**
With Homebrew updated and the MongoDB formula tapped, you can now install MongoDB. Execute the following command in your Terminal:

```bash
brew install mongodb-community
```

**Start MongoDB**
After the installation, you can start MongoDB as a background service. Running it as a service ensures that it starts automatically at login and continues running in the background:

```bash
brew services start mongodb/brew/mongodb-community
```

**Verify the installation**
To ensure that MongoDB is installed correctly and running, you can connect to the MongoDB shell. Open the Terminal and type:

```bash
mongosh
```

**Stop MongoDB**
If you need to stop MongoDB, perhaps for maintenance or system updates, you can stop the service with the following command:

```bash
brew services stop mongodb/brew/mongodb-community
```

**Uninstalling MongoDB**
If you ever need to uninstall MongoDB, you can do so easily with Homebrew:

```bash
brew services stop mongodb/brew/mongodb-community
```
```bash
brew uninstall mongodb/brew/mongodb-community
```