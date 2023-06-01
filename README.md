# Pippi - Python Voice Assistant

Pippi is a voice assistant built in Python that allows you to interact with your computer using voice commands. It utilizes the Google Speech Recognition API for speech-to-text conversion and provides several useful features to enhance your productivity and entertainment.

## Features

1. Google Speech Recognition API Integration: Pippi leverages the power of the Google Speech Recognition API to accurately convert spoken words into text, enabling seamless voice interaction.

2. Website Opening: With Pippi, you can conveniently open popular websites like YouTube by simply issuing voice commands. Just say "Open YouTube" and it will launch the website in your default browser.

3. Wikipedia Search: Pippi can perform quick and efficient Wikipedia searches for you. Simply ask a question or specify a topic, and Pippi will fetch the relevant information from Wikipedia.

4. Simple Calculations: Need to perform a quick calculation? Pippi has got you covered. You can ask Pippi to perform simple calculations, such as addition, subtraction, multiplication, and division.

5. Spotify Integration: Pippi enhances your music experience by allowing you to play your favorite songs on Spotify. When you ask Pippi to play a song, it will prompt you to provide the song's name, and then it will search and play the requested song on Spotify.

6. Computer Control: Pippi provides convenient computer control commands. You can ask Pippi to shut down or restart your computer, saving you the hassle of manual operation.

## Requirements

To use Pippi, you'll need the following:

- Python 3.x: Pippi is built using Python, so make sure you have Python 3.x installed on your system.

- Google Speech Recognition Library: Pippi relies on the Google Speech Recognition API for speech recognition. Install the `SpeechRecognition` library by running the following command:

  ```
  pip install SpeechRecognition
  ```

- Spotify API Credentials: For the Spotify integration, you'll need to obtain Spotify API credentials. Visit the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/) and create a new application to obtain the necessary client ID and client secret.

- Spotify Python Library: Pippi uses the `spotipy` library to interact with the Spotify API. Install it by running the following command:

  ```
  pip install spotipy
  ```

- Additional Libraries: Pippi may require additional libraries depending on your system configuration and specific features you're using. Please refer to the requirements provided with the project for a complete list of dependencies and install them.


## Installation

To use Pippi, follow these steps:

1. Clone the repository:

   ```
   git clone https://github.com/jahnavirishikesh/Voice-Assistant-Pippi-using-Python.git
   ```

2. Install the required dependencies as mentioned in the Requirements section.

3. Update the file with your Spotify API credentials:

   ```python
   SPOTIFY_CLIENT_ID = 'your-client-id'
   SPOTIFY_CLIENT_SECRET = 'your-client-secret'
   ```

4. Run the script:

   ```
   python pippi.py
   ```

## Usage

Refer to the Features section in the README file for details on how to use specific features of Pippi.


## License

Pippi is released under the [MIT License](https://opensource.org/licenses/MIT).
```
