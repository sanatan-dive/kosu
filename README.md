# Next.js AI Agent Application
This is a [Next.js](https://nextjs.org) project that integrates with Hugging Face's AI models for various AI agent functionalities.

## Features

- **Talent Scout**: Matches job requirements with candidate profiles using zero-shot classification
- **Skill Verifier**: Verifies skills and credentials using question answering models
- **Interview Prep**: Generates interview questions and feedback using text generation models
- **Resume Analyzer**: Extracts skills, experience, and education from resumes using sentiment analysis

## Hugging Face API Integration

This project uses Hugging Face's API for AI model inference. To use the AI features, you need to:

1. Create a Hugging Face account at [huggingface.co](https://huggingface.co)
2. Generate an API key from your [Hugging Face settings](https://huggingface.co/settings/tokens)
3. Add your API key to the `.env.local` file:

```
NEXT_PUBLIC_HUGGING_FACE_API_KEY=your_api_key_here
```

### AI Models Used

The project uses the following models by default:
- **Talent Scout**: facebook/bart-large-mnli (Zero-shot classification model for job matching)
- **Skill Verifier**: deepset/roberta-base-squad2 (Question answering model for skill verification)
- **Interview Prep**: gpt2 (Text generation model for interview preparation)
- **Resume Analyzer**: distilbert-base-uncased-finetuned-sst-2-english (Sentiment analysis model for resume analysis)

You can customize these models by changing the environment variables in `.env.local`:

```
NEXT_PUBLIC_HF_TALENT_SCOUT_MODEL=facebook/bart-large-mnli
NEXT_PUBLIC_HF_SKILL_VERIFIER_MODEL=deepset/roberta-base-squad2
NEXT_PUBLIC_HF_INTERVIEW_PREP_MODEL=gpt2
NEXT_PUBLIC_HF_RESUME_ANALYZER_MODEL=distilbert-base-uncased-finetuned-sst-2-english
```

## Recent Updates

### API Integration
- Implemented real Hugging Face API endpoints instead of mock endpoints
- Added environment variable configuration for API keys and model selection
- Improved error handling with retry logic for model loading and rate limiting
- Added fallback mechanisms for when AI services are unavailable

### TypeScript Configuration
- Modified TypeScript configuration to be less strict for development
- Updated ESLint configuration to disable certain rules for better developer experience
- Fixed type compatibility issues between AIAgent and Agent interfaces

### Code Improvements
- Enhanced the queryHuggingFaceModel function with better retry logic
- Added proper type definitions for AI agents and their responses
- Improved error handling throughout the application

## Getting Started

First, install the dependencies:

```bash
npm install
# or
yarn install
# or
pnpm install
# or
bun install
```

Then, create a `.env.local` file with your Hugging Face API key:

```
NEXT_PUBLIC_HUGGING_FACE_API_KEY=your_api_key_here
```

Finally, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

To learn more about Hugging Face:

- [Hugging Face Documentation](https://huggingface.co/docs) - learn about Hugging Face models and APIs.
- [Inference API](https://huggingface.co/docs/api-inference/index) - documentation for the Inference API used in this project.
