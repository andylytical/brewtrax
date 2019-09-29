# BREWTRAX
Brewery and Tilt Hydrometer log tracking and cloud storage

# Usage

1. Edit docker-compose.yaml
   1. See "Environment Variables" below.
1. docker-compose up

## Environment Variables

### Reading data from tilt

* PYTILT_CSVOUTFILE
    CSV formatted output file
* PYTILT_SAMPLE_PERIOD
    Elapsed time, in seconds, of a single sample period.
    Data will be collected for this entire period and a single value, the "median",
    will be returned.
* PYTILT_SAMPLE_RATE
    How long, in seconds, to wait between taking samples during a sample period.
    The total number of samples in a single "sample period" is the result of
    "sample_period" / "sample_rate"
* PYTILT_COLOR
    Limit the output to a single tilt color. If left undefined, all tilt colors
    are reported.

### Pushing data to google cloud storage

* GOOGLE_AUTH_CLIENT_SECRETS_FILE
    Filesystem path, on the local machine, to the client secrets file.
    This is downloaded manually from your Google account.
    See "One-Time Setup" <-- LINK HERE
* GOOGLE_AUTH_CREDENTIALS_FILE
    Filesystem path, on the local machine, to store the auth credentials file.
    This is generated on the first connection, and updated automatically by the software.
* GOOGLE_DRIVE_FOLDER_ID
    Parent folder ID where to search for the google sheet name in which to store data.
* GOOGLE_SHEETS_SHEET_NAME
    Name (unambiguous prefix) of the google sheet in which to store data.
* CLOUD_BACKUP_INTERVAL_SECONDS
    How often, in seconds, to push data to the cloud. Defaults to 3600 = 1 hour.

