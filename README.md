# AgriLM: Nigerian Agricultural Advisor

AgriLM is an agricultural decision-support application designed to help farmers and agricultural stakeholders access reliable, contextual recommendations using AI and a local knowledge base. The project combines a retrieval-augmented generation (RAG) approach, voice input support, and plant disease image classification to provide an intelligent agricultural assistant.

## Overview

This project was developed to support Nigerian agriculture by addressing common farming needs such as:

- crop and soil guidance
- fertilizer recommendations
- pest and disease information
- irrigation and storage advice
- market-related agricultural insights
- plant disease identification from uploaded images

AgriLM is built to work with a local knowledge base and an LLM backend, enabling offline or semi-offline agricultural assistance without requiring internet connectivity for core responses.

## Key Features

- AI-powered agricultural advisory assistant
- retrieval-augmented knowledge base for farming guidance
- voice input transcription via Whisper
- plant disease classification from image uploads
- farmer-friendly web interface
- support for Nigerian agricultural context and crop information
- modular design for future expansion and customization

## Application Capabilities

### Agricultural Advisory
The system answers common questions about:

- crop selection
- soil conditions
- fertilizer use
- protected cultivation practices
- irrigation management
- storage and post-harvest handling
- livestock support and farm operations

### Disease Detection
The model supports plant image classification and provides recommendations for likely disease categories with confidence estimates.

### Voice Interaction
The application accepts voice input and transcribes it before processing the farmer's question.

## Project Structure

```text
.
├── README.md
├── agrilm.py
├── baseline.py
├── baseline_3b.py
├── image_classifier.py
├── index.html
├── preprocessor.py
├── rag.py
├── start.sh
├── system_prompt.txt
├── web_app.py
├── .gitignore
├── data/
│   └── PlantVillage
├── knowledge/
│   ├── extension_services.txt
│   ├── irrigation.txt
│   ├── livestock_basics.txt
│   ├── market_prices.txt
│   ├── nigerian_crops.txt
│   ├── pest_disease.txt
│   ├── soil_and_fertilizer.txt
│   └── storage_processing.txt
├── anaconda_projects/
└── ...
```

## Technologies Used

- Python
- Flask-like HTTP server implementation for the web interface
- Jupyter notebooks for experimentation
- ONNX-based plant disease classification
- Whisper-based speech transcription
- Retrieval-augmented generation (RAG)
- Local agricultural knowledge base

## Requirements

Before running the project, install the required Python dependencies:

```bash
pip install requests numpy pandas matplotlib
```

Additional system requirements may include:

- Python 3.10+
- ffmpeg for audio conversion
- a running local LLM backend on port 8080
- Whisper model files for transcription
- trained image classification model assets

## Setup

1. Clone the repository:

```bash
git clone https://github.com/emmyfly/agricultural-model.git
cd agricultural-model
```

2. Ensure the local knowledge files in the `knowledge/` folder are present.

3. Prepare the AI model backend and ensure it is running locally at:

```text
http://localhost:8080/v1/chat/completions
```

4. Start the application:

```bash
python web_app.py
```

5. Open the app in a browser at:

```text
http://localhost:5001
```

## Running the Application

The application provides a web interface for:

- asking farming questions
- uploading plant images
- transcribing voice messages
- receiving AI-assisted agricultural guidance

You can also run the terminal version via:

```bash
python agrilm.py
```

## Knowledge Base

The project includes files under `knowledge/` that store agricultural guidance on topics such as:

- crop information
- fertilizer and soil recommendations
- irrigation practices
- pest and disease management
- livestock basics
- market prices
- extension services
- storage and post-harvest systems

## Model Workflow

The application workflow uses a retrieval-based pipeline:

1. the user submits a question or image
2. relevant knowledge is retrieved from the local agricultural documents
3. the question is enriched with contextual information
4. the LLM provides a grounded response
5. the final answer is shown to the user in the interface

## Future Improvements

Planned enhancements include:

- expanding the knowledge base with more region-specific agricultural data
- improving yield prediction and crop recommendation models
- adding more disease classes and stronger classification performance
- integrating mobile-friendly interfaces
- adding support for additional local languages
- improving analytics and reporting features for farmers

## License

This project currently does not include a formal license file. If you plan to publish or distribute it publicly, consider adding an open-source license such as MIT.

## Contact

For questions or collaboration opportunities, contact the project maintainer or update this section with your preferred communication details.

## Notes

AgriLM is designed as a practical agricultural intelligence tool for farmers, researchers, and developers working in AI-driven agricultural support and decision-making.
