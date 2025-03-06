# Karaoke_Gen - AI-Powered Karaoke Generator

A tool to automatically create karaoke videos by syncing lyrics with audio tracks using AI.

![Karaoke Demo](https://via.placeholder.com/800x450/264653/ffffff?text=LyricSync+Karaoke+Generator)

## Features

- **Vocal Separation**: Uses Spleeter to separate vocals from instrumentals
- **AI Transcription**: Uses Whisper for accurate speech-to-text conversion with timestamps
- **Intelligent Sync**: Matches lyrics to the transcribed audio for accurate timing
- **Professional Output**: Creates karaoke videos with current and upcoming lyrics

## Getting Started

### Option 1: Setup with Conda (Recommended)

```bash
# Clone the repository (if using Git)
git clone https://github.com/yourusername/lyric-sync.git
cd lyric-sync

# Create and activate the conda environment
conda env create -f environment.yml
conda activate lyric-sync

# Run the generator
python karaoke_generator.py --audio song.mp3 --lyrics lyrics.txt --output karaoke.mp4
```

### Option 2: Setup with Pip

```bash
# Install FFmpeg first (system dependent)
# Ubuntu: sudo apt install ffmpeg
# macOS: brew install ffmpeg
# Windows: download from ffmpeg.org

# Install Python dependencies
pip install -r requirements.txt

# Run the generator
python karaoke_generator.py --audio song.mp3 --lyrics lyrics.txt --output karaoke.mp4
```

See the [Setup Instructions](SETUP.md) for detailed installation steps, including GPU setup and troubleshooting.

## Usage Examples

### Basic Usage
```bash
python karaoke_generator.py --audio song.mp3 --lyrics lyrics.txt --output karaoke.mp4
```

### Create Karaoke with Instrumental Track Only
```bash
python karaoke_generator.py --audio song.mp3 --lyrics lyrics.txt --output karaoke.mp4 --use-instrumentals
```

### Custom Styling
```bash
python karaoke_generator.py --audio song.mp3 --lyrics lyrics.txt --output karaoke.mp4 --font "Times New Roman" --fontsize 48 --bg-color "blue" --text-color "white" --highlight-color "yellow"
```

### Foreign Language Support
```bash
python karaoke_generator.py --audio japanese_song.mp3 --lyrics japanese_lyrics.txt --output karaoke.mp4 --language ja
```

## Command-Line Options

```
--audio          Audio file path (required)
--lyrics         Lyrics file path (required)
--output         Output video file path (required)
--timestamps     Timestamps file (if already created)
--temp-dir       Directory for temporary files
--font           Font to use for lyrics (default: Arial)
--fontsize       Font size for lyrics (default: 40)
--bg-color       Background color (default: black)
--text-color     Text color (default: white)
--highlight-color Highlight color for current lyric (default: yellow)
--language       Language code for transcription (default: en)
--skip-separation Skip vocal separation step
--use-instrumentals Use instrumentals for final video
```

## How It Works

1. **Audio Separation**: Spleeter extracts the vocals from the music
2. **Transcription**: Whisper AI analyzes the vocal track to detect words and timing
3. **Lyric Alignment**: The script matches your lyrics to the transcribed words
4. **Video Creation**: A karaoke video is generated with synchronized lyrics

## Requirements

- Python 3.8+
- FFmpeg
- GPU recommended for faster transcription

## License

MIT License - Feel free to use and modify for your projects!