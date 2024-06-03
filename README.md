<p align="right">
  [English]
  [<a href="README-ko.md">한국어</a>]
</p>

# YTDClip

YTDClip is a tool that simplifies downloading YouTube videos by offering various format and quality options. This project is built using the yt-dlp library in Python.

> I created YTDClip to reduce the hassle of finding and downloading regularly updated content one by one. By adding items to your favorites list and specifying their numbers, YTDClip will skip already downloaded content and download only the newly updated content.

## Features

- Download YouTube videos (Videos, Shorts, Playlists)
- Convert to various formats (mp4, webm, mp3, m4a, etc.)
- Offer multiple quality options (highest video+audio, video, audio, general)
- Batch download from a list of URLs in a file (txt)
- Support interactive mode for easy operation

<img width="682" alt="ss" src="https://github.com/micronzone/YTDClip/assets/47780105/55f09620-cdc6-4c47-93bb-ef2ba674b0ad">

## Installation

Clone the project:

```bash
git clone https://github.com/micronzone/YTDClip.git
cd YTDClip
```

Grant execute permission:

```bash
chmod +x ytdclip
```

(Optional) Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate  # Linux or macOS
.\.venv\Scripts\activate   # Windows
```

Install the required libraries using pip:

```bash
pip3 install -r requirements.txt
```

Alternatively, you can install yt-dlp>=2023.05.18:

```bash
pip3 install yt-dlp
```

Add alias (optional):

```bash
nano ~/.zshrc   # macOS ~/.zshrc, Linux `~/.bashrc` or `~/.zshrc`
alias ytdclip='/path/to/ytdclip'
```

```bash
source ~/.zshrc
```

## Usage
YTDClip can be used through a command-line interface (CLI) or in interactive mode.

Options
- `-a`: Run interactively
- `-l FILE`: Load URLs of YouTube `Videos`, `Shorts`, `Playlists` from a `txt` file
- `-e`, `--extension` {`mp4`, `webm`, `mp3`, `m4a`, etc.}: Specify the extension of the file to download (default: mp4)
- `-f`, `--format` {`b`, `bv`, `ba`, `bb`}: Specify download quality (b=general video+audio, bv=best video, ba=best audio, bb=best video+audio, default: b)
- `-o`, `--output` `PATH`: Specify the download directory
- `--debug`: Enable debug logging

## Command-Line Interface (CLI) Usage

Basic usage is as follows:

```bash
# Using alias (refer to installation) or run ./ytdclip from the YTDClip directory
ytdclip
ytdclip [YouTube URL]
ytdclip [options] [YouTube URL]
```

Using a list of YouTube URLs:

```bash
ytdclip [options] [Favorites.txt]
```

```bash
# [YouTube URL], [Comment]
https://www.youtube.com/watch?v=example, Informative video
https://www.youtube.com/@example, Grizzly Bear
https://www.youtube.com/@example/shorts, Dance Shorts
https://www.youtube.com/@example/playlists, Favorite playlists
```
## Examples

Simple example to download a YouTube video:

Run interactively:

```bash
ytdclip -a
```

Run interactively with specified options:

```bash
ytdclip -a -o ~/Downloads
ytdclip -a -o ~/Downloads -e mp4
ytdclip -a -o ~/Downloads -e mp4 -f b
ytdclip -a -o ~/Downloads -e mp4 -f b -l favorites.txt
```

Run from the command line:

```bash
ytdclip -o ~/Downloads -e mp4 -f b https://www.youtube.com/watch?v=YOUR_VIDEO_ID
```

Run with a list of YouTube URLs from the command line:

```bash
ytdclip -o ~/Downloads -e mp4 -f b -l favorites.txt
```

## Updating
It's a good idea to check for updates in the YTDClip repository!

```bash
cd YTDClip
git status
```

Fetch changes:

```bash
git pull origin main
```

## Contributing

Thank you for your interest in contributing! To contribute to this project, follow these steps:

1. Fork this repository
2. Create a feature branch (git checkout -b micronzone/YTDClip)
3. Commit your changes (git commit -m 'Add some YTDClip')
4. Push to the branch (git push origin micronzone/YTDClip)
5. Open a pull request

## License

This project is distributed under the MIT License. See the [LICENSE](LICENSE) file for details.