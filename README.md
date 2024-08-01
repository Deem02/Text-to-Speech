# Text To Speech Converter 🎤🗣️

Welcome to the **Text To Speech Converter** project! This is a simple web application that allows you to convert written text into spoken words using your browser's built-in speech synthesis capabilities. 

## Table of Contents
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Code Walkthrough](#code-walkthrough)
- [Demo](#demo)


## Features ✨

- **User-Friendly Interface**: A clean and intuitive user interface for easy and convenient usage. 🤩
- **Voice Selection**: Choose from a variety of available voices to find the one that suits your preference. 🔊
- **Real-Time Speech**: Hear your text read out loud instantly as you interact with the application. 🔍
- **Responsive Design**: The application is designed to work seamlessly on desktop and mobile devices. 📱

## Getting Started  🚀

### Prerequisites

To use the Text To Speech Converter, you will need a modern web browser that supports the Web Speech API. Most major browsers, such as Google Chrome, Mozilla Firefox, and Microsoft Edge, support this feature. 🌐

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/text-to-speech-converter.git
   ```
2. Navigate to the project directory:
   ```bash
   cd text-to-speech-converter
   ```
3. Open the `index.html` file in your preferred web browser. 💻

## Usage

1. Enter the text you want to convert to speech in the provided text area. 📝
2. Select the desired voice from the dropdown menu. 🔍
3. Click the "Listen" button to hear the text read aloud. 🔊

## Project Structure 📂

- `index.html`: The main HTML file that contains the structure of the application.
- `style.css`: The CSS file responsible for the styling of the application.
- `script.js`: The JavaScript file that handles the text-to-speech functionality.

## Code Walkthrough 💻

Here's a closer look at the core JavaScript function that powers the text-to-speech conversion:

```javascript
let speech = new SpeechSynthesisUtterance();

let voices = [];

let voiceSelect = document.querySelector("select");

window.speechSynthesis.onvoiceschanged = () => {
    voices = window.speechSynthesis.getVoices();
    speech.voice = voices[0];

    voices.forEach((voice, i) => (voiceSelect.options[i] = new Option(voice.name, i)));
};

voiceSelect.addEventListener("change", () => {
    speech.voice = voices[voiceSelect.value];
});

document.querySelector("button").addEventListener("click", () => {
    speech.text = document.querySelector("textarea").value;
    window.speechSynthesis.speak(speech);
});
```

This code sets up the necessary components for the text-to-speech functionality, including creating a `SpeechSynthesisUtterance` object, retrieving the available voices, populating the voice selection dropdown, and handling the button click event to trigger the speech synthesis.

## Demo

Check out the video below to see the Text To Speech Converter in action: 🎥

[https://github.com/user-attachments/assets/08d1881a-78a6-452a-b4ef-845141de423e]




