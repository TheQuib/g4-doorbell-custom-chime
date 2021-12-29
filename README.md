# G4-Doorbell-Custom-Chime
Checks for custom chime on UniFi Protect G4 Doorbell and uploads it if it doesn't exist. Written in Python

## Requirements
  - The Netmiko network automation library
    - `pyhthon3 pip install netmiko`
    - Utilizes the `ConnectHandler` class for SSH connections
  - .WAV file with the following specifications (Audacity can do all of this):
    - Specs:
      - Mono
      - 44100 Hz
      - 16 bit
    - Good idea to:
      - Normalize the audio
        - Effect > Normalize
          - Default settings
      - Add a limiter to the audio
        - Effect > Limiter
          - Default settings

## General Usage
This script can be run without command-line arguments by just running `pythonScript.py`, but does accept arguments. You can use `pythonScript.py -h` or `pythonScript.py --help` to get a list of acceptable command-line options for use in automation tasks.

<br>

Current acceptable flags and arguments supported are:
  - -a, --Address
    - IP Address of doorbell to connect to
  - -u, --Username
    - Username to authenticate with (Default: ubnt)
  - -p, --Password
    - Password to authenticate with
  - -f, --File
    - WAV file to upload to doorbell, specifications can be found in [Requirements](#requriements)
  - -r, --Reset
    - Reset doorbell chime settings back to default

<br>

The `-r` or `--Reset` flag can be given to reset

<br>

### Tl;dr
Each script uses `argparse` to accept command-line arguments. If you don't give it arguments, you can just run the script and it will prompt you for the required variables.
