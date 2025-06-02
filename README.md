AI Story Generator
The AI Story Generator is a Python-based tool that creates illustrated and narrated children's stories from a simple prompt. It combines the power of generative text models, AI-generated images, and text-to-speech synthesis to produce complete storybooks in PDF and video formats.

Features
Automatically generates story text using OpenAI's GPT models

Creates corresponding images for each story segment

Converts text to speech using either Google TTS or AWS Polly

Compiles stories into PDF and MP4 video formats

Extracts keywords using KeyBERT for metadata or tagging

Installation
Clone this repository:

bash

git clone https://github.com/prasadmore03/ai-story-generator.git
cd ai-story-generator
(Optional) Create and activate a virtual environment:

lua

conda create -n storyenv python=3.10
conda activate storyenv
Install the required packages:

nginx

pip install -r requirements.txt
Setting Up Credentials
Create a credentials/ directory and add the following files:

OpenAI credentials (openai-creds.json)

json

{
  "api_key": "your-openai-api-key",
  "organization": "your-org-id"
}
AWS Polly credentials (polly-creds.json) (optional if not using Polly)

json

{
  "aws_access_key_id": "your-key-id",
  "aws_secret_access_key": "your-secret-access-key",
  "region_name": "your-region"
}
Usage
To generate a new story using a prompt:

css

py -3.10 main.py --prompt "The story of Rabbit and Tortoise"
To load and regenerate a previously saved story using a pickle file:

css

py -3.10 main.py --pickle path/to/story_content.pickle
Additional options:

--size: Choose from 256, 512, or 1024 (default is 256)

--polly: Use AWS Polly for text-to-speech (optional)

Output
Each story is saved under the _stories/ directory with the following structure:

css

_stories/
 └── timestamp-story-title/
     ├── audio/
     ├── images/
     ├── pages/
     ├── story_content.pickle
     ├── story.pdf
     └── story.mp4
Project Structure
bash

.
├── main.py
├── data_models.py
├── story_manager.py
├── story_provider.py
├── requirements.txt
├── credentials/
├── generators/
├── processors/
├── util/
└── _stories/        # Automatically generated output folder
License
This project is open-source and available under the MIT License.

