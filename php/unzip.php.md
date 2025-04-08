# Extract contents of a ZIP file

The following PHP code aims to extract the contents of a ZIP file into a specified directory. The ZIP file is opened, its contents are extracted to the same directory where the PHP script is located, and finally a success or failure message is displayed.

---

```php
<?php
set_time_limit(3600);
ini_set('memory_limit', '256M');
// Get Project path
// Zip file name
$filename = 'zip.zip';
$zip = new ZipArchive;
$res = $zip->open($filename);
if ($res === TRUE) {
    // Unzip path
    $path = dirname(__FILE__);
    // Extract file
    $zip->extractTo($path);
    $zip->close();
    echo 'Unzip!';
} else {
    echo 'failed!';
}
```

- **set_time_limit(3600)**: Sets the maximum script execution time to 3600 seconds (1 hour). This is useful to prevent the script from terminating prematurely when extracting large files.

- **ini_set('memory_limit', '256M')**: Sets the memory limit that the script can use to 256 MB. This is useful for handling large ZIP files without running into out of memory errors.

- **$filename**: Contains the name of the ZIP file to extract.

- **$zip = new ZipArchive**: Creates an instance of the ZipArchive class, which is used to handle operations on ZIP files.

- **$res = $zip->open($filename)**: Attempts to open the specified ZIP file. The result of the operation is stored in the $res variable.

- **$path = dirname(__FILE__)**: Gets the path to the directory where the current PHP script is located. This path is used as the destination for extracting files.

- **$ zip->extractTo($path)**: Extracts the contents of the ZIP file to the directory specified by $path.

- **$zip->close()**: Closes the ZIP file after extraction.

- **echo 'Unzip!'**: Displays a success message if the extraction was successful.

- **echo 'failed!'**: If opening the ZIP file fails, an error message appears.


