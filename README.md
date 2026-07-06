# Roanoke Cam Timelapse

This repository contains scripts and configuration for capturing a timelapse from the Roanoke camera and assembling images into a timelapse video.

## Contents
- scripts/ - capture and processing scripts
- config/ - configuration files
- README.md - this file

## Requirements
- A Linux-based system (Raspberry Pi / server)
- ffmpeg (for assembling timelapse video)
- wget or curl (for downloading images)
- cron or systemd timers for scheduling

## Installation
1. Clone the repository:
   git clone https://github.com/scottobear2/roanoke-cam-timelapse.git
2. Install required tools:
   sudo apt update && sudo apt install ffmpeg wget curl

## Configuration
- Edit files in `config/` to set the camera URL, output directories, and schedule.
- Ensure the capture script has execute permission:
  chmod +x scripts/capture.sh

## Usage
- To capture images manually:
  ./scripts/capture.sh
- To create a timelapse from captured images:
  ./scripts/make_timelapse.sh

## Scheduling
Use cron or systemd timers to run the capture script at your desired interval. Example cron entry (every 5 minutes):

*/5 * * * * /path/to/roanoke-cam-timelapse/scripts/capture.sh >> /var/log/roanoke-capture.log 2>&1

## Contributing
Contributions are welcome. Please open an issue or submit a pull request with your changes.

## License
MIT License. See LICENSE file if present.
