# AI Agent System for Contractors and Real Estate Agents

This project implements an AI-powered system that helps contractors and real estate agents verify phone calls and manage contact information automatically. The system uses voice recognition, AI verification, and Google Sheets integration to streamline the contact management process.

## Features

- **Phone Call Verification**
  - AI-powered voice recognition
  - Automated identity verification
  - Multi-step verification process
  - Retry mechanism for failed verifications

- **Contact Information Management**
  - Automatic collection of:
    - Name
    - Email
    - Phone Number
    - Address
  - Google Sheets integration
  - Real-time data updates
  - Contact history tracking

- **AI Integration**
  - OpenAI-powered verification analysis
  - Confidence scoring
  - Fraud detection
  - Natural language processing

- **Voice Interface**
  - Text-to-speech capabilities
  - Speech recognition
  - Customizable voice settings
  - Multi-language support

## Prerequisites

- Python 3.8 or higher
- Twilio account and phone number
- OpenAI API key
- Google Cloud account with Sheets API enabled
- Google Sheets document

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd real-state-ai-agent
```

2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
Create a `.env` file in the root directory with the following variables:
```
# Twilio Configuration
TWILIO_ACCOUNT_SID=your_twilio_account_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_PHONE_NUMBER=your_twilio_phone_number

# OpenAI Configuration
OPENAI_API_KEY=your_openai_api_key

# Google Sheets Configuration
GOOGLE_CREDENTIALS_FILE=credentials.json
SPREADSHEET_ID=your_google_sheet_id

# Application Configuration
PORT=5000
```

4. Set up Google Sheets API:
   - Go to [Google Cloud Console](https://console.cloud.google.com)
   - Create a new project
   - Enable Google Sheets API
   - Create credentials (OAuth 2.0 Client ID)
   - Download the credentials JSON file
   - Save it as `credentials.json` in the project root directory

5. Set up Twilio:
   - Create a [Twilio account](https://www.twilio.com)
   - Get your Account SID and Auth Token
   - Set up a phone number for the AI agent
   - Update the `.env` file with your Twilio credentials

6. Get OpenAI API key:
   - Go to [OpenAI Platform](https://platform.openai.com)
   - Create an account or sign in
   - Generate an API key
   - Update the `.env` file with your OpenAI API key

## Project Structure

```
real-state-ai-agent/
├── src/
│   ├── agents/
│   │   ├── __init__.py
│   │   ├── contractor_agent.py
│   │   └── real_estate_agent.py
│   ├── utils/
│   │   ├── __init__.py
│   │   ├── voice_handler.py
│   │   ├── google_sheets.py
│   │   └── verification.py
│   └── main.py
├── config/
│   └── config.py
├── requirements.txt
├── run.py
└── README.md
```

## Usage

1. Start the application:
```bash
python run.py
```

2. The system will:
   - Listen for incoming calls on the configured Twilio number
   - Verify caller identity using AI
   - Collect and store contact information
   - Update Google Sheets automatically

3. API Endpoints:
   - `/voice` (POST): Handle incoming voice calls
   - `/contacts` (GET): Get all verified contacts
   - `/call` (POST): Make outbound calls

## Configuration

### Voice Settings
- Language: English (US)
- Gender: Female
- Speed: 1.0x

### Verification Settings
- Maximum retries: 3
- Call timeout: 300 seconds (5 minutes)
- Verification questions:
  1. Full name confirmation
  2. Email address
  3. Phone number
  4. Current address

### Google Sheets
- Automatic column headers
- Timestamp tracking
- Verification status
- Agent type tracking

## Error Handling

The system includes comprehensive error handling:
- Graceful handling of missing credentials
- Automatic retries for failed verifications
- Detailed error logging
- Fallback mechanisms for service failures

## Security

- All sensitive data is stored securely
- API keys and credentials are managed through environment variables
- Data transmission is encrypted
- Input validation and sanitization
- Rate limiting and request validation

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

MIT License

## Support

For support, please open an issue in the repository or contact the maintainers. 