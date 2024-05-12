
# Plex-Tidal-DL

**Plex-Tidal-DL** is a Python script designed to enhance your music experience by integrating Plex with Tidal. If you have a Tidal subscription and use Plex as your media server, this script automates the process of checking for newly favorited Tidal albums and downloading them using Tidal-DL. Once downloaded, the script updates your Plex library to include these new additions.

## Features
- **Automatic Syncing**: Regularly checks for new favorited albums on Tidal and downloads them.
- **Plex Library Updates**: Automatically refreshes your Plex library with newly downloaded content.
- **Flexible Scheduling**: Configure the frequency of checks to suit your needs.

## Prerequisites
- A Plex server setup with access to a Tidal subscription.
- Python 3.x installed on your system.
- Tidal-DL installed, which can be found [here](https://github.com/yaronzz/Tidal-Media-Downloader).


## Setup
On Windows, I created a job in Task Scheduler with a daily trigger. The program/script field should a path to python.exe. The argument should be the directory containing the script with any arguments:
```bash
"C:\Users\Morgan\Desktop\Plex-Tidal-DL-job.py" --s --i 60m
```

## Usage
To start the script with the default settings (checking every 30 minutes):
```bash
python plex-tidal-dl.py
```

You can start and scan immediately by add '--s'
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


## Acknowledgments
Special thanks to **dirty-jimm** for his original script. Check it out [here](https://github.com/dirty-jimm/Tidal_DL_Plus).


