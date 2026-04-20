# PeteZah-Next-Password-Bot Web Interface

A web interface for PeteZah-Next-Password-Bot, allowing users to retrieve passwords directly from the browser.

## Features

- Get the latest password from Redis
- Displays request count with ordinal formatting
- Discord-like interface
- Static deployment ready

## Setup

Before deploying, you need to configure the Upstash Redis credentials in `index.html`:

```javascript
const UPSTASH_URL = 'YOUR_UPSTASH_REDIS_REST_URL'; // e.g., https://your-redis.upstash.io
const UPSTASH_TOKEN = 'YOUR_UPSTASH_REDIS_REST_TOKEN';
```

Get these from your [Upstash](https://upstash.com) Redis database.

## Deployment

This is a static website that can be deployed on any static host like Netlify, Vercel, GitHub Pages, etc.

### Netlify Deployment

1. Fork or clone this repository
2. Go to [Netlify](https://netlify.com)
3. Click "New site from Git"
4. Connect your repository
5. Deploy (no build settings needed, it's static HTML)

### Local Development

Open `index.html` directly in your web browser, or serve it with a local server:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser.

## How it Works

The bot fetches passwords from Redis using keys in the format `password:YYYY-MM`. It prioritizes next month's password over the current month's. Each request increments a counter stored in Redis.

## Original Bot

This web interface replicates the functionality of the [PeteZah-Next-Password-Bot](https://github.com/PeteZah-Games/PeteZah-Next-Password-Bot) Discord bot.