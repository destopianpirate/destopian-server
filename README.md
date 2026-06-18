# Destopian Server

Destopian Server is a high-performance media extraction and download server built with Node.js, Express, Puppeteer, and yt-dlp. It provides API endpoints to fetch media links, extract formats, preview streams, and merge high-quality video and audio formats.

## Features

- Multi-Platform Support: Extract video and audio from YouTube, Instagram, Twitter/X, TikTok, and more.
- Cloud Drive Extraction: Headless scraping via Puppeteer Stealth to bypass anti-bot challenges on Terabox and DiskWala.
- API Key System: Built-in optional authentication with rate limiting for secure and managed access.
- High Quality Merging: Automatic merging of best quality video and audio streams using system FFmpeg.
- Format Caching: In-memory caching mechanism to optimize response times for repeated extractions.

## API Endpoints

All post requests accept a JSON body and require an API key header if authentication is enabled.

- POST `/api/json`: Returns direct download URLs and merges high-quality video and audio.
- POST `/api/formats`: Lists all available qualities, file sizes, and container formats for a given URL.
- POST `/api/audio`: Extracts audio-only streams in various bitrates.
- POST `/api/image`: Returns video thumbnails.
- POST `/api/key`: Generates a new API key with built-in hourly rate limiting.

## Installation and Setup

### Prerequisites

- Node.js (v18 or higher)
- Python 3 (required for yt-dlp)
- FFmpeg (for media stream merging)
- Chromium or Google Chrome (for Puppeteer scraping)

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/destopianpirate/destopian-server.git
   cd destopian-server
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm start
   ```

The server will run on `http://localhost:3000`.

## Docker Deployment

To build and run the server inside a Docker container:

```bash
docker build -t destopian-server .
docker run -p 3000:3000 destopian-server
```
