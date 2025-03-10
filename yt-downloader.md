# Youtube Downloader w/ Python

The code uses the yt_dlp library to download videos from YouTube (or other supported sites) and save them in a specified folder. The yt_dlp library is a fork of youtube-dl with additional improvements and updates.

```bash
pip install yt-dlp
```

We also need to download the ffmpeg library for managing multimedia files, we can do it through homebrew.

```bash
brew install ffmpeg
```

```bash
from yt_dlp import YoutubeDL

link = "" 
output_folder = "./videos" 

ydl_opts = {
    'format': 'bestvideo+bestaudio/best', 
    'merge_output_format': 'mp4', 
    'outtmpl': f'{output_folder}/%(title)s.%(ext)s',
}

with YoutubeDL(ydl_opts) as ydl:
    ydl.download([link])
```

**link = ""** A string containing the URL of the video you want to download. It is currently empty (""), so it needs to be filled with the correct URL.

**output_folder = "./videos"** A string that specifies the folder where the downloaded video will be saved. The default path is ./videos, which means a folder called "videos" in the current directory.

**'format': 'bestvideo+bestaudio/best'** Specify the format of the video to download. In this case, 'bestvideo+bestaudio/best' instructs you to download the best available quality for the video and audio separately, and then merge them. If that's not possible, download the best format available that already includes both video and audio.

**'merge_output_format': 'mp4'** Specifies the final file format after merging video and audio. In this case, 'mp4' indicates that the final file will be in MP4 format.

**'outtmpl': f'{output_folder}/%(title)s.%(ext)s'** Specify the template for the output file name. The template '%(title)s.%(ext)s' uses the title of the video as the filename and the extension of the chosen format. The save path is prefixed with output_folder, so the video will be saved in the specified folder.

**with YoutubeDL(ydl_opts) as ydl** Creates an instance of YoutubeDL with the specified options. The with block ensures that resources are properly freed after download.

**ydl.download([link])** Starts downloading the video specified by the URL contained in the link variable. The URL is passed as a list, so you can pass multiple URLs if you want to download multiple videos at once.