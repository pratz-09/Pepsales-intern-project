# Notification Service

A real-time notification system built with React, Socket.IO, and Express that supports email, SMS, and in-app notifications.

## Features

- 🔔 Multiple notification types (Email, SMS, In-app)
- 🔄 Real-time updates using WebSocket
- 📊 Dashboard with notification analytics
- 🔍 Searchable notification center
- 🔁 Automatic retry mechanism for failed notifications
- 📱 Responsive design
- 🎯 Status tracking (queued, delivered, failed)

## Tech Stack

- Frontend:
  - React 18
  - TypeScript
  - Tailwind CSS
  - Socket.IO Client
  - Lucide React (icons)
  - React Router

- Backend:
  - Express
  - Socket.IO
  - UUID for unique identifiers
  - Date-fns for date formatting

## Prerequisites

- Node.js 18+ and npm

## Setup Instructions

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server and backend:
   ```bash
   npm run dev:all
   ```

   This will start:
   - Frontend at http://localhost:5173
   - Backend at http://localhost:3000

## Project Structure

```
├── server/             # Backend server code
│   └── index.js       # Express server & Socket.IO setup
├── src/
│   ├── components/    # React components
│   ├── context/      # React context providers
│   ├── pages/        # Page components
│   └── main.tsx      # Application entry point
```

## API Endpoints

- `POST /notifications`
  - Create a new notification
  - Body: `{ userId, type, title, message }`

- `GET /users/{id}/notifications`
  - Get all notifications for a user

- `PUT /notifications/{id}/read`
  - Mark a notification as read

## Assumptions

1. Authentication:
   - Basic user system with hardcoded users for demo
   - In production, would implement proper authentication

2. Notification Delivery:
   - Simulated delivery with 80% success rate
   - In production, would integrate with actual email/SMS providers

3. Data Persistence:
   - In-memory storage for demo
   - In production, would use a proper database

4. Queue System:
   - Simple in-memory queue implementation
   - In production, would use a proper message queue (RabbitMQ/Kafka)

## Production Considerations

1. Database Integration:
   - Add proper database for persistent storage
   - Implement data migrations

2. Authentication & Authorization:
   - Implement user authentication
   - Add role-based access control

3. External Services:
   - Integrate email service (e.g., SendGrid)
   - Integrate SMS service (e.g., Twilio)

4. Monitoring & Logging:
   - Add error tracking
   - Implement logging system
   - Add performance monitoring

5. Security:
   - Add rate limiting
   - Implement input validation
   - Add CSRF protection

## Live Demo

The application is deployed at: [https://incandescent-dragon-425526.netlify.app](https://notification-service-prateek1234.netlify.app/)

Note: The backend needs to be running locally as it's not deployed.
