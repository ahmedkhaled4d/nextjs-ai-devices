<h1 align="center">AI Device Template</h1>
<div>
    <div align="center">
        <a href="https://twitter.com/ahmedkhaled4d">
            <img src="https://img.shields.io/badge/X/Twitter-000000?style=for-the-badge&logo=x&logoColor=white" />
        </a>
        <a href="https://www.youtube.com/@ahmedkhaled4d">
            <img src="https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white" />
        </a>
    </div>
</div>
<h2 style="display: flex; justify-content: center; align-items: left; width: 100%;">Now supports gpt-4o and gemini-1.5-flash-latest for Vision Inference</h2>
<div style="display: flex; justify-content: center; align-items: left; width: 100%;" >
    <div align="center" style="width:100%"> 
        <a href="https://www.youtube.com/@ahmedkhaled4d" >
            <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExMmV0bjdkYzNpcDNka3BoaTFoNDJ3MTl0c3dmN3pqZGdjanh6N3c2YSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/UjkWj9Q6yInxQHp1tY/giphy.gif" style="width: 100%; height: auto;"/>
        </a>
        <a href="https://twitter.com/ahmedkhaled4d" >
            <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExbzZtaTB5eHVzcjlnaHQ5b2c5OGJqeG9kcTk3N3V4eG5xY25mdHlpayZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/GIcUHNXLsv0pEHHQ2i/giphy.gif" style="width: 100%; height: auto;" />
        </a>
    </div>
</div>

This project is an AI-powered voice assistant utilizing various AI models and services to provide intelligent responses to user queries. It supports voice input, transcription, text-to-speech, image processing, and function calling with conditionally rendered UI components. This was inspired by the recent trend of AI Devices such as the Humane AI Pin and the Rabbit R1.

## Features

- **Voice input and transcription:** Using Whisper models from Groq or OpenAI
- **Text-to-speech output:** Using OpenAI's TTS models
- **Image processing:** Using OpenAI's GPT-4 Vision or Fal.ai's Llava-Next models
- **Function calling and conditionally rendered UI components:** Using OpenAI's GPT-3.5-Turbo model
- **Customizable UI settings:** Includes response times, settings toggle, text-to-speech toggle, internet results toggle, and photo upload toggle
- **(Optional) Rate limiting:** Using Upstash
- **(Optional) Tracing:** With Langchain's LangSmith for function execution

## Setup

### 1. Clone the repository

```bash
git clone https://github.com:ahmedkhaled4d/nextjs-ai-devices.git
```

### 2. Install dependencies

```bash
npm install
# or
bun install
```

## 3. Add API Keys

To use this AI-powered voice assistant, you need to provide the necessary API keys for the selected AI models and services.

### Required for core functionality

- **Groq API Key** For Llama + Whisper
- **OpenAI API Key** for TTS and Vision + Whisper
- **Serper API Key** for Internet Results

### Optional for advanced configuration

- **Langchain Tracing** for function execution tracing
- **Upstash Redis** for IP-based rate limiting
- **Spotify** for Spotify API interactions
- **Fal.AI (Lllava Image Model)** Alternative vision model to GPT-4-Vision

Replace 'API_KEY_GOES_HERE' with your actual API keys for each service.

### 4. Start the development server

```bash
npm run dev
# or
bun dev
```

Access the application at `http://localhost:3000` or through the provided URL.

## Configuration

Modify `app/config.tsx` to adjust settings and configurations for the AI-powered voice assistant. Here’s an overview of the available options:

```typescript
export const config = {
  // Inference settings
  inferenceModelProvider: "groq", // 'groq' or 'openai'
  inferenceModel: "llama3-8b-8192", // Groq: 'llama3-70b-8192' or 'llama3-8b-8192'.. OpenAI: 'gpt-4-turbo etc

  // BELOW OPTIONAL are some options for the app to use

  // Whisper settings
  whisperModelProvider: "openai", // 'groq' or 'openai'
  whisperModel: "whisper-1", // Groq: 'whisper-large-v3' OpenAI: 'whisper-1'

  // TTS settings
  ttsModelProvider: "openai", // only openai supported for now...
  ttsModel: "tts-1", // only openai supported for now...s
  ttsvoice: "alloy", // only openai supported for now... [alloy, echo, fable, onyx, nova, and shimmer]

  // OPTIONAL:Vision settings
  visionModelProvider: "google", // 'openai' or 'fal.ai' or 'google'
  visionModel: "gemini-1.5-flash-latest", // OpenAI: 'gpt-4o' or  Fal.ai: 'llava-next' or  Google: 'gemini-1.5-flash-latest'

  // Function calling + conditionally rendered UI
  functionCallingModelProvider: "openai", // 'openai' current only
  functionCallingModel: "gpt-3.5-turbo", // OpenAI: 'gpt-3-5-turbo'

  // UI settings
  enableResponseTimes: false, // Display response times for each message
  enableSettingsUIToggle: true, // Display the settings UI toggle
  enableTextToSpeechUIToggle: true, // Display the text to speech UI toggle
  enableInternetResultsUIToggle: true, // Display the internet results UI toggle
  enableUsePhotUIToggle: true, // Display the use photo UI toggle
  enabledRabbitMode: true, // Enable the rabbit mode UI toggle
  enabledLudicrousMode: true, // Enable the ludicrous mode UI toggle
  useAttributionComponent: true, // Use the attribution component to display the attribution of the AI models/services used

  // Rate limiting settings
  useRateLimiting: false, // Use Upstash rate limiting to limit the number of requests per user

  // Tracing with Langchain
  useLangSmith: true, // Use LangSmith by Langchain to trace the execution of the functions in the config.tsx set to true to use.
};
```

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

I'm the developer behind Developers Digest. If you find my work helpful or enjoy what I do, consider supporting me. Here are a few ways you can do that:

- **Website**: Check out my website at [ahmedkhaled4d.com](https://ahmedkhaled4d.com)
- **Github**: Follow me on GitHub at [github.com/ahmedkhaled4d](https://github.com/ahmedkhaled4d)
- **Twitter**: Follow me on Twitter at [twitter.com/ahmedkhaled4d](https://twitter.com/ahmedkhaled4d)
