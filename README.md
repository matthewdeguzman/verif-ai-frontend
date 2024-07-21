# Verif.ai

## Problem

Misinformation is widespread nowadays and it can be hard to distinguish fact from fiction, especially in important moments such as presidential debates or speeches where the fate of a country may lie in the hands of the people who are watching.

## Solution

We created a web application that transcribes text from videos and scrapes the internet for data about what is said in a video. A decision is made by an LLM about what is said based on the evidence that is gathered.

The general shape of the solution allows users to feed us a video which we transcribe using OpenAI's Whisper, an automatic speech recognition (ARS) system, and check for facts or misinformation. The end result displays a list of facts and misinformation gathered from the video.

## Features

- Users can paste a YouTube video link into the page to analyze the facts and false claims said in the video.
- OpenAI's Whisper transcibes the video
- GPT 3.5 determines what statements are claims or just opinions / yapping.

![Transcription Image](https://github.com/matthewdeguzman/verif-ai-frontend/blob/main/assets/transcript1.jpeg)
![Transcription Image](https://github.com/matthewdeguzman/verif-ai-frontend/blob/main/assets/transcript2.jpeg)
