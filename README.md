# musidl
musidl is a simple command-line utility written in Bash for downloading music from YouTube with ID3v2 tags (used by media players to display the artist, album, etc.). It is licensed under the GNU GPLv3.

musidl requires [yt-dlp](https://github.com/yt-dlp/yt-dlp) to get information about and download the audio from videos, [jq](https://github.com/stedolan/jq) to process JSON, and [eyeD3](https://github.com/nicfit/eyeD3) to add ID3v2 tags.

## Installation

To install, `git clone` this repository, `cd` into it, and run
```sh
sudo ln -s $PWD/musidl /usr/local/bin/musidl
```

## Usage

Help information is also available by running `musidl --help`

Usage: `musidl [options]... [url]... (-- [yt-dlp options])`

Options:

| Flag              | Argument | Description                                                                               |
|-------------------|----------|-------------------------------------------------------------------------------------------|
| `-h`, `--help`    |          | Show help information and exit                                                            |
| `-v`, `--version` |          | Show the version and exit                                                                 |
| `-q`, `--quiet`   |          | Only print errors                                                                         |
| `-f`, `--format`  | `fmt`    | The audio format to use (default: mp3)                                                    |
| `-a`, `--artist`  | `name`   | The audio format to use (default: mp3)                                                    |
| `-A`, `--album`   | `name`   | Set the album title (default: detect from YouTube)                                        |
| `-t`, `--song `   | `name`   | Set the song title (default: detect from YouTube)                                         |
| `-g`, `--genre`   | `name`   | Set the genre (default: none)                                                             |
| `-y`, `--year `   | `year`   | Set the year (default: detect from YouTube)                                               |
| `-T`, `--track`   | `track`  | Set the track (default: detect from playlist, otherwise none)                             |
| `-s`, `--show `   |          | Print information to stdout instead of downloading to file                                |
| `-o`, `--output ` |          | Set the template used for filenames. See the `yt-dlp` documentation for more info     |
| `--color`         | `when`   | Enable or disable colored output. `<when>` must be `always`, `auto` (default), or `never` |

Any arguments after '--' will be sent to yt-dlp directly. These are not officially supported and some may cause problems.
