# 🎥 Radarlyte Video Processor

This is a lightweight Python-based video processing microservice for overlaying branding assets (such as logos or text) on top of uploaded video clips. Built for use in Radarlyte's media pipeline, the service is fully containerized and intended for integration into microservice architectures via HTTP.

---

## ✨ Features

- ✅ Add PNG logo overlay to video (bottom-right by default)
- ✅ Resize logo dynamically
- ✅ Automatically delete temp files after each job
- ✅ Returns processed video as `video/mp4`
- ✅ Containerized and production-ready

---

## 📦 Tech Stack

- 🐍 Python 3.11
- 🎞️ [MoviePy](https://zulko.github.io/moviepy/)
- 🚀 Flask
- 🐳 Docker (containerized deployment)
- 🎬 `ffmpeg` (via MoviePy)

---

## 📥 API

### `POST /process`

Upload a video and receive a processed MP4 with an overlaid logo.

**Request:**

- `multipart/form-data` with key `video` (e.g., `.webm`, `.mp4`)
- Example: using curl

```bash
curl -X POST http://localhost:5000/process \
  -F "video=@myvideo.webm" \
  --output processed.mp4
