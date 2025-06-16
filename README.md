# AI PDF Summarizer

A full-stack application that uses AI to summarize PDF documents. Built with React Native/Expo for the frontend and Node.js/Express for the backend.

## Features

- PDF text extraction
- AI-powered summarization
- Cross-platform mobile support (iOS/Android)
- Secure file handling
- Rate limiting and security measures

## Prerequisites

- Node.js >= 18.0.0
- npm or yarn
- Expo CLI
- OpenAI API key

## Project Structure

```
.
├── app/                 # Frontend React Native/Expo app
├── backend/            # Express.js backend server
├── components/         # Reusable React components
├── constants/          # App constants and configuration
├── hooks/             # Custom React hooks
└── assets/            # Static assets
```

## Setup

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the backend directory with the following variables:
   ```
   PORT=3000
   NODE_ENV=production
   ALLOWED_ORIGINS=https://your-frontend-domain.com
   RATE_LIMIT_WINDOW_MS=900000
   RATE_LIMIT_MAX_REQUESTS=100
   OPENAI_API_KEY=your_openai_api_key
   MAX_FILE_SIZE=10485760
   UPLOAD_DIR=uploads
   LOG_LEVEL=info
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```

### Frontend Setup

1. Install dependencies:
   ```bash
   npm install
   ```

2. Create a `.env` file in the root directory with your configuration:
   ```
   EXPO_PUBLIC_API_URL=http://localhost:3000
   ```

3. Start the development server:
   ```bash
   npm start
   ```

## Production Deployment

### Backend Deployment

1. Build the backend:
   ```bash
   cd backend
   npm install --production
   ```

2. Set up environment variables on your hosting platform (e.g., Heroku, AWS, DigitalOcean)

3. Start the production server:
   ```bash
   npm start
   ```

### Frontend Deployment

1. Build the Expo app:
   ```bash
   expo build:android  # For Android
   expo build:ios     # For iOS
   ```

2. Follow the Expo build instructions to deploy to app stores

## Security Considerations

- All API endpoints are rate-limited
- File uploads are restricted to PDFs only
- CORS is configured to allow only specific origins
- Helmet.js is used for security headers
- File size limits are enforced
- Environment variables are used for sensitive data

## Monitoring and Maintenance

- Health check endpoint available at `/health`
- Morgan logging for request tracking
- Error handling middleware for graceful error responses
- Automatic file cleanup after processing

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
