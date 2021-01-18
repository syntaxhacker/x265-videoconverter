# x265-converter
A database focused media conversion utility that converts video files to the
HEVC video codec with a focus on reducing disk usage in media libraries. This
script attempts to be as safe as possible, however encoding to HEVC is a lossy
operation. though it should be unnoticable it is recommended to test first.
Backups are encouraged.

# requirements:
x265-videoconverter needs python3 and ffmpeg
The latest version of ffmpeg is 4.1.4 when testing, download from [ffmpeg](https://ffmpeg.org/download.html).

# typical usage:
    python3 main.py -t /path/to/media -s
    python3 main.py -n 10
# example usage:

    usage: python3 main.py [-h] [--crf int] [--errors] [--database DATABASE] [--focus PATH] [--list-paths] [--low-profile] [--number NUMBER] [--nvenc] [--preset PRESET] [--track PATH] [--saved-space] [--scan] [--quiet] [--verbose]

    A database focused media conversion utility that converts video files to the HEVC video codec with a focus on reducing disk usage in media libraries. This script attempts to be as safe as possible, however encoding to HEVC is a lossy operation. though it should be
    unnoticable it is recommended to test first. Backups are encouraged.

    optional arguments:
    -h, --help            show this help message and exit
    --crf int             CRF paramater to be passed through to ffmpeg, determines quality and speed with lower values being slower but higher quality
    --errors, -e          list errors
    --database DATABASE   name of database to be used
    --focus PATH, -f PATH
                            immediately begin conversion on target directory
    --list-paths, -lp     list tracked paths
    --low-profile         for weaker devices, convert to 4-bit HEVC including downgrading 10-bit hevc
    --number NUMBER, -n NUMBER
                            transcode from tracked paths limit number of files to be converted
    --nvenc               transcode using NVENC compatable GPU
    --preset PRESET       string for ffmpeg paramater, accepts ultrafast, superfast, veryfast, faster, fast, medium, slow, slower, veryslow and placebo, slower speeds have a higher filesize and better quality
    --track PATH, -t PATH
                            add a new path to be tracked
    --saved-space         display HDD space saved by transcoding into x265
    --scan, -s            scan tracked directories for new files
    --quiet, -q           only produce minimal output
    --verbose, -v         produce as much output as possible
