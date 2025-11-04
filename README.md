# 🚀 LinkedIn Post Automation with Image Upload (RSS → AI → LinkedIn)

## 🎬 Video Demo

Watch the full workflow demo here:  
▶️ https://youtu.be/Zgv1KPXB6Cc

## 📘 Overview
This workflow is a **fully automated content pipeline** built with **n8n** that transforms your **YouTube channel content** into **professional LinkedIn posts** — complete with an **AI-generated cover image**, **clean transcript**, and **Google Sheets tracking**.

It is a no-touch automation that continuously monitors your YouTube RSS feed, extracts the latest video details, generates an engaging post using AI, and publishes it directly to LinkedIn — saving hours of manual work.

---

## 🎯 Purpose
To automate the entire process of:
- Fetching new YouTube videos from an RSS feed
- Extracting and cleaning video transcripts
- Generating a polished LinkedIn post (title + body)
- Creating an AI-based cover image (Flux.1 Schnell)
- Uploading the image to Google Drive
- Publishing the post to LinkedIn
- Logging all post details to Google Sheets

This same workflow can also be adapted for posting on other social platforms like **Facebook**, **Twitter (X)**, or **Instagram**.

---

## 🧠 Workflow Summary

### 🔹 Input
- YouTube RSS feed (video metadata + link)
- AI models (Gemini / DeepSeek)
- APIs (RapidAPI, Hugging Face, LinkedIn, Google)

### 🔹 Output
- Published LinkedIn post (with image)
- Google Drive image copy
- Google Sheets log of all published posts

---

## ⚙️ Step-by-Step Workflow

### 1. **RSS Feed Trigger**
- Checks the YouTube RSS feed every **6 hours**.
- Filters only videos published in the **last 6h + 15min buffer**.
- Ensures no duplicate posts for old videos.

### 2. **Transcript Extraction**
- Uses **RapidAPI – YouTube Video Summarizer** to fetch multilingual transcripts.
- Extracts and combines transcripts into a single clean text file.

### 3. **Transcript Cleaning (AI)**
- Uses **Google Gemini** or **DeepSeek** to:
  - Remove filler words
  - Correct grammar
  - Keep the original message intact
  - Output: “Clean Transcript”

### 4. **LinkedIn Post Generation**
- The clean transcript is sent to the AI again to produce:
  - **Post Title**
  - **Post Content** (LinkedIn-optimized)
  - **Image Prompt** (for cover generation)
- The AI output is validated with a strict JSON schema for reliability.

### 5. **AI Cover Image Generation**
- Uses **Hugging Face – Flux.1 Schnell Model** to create:
  - A professional, editorial-style image based on the post theme.
- Output: `.png` image file.

### 6. **Image Upload to Google Drive**
- Saves generated image into a dedicated folder (`LinkedIn Images`) on Google Drive.

### 7. **LinkedIn Posting**
- Publishes post (text + image) to LinkedIn using LinkedIn’s OAuth2 API.
- Generates a post URN and retrieves the public post link.

### 8. **Google Sheets Logging**
- Logs each post with details:
  - Video Link
  - Post Title
  - Post Text
  - Image Link
  - LinkedIn Post URL
  - Timestamp

---

## 🤖 Integrated APIs & Tools

| Service | Purpose |
|----------|----------|
| **YouTube RSS** | Detect new videos |
| **RapidAPI (YouTube Summarizer)** | Fetch video transcript |
| **Google Gemini / DeepSeek** | Clean transcript & generate post |
| **Hugging Face (Flux.1 Schnell)** | Generate AI cover image |
| **LinkedIn API (OAuth2)** | Post to LinkedIn |
| **Google Drive** | Store generated images |
| **Google Sheets** | Track published posts |

---


