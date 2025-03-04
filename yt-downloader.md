# Youtube Downloader

The code uses the yt_dlp library to download videos from YouTube (or other supported sites) and save them in a specified folder. The yt_dlp library is a fork of youtube-dl with additional improvements and updates.

```bash
pip install yt-dlp
```

```bash
from yt_dlp import YoutubeDL

link = "" #URL video
output_folder = "./videos" #folder path

ydl_opts = {
    'format': 'bestvideo+bestaudio/best', #unisce audio e video
    'merge_output_format': 'mp4', #formato
    'outtmpl': f'{output_folder}/%(title)s.%(ext)s', #cartella di salvataggio
}

with YoutubeDL(ydl_opts) as ydl:
    ydl.download([link])
```

**link = ""** A string containing the URL of the video you want to download. It is currently empty (""), so it needs to be filled with the correct URL.

**output_folder = "./videos"** A string that specifies the folder where the downloaded video will be saved. The default path is ./videos, which means a folder called "videos" in the current directory.

**'format': 'bestvideo+bestaudio/best'** Specifica il formato del video da scaricare. In questo caso, 'bestvideo+bestaudio/best' indica di scaricare la migliore qualità disponibile per il video e l'audio separatamente, e poi unirli. Se non è possibile, scarica il miglior formato disponibile che include già sia video che audio.

**'merge_output_format': 'mp4'** Specifies the final file format after merging video and audio. In this case, 'mp4' indicates that the final file will be in MP4 format.

**'outtmpl': f'{output_folder}/%(title)s.%(ext)s'** Specifica il template per il nome del file di output. Il template '%(title)s.%(ext)s' utilizza il titolo del video come nome del file e l'estensione del formato scelto. Il percorso di salvataggio è prefissato con output_folder, quindi il video verrà salvato nella cartella specificata.

**with YoutubeDL(ydl_opts) as ydl** Creates an instance of YoutubeDL with the specified options. The with block ensures that resources are properly freed after download.

**ydl.download([link])** Starts downloading the video specified by the URL contained in the link variable. The URL is passed as a list, so you can pass multiple URLs if you want to download multiple videos at once.