# SkyRDS
An RDS screen to display information on music broadcast on Skyrock

# SkyRDS

SkyRDS is a web application that displays real-time information about the currently playing song on **Skyrock Radio**. It dynamically fetches data from Skyrock's API, showing the current track's artist, title, and album cover, while also providing a countdown timer for the end of the song. When a song finishes, the interface updates to indicate either a commercial break or a DJ's speech segment.

Everything is shifted by 20s to be synchronized with the Skyrock audio stream

## Features

- **Real-time Song Display**: Shows the currently playing song's artist, title, and cover image from Skyrock's API.
- **Countdown Timer**: Displays the remaining time for the current song, blinking during the last 15 seconds.
- **Automatic Updates**: The page refreshes every second to check for new songs and update the countdown timer.
- **Commercial/Break Detection**: Switches to a "PUB OU SPEAK" (Ad or DJ Talk) screen when no song is playing.

## Installation

1. Clone this repository to your local machine.
   ```bash
   git clone https://github.com/heavyagain/SkyRDS
   ```

2. Open the `index.html` file in your web browser to run the application.

## How it Works

1. **Song Fetching**: The app sends a request every second to the Skyrock API to retrieve the current playlist.
   - URL: `https://skyrock.fm/api/v3/player/onair/parisidf`
   
2. **Song Display**: When a song is detected, it displays the song's artist, title, and cover image.
   - If no song is playing (i.e., during commercials or DJ talk), the display switches to an alternative screen.

3. **Countdown Timer**: The remaining time for the song is calculated by comparing the current time with the song's end time. The timer is updated every second.

4. **Commercial/Break Detection**: If there is a gap between songs, a "PUB OU SPEAK" message and a placeholder image are displayed after 15s.

## Customization

- **Logo and Background**: The Skyrock logo and background color can be customized via the `#logo` and `body` sections of the CSS.

- **Config** : 
   - apiUrl : Choose between 'natio' or 'parisidf' after /onair/
   - pubOrSpeakText : The text that there mark, when a commercials or a speak is detect
   - pubOrSpeakImage : Default image URL for commercials or speaks
   - countdownColor : Countdown text color
   - endTrackMessage : Message displayed at the end of the track
   - updateIntervalMs : Update interval in milliseconds (1 second)
   - apiRefreshIntervalMs : API refresh interval in milliseconds
## License

This project is licensed under the MIT License.

