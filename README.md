# Jarvis - Virtual Assistant Bot

A Python-based virtual assistant that responds to voice commands and can perform various tasks including web browsing, music playback, news retrieval, and AI-powered interactions.

## Features

- **Voice Recognition**: Uses Google Speech Recognition to understand voice commands
- **Text-to-Speech**: Converts responses to speech using gTTS (Google Text-to-Speech)
- **Web Browsing**: Opens popular websites (Google, Facebook, YouTube, LinkedIn)
- **Music Playback**: Plays songs from a custom music library
- **News Updates**: Fetches and reads top news headlines
- **AI Integration**: Uses OpenAI's GPT-3.5-turbo for intelligent responses to general queries
- **Always-On Listening**: Activates with "Jarvis" wake word

## Requirements

- Python 3.7+
- Microphone for audio input
- Internet connection

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Amritanshu2210/jarvis.git
cd jarvis
```

2. Install required dependencies:
```bash
pip install speech_recognition pyttsx3 requests openai gtts pygame pocketsphinx
```

3. Install additional system dependencies (if needed):
```bash
# For Ubuntu/Debian
sudo apt-get install python3-pyaudio

# For macOS
brew install portaudio
pip install pyaudio
```

## Configuration

Before running the assistant, you need to set up your API keys:

1. **OpenAI API Key**: 
   - Get your API key from [OpenAI Platform](https://platform.openai.com/api-keys)
   - Replace `"<Your Key Here>"` in `aiProcess()` function

2. **News API Key**:
   - Get your API key from [NewsAPI.org](https://newsapi.org/)
   - Replace `"<Your Key Here>"` in the `newsapi` variable

3. **Music Library** (Optional):
   - Create a `musicLibrary.py` file with your song mappings:
   ```python
   music = {
       "song_name": "spotify_or_youtube_url",
       "another_song": "url"
   }
   ```

## Usage

Run the assistant:
```bash
python main.py
```

Once running:
1. Say **"Jarvis"** to activate the assistant
2. Wait for the confirmation response ("Ya")
3. Speak your command

### Available Commands

- **"Open Google"** - Opens google.com
- **"Open Facebook"** - Opens facebook.com
- **"Open YouTube"** - Opens youtube.com
- **"Open LinkedIn"** - Opens linkedin.com
- **"Play [song name]"** - Plays a song from your music library
- **"News"** - Reads the latest headlines from India
- Any other command - Processed by OpenAI GPT-3.5-turbo

## Project Structure

```
jarvis/
├── main.py              # Main application file
├── musicLibrary.py      # Music library mappings (to be created)
└── README.md           # This file
```

## How It Works

1. **Initialization**: Starts the voice recognition engine and initializes Jarvis
2. **Wake Word Detection**: Continuously listens for the "Jarvis" wake word
3. **Command Recognition**: Once activated, listens for the user's command
4. **Command Processing**: Routes the command to appropriate function:
   - Web browsing commands → Opens URL in browser
   - Music commands → Plays music from library
   - News command → Fetches and reads news
   - Other commands → Sends to OpenAI for intelligent response
5. **Response**: Speaks the response using text-to-speech

## Dependencies

| Package | Purpose |
|---------|---------|
| `speech_recognition` | Voice input recognition |
| `pyttsx3` | Text-to-speech engine (legacy) |
| `gtts` | Google Text-to-Speech |
| `pygame` | Audio playback |
| `requests` | HTTP requests for APIs |
| `openai` | OpenAI API integration |
| `pocketsphinx` | Offline speech recognition (optional) |

## Troubleshooting

### Microphone not detected
- Check if your microphone is connected and set as default
- Install `pyaudio`: `pip install pyaudio`

### API Key errors
- Verify your API keys are correctly set in the code
- Check that your OpenAI account has sufficient credits
- Ensure NewsAPI key is valid

### Audio playback issues
- Make sure Pygame is properly installed
- Check speaker volume and connections
- Ensure `temp.mp3` file can be created in the working directory

### Speech recognition errors
- Speak clearly and at a normal pace
- Ensure there's minimal background noise
- Check internet connection for Google Speech Recognition

## Future Enhancements

- Add more command types (weather, reminders, calendar integration)
- Implement local wake word detection for offline operation
- Add voice command customization
- Create a GUI interface
- Add support for multiple languages
- Implement command history and logging

## License

This project is open source and available under the MIT License.

## Author

Created by Amritanshu2210

## Contributing

Feel free to fork this project and submit pull requests for any improvements!

## Disclaimer

This project requires valid API keys from OpenAI and NewsAPI. Usage may incur costs depending on the API plans. Please review the terms and pricing of each service before use.
