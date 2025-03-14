# KOSU
## Features

- **Talent Scout**: Matches job requirements with candidate profiles using zero-shot classification
- **Skill Verifier**: Verifies skills and credentials using question answering models
- **Interview Prep**: Generates interview questions and feedback using text generation models
- **Resume Analyzer**: Extracts skills, experience, and education from resumes using sentiment analysis
- **PDF Processing**: Browser-compatible PDF text extraction for resume analysis
- **Hackathon Events**: Browse, register, and participate in blockchain hackathons with wallet integration
- **NFT Minting**: Mint exclusive KOSU NFTs with unique attributes and rarity levels using Petra Wallet
- **Hackathon Teammate Finder**: Helps hackathon participants find teammates based on skill compatibility and experience using AI-powered matching

## Hugging Face API Integration

This project uses Hugging Face's API for AI model inference. To use the AI features, you need to:

1. Create a Hugging Face account at [huggingface.co](https://huggingface.co)
2. Generate an API key from your [Hugging Face settings](https://huggingface.co/settings/tokens)
3. Add your API key to the `.env.local` file:

```plaintext
NEXT_PUBLIC_HUGGING_FACE_API_KEY=your_api_key_here
```

### AI Models Used

The project uses the following models by default:
- **Talent Scout**: facebook/bart-large-mnli (Zero-shot classification model for job matching)
- **Skill Verifier**: deepset/roberta-base-squad2 (Question answering model for skill verification)
- **Interview Prep**: gpt2 (Text generation model for interview preparation)
- **Resume Analyzer**: distilbert-base-uncased-finetuned-sst-2-english (Sentiment analysis model for resume analysis)
- **Skill Based Matching**: all-MiniLM-L6-v2

You can customize these models by changing the environment variables in `.env.local`:

```plaintext
NEXT_PUBLIC_HF_TALENT_SCOUT_MODEL=facebook/bart-large-mnli
NEXT_PUBLIC_HF_SKILL_VERIFIER_MODEL=deepset/roberta-base-squad2
NEXT_PUBLIC_HF_INTERVIEW_PREP_MODEL=gpt2
NEXT_PUBLIC_HF_RESUME_ANALYZER_MODEL=distilbert-base-uncased-finetuned-sst-2-english
```

## Recent Updates

### NFT Minting Integration
- Added NFT minting functionality with Petra Wallet integration
- Implemented a simulated minting process for testing and demonstration
- Created a visually appealing NFT display with attributes and rarity levels
- Added wallet connection status monitoring and testing tools
- Implemented local storage for persisting NFT ownership information

### Hackathon Events Platform
- Added a comprehensive events page to browse upcoming hackathons
- Implemented event detail pages with registration functionality
- Created a registration system with wallet authentication
- Added dashboard integration to display registered hackathons
- Implemented responsive design for all event-related pages

### PDF Processing Improvements
- Implemented browser-compatible PDF text extraction using PDF.js
- Added robust error handling for various PDF issues (password protection, scanned documents)
- Created a debug mode to help troubleshoot PDF extraction problems
- Added a sample resume template for users who have trouble with PDF uploads
- Improved user guidance with specific error messages and solutions

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
- Created dedicated service for PDF processing with browser compatibility

## Hackathon Teammate Finder

### Overview

This feature helps hackathon participants find potential teammates based on skill compatibility and experience using AI-powered matching.

### How It Works

The teammate finder uses the `sentence-transformers/all-MiniLM-L6-v2` model to create embeddings of user skills and experience descriptions. It then calculates the similarity between users to find the most compatible potential teammates.

#### Technical Implementation

1. **Embedding Generation**: The system uses the `@xenova/transformers` library to generate embeddings for user profiles based on their skills and experience.

2. **Similarity Calculation**: Cosine similarity is used to measure how similar two user profiles are.

3. **Matching Algorithm**: Users are ranked by similarity score, with the most similar profiles shown first.

### How to Use

1. **Access the Feature**: Click on the team icon (👥) on any hackathon card to open the teammate finder modal.

2. **Select Skills**: Choose the skills you're looking for in potential teammates. These can be different from your own skills if you're looking for complementary team members.

3. **Describe Experience (Optional)**: Add a brief description of your experience level and what you're looking for in teammates.

4. **Find Matches**: Click "Find Teammates" to see a list of potential teammates ranked by compatibility.

5. **Connect with Matches**: View the profiles of potential teammates and reach out to them to form a team.

### Requirements

- You must connect your wallet to use this feature.
- Your profile should have skills listed for the best matching results.

### Privacy

- Your skills and experience data are only used for matching purposes and are not shared with third parties.
- The matching process happens on the server, and embeddings are not stored permanently.

### Dependencies

This feature uses:
- `@xenova/transformers`: For generating embeddings
- MongoDB: For storing and retrieving user profiles
- Next.js API routes: For handling the matching logic

### Future Improvements

- Direct messaging between potential teammates
- Team formation and management
- Skill verification and endorsements
- Advanced filtering options (location, availability, etc.)

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

```plaintext
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

## PDF Processing

The application uses PDF.js for browser-compatible PDF text extraction. This allows users to upload their resumes in PDF format without requiring server-side processing.

Key features:
- Client-side PDF text extraction
- Support for both PDF and TXT file formats
- Detailed error messages for common PDF issues
- Debug mode for troubleshooting extraction problems
- Sample resume template for users who have trouble with their PDFs

## Hackathon Events

The platform includes a comprehensive hackathon events system that allows users to:

- Browse upcoming blockchain hackathons with detailed information
- View event details including dates, locations, prizes, and requirements
- Register for events using wallet authentication (Petra Wallet)
- Track registered hackathons in the user dashboard
- Receive NFT badges and credentials for participation and achievements

Key features:
- Responsive design for all event pages
- Wallet integration for secure registration
- Detailed event information with judging criteria
- Registration form with skill and experience tracking
- Dashboard integration for registered events

## NFT Minting

The platform includes an NFT minting system that allows users to mint exclusive KOSU NFTs:

- Mint unique KOSU Genesis NFTs with random attributes and rarity levels
- Connect with Petra Wallet for blockchain interaction
- View detailed NFT information including attributes and rarity
- Track minted NFTs in the user dashboard
- Test wallet connection and contract functions

Key features:
- Simulated minting process for testing and demonstration
- Realistic wallet interaction with approval/rejection flows
- Random NFT generation with unique attributes (Power, Intelligence, Charisma, Luck)
- Five rarity levels (Common, Uncommon, Rare, Epic, Legendary)
- Visual attribute display with progress bars
- Wallet connection status monitoring
- Local storage for persisting NFT ownership information

### Using the NFT Minter

1. Connect your Petra Wallet by clicking "Log in" in the header
2. Navigate to the Dashboard page
3. Click "Mint KOSU NFT" to start the minting process
4. Approve the transaction in the wallet popup
5. View your minted NFT with its unique attributes and rarity level

For testing purposes, the minting process is simulated and doesn't require an actual blockchain transaction. The NFT data is stored locally in your browser's localStorage.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

To learn more about Hugging Face:

- [Hugging Face Documentation](https://huggingface.co/docs) - learn about Hugging Face models and APIs.
- [Inference API](https://huggingface.co/docs/api-inference/index) - documentation for the Inference API used in this project.

To learn more about PDF.js:

- [PDF.js Documentation](https://mozilla.github.io/pdf.js/) - learn about the PDF.js library used for PDF text extraction.
- [PDF.js GitHub](https://github.com/mozilla/pdf.js) - the source code for PDF.js

---
