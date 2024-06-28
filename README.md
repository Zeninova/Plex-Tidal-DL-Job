
# Plex-Tidal-DL

Plex supports Tidal integration. If you have a Tidal subscription and use Plex as your media server, this script automates the process of checking for newly favorited Tidal albums and downloading them using Tidal-DL. Once downloaded, the script updates your Plex library to include these new additions.

This is a simplified version of the [Plex-Tidal-DL script](https://github.com/Zeninova/Plex-Tidal-DL) that lacks a settings menu. This is useful if you just want to run the script from a task scheduler.

## Features
- **Automatic Syncing**: Regularly checks for new favorited albums on Tidal and downloads them.
- **Plex Library Updates**: Automatically refreshes your Plex library with newly downloaded content.
- **Daily Logging**: Automatically creates logs in the script's directory. New logs are created daily at midnight.

## Prerequisites
- A Plex server setup with access to a Tidal subscription.
- Python 3.x installed on your system.
- Tidal-DL installed, which can be found [here](https://github.com/yaronzz/Tidal-Media-Downloader).

## Usage
To start the script with the default settings (checking every 30 minutes):
```bash
python plex-tidal-dl.py
```

You can start and scan immediately by adding '--s'
```bash
python plex-tidal-dl.py --s
```

### Changing the Check Interval
You can adjust the frequency of checks by using the command-line argument `--i` or `--interval`:
- To set the interval to 60 minutes:
  ```bash
  python plex-tidal-dl.py --i 60m
  ```
- To set the interval to 10 seconds and start immediately:
  ```bash
  python plex-tidal-dl.py --i 10s --s
  ```

**Note**: Only minute (m) and second (s) intervals are supported.

## Setup
On Windows, I created a job in Task Scheduler with a daily trigger. The program/script field should be a path to python.exe. The argument should be the directory containing the script with any arguments:
```bash
"<SCRIPT DIRECTORY>\Plex-Tidal-DL-job.py" --s --i 60m
```
In this example, the script will scan immediately upon starting, and then scan every 60 minutes after that.

## Acknowledgments
Special thanks to **dirty-jimm** for his original script. Check it out [here](https://github.com/dirty-jimm/Tidal_DL_Plus).


