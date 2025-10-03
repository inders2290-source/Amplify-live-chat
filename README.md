# Amplify Live Chat

A real-time chat application built using **AWS Amplify** and **Next.js**. This project demonstrates how to integrate Amplify’s real-time APIs to build a live chat system that synchronizes messages between users instantly.

---

## Features

- Real-time chat with message updates pushed to all connected clients  
- User authentication managed by AWS Amplify (Cognito)  
- Simple, clean UI for chatting  
- Next.js pages and API routes  
- Amplify GraphQL subscriptions for live updates  

---

## Tech Stack

- **Frontend / Backend:** Next.js  
- **Realtime / Backend as a Service:** AWS Amplify (GraphQL, AppSync, Cognito)  
- **Authentication:** AWS Cognito via Amplify  
- **Subscriptions / Real-time:** GraphQL subscriptions through Amplify  

---

## Project Structure

```

amplify-live-chat/
├── pages/                      # Next.js pages (chat, login, etc.)
├── components/                 # React components (ChatBox, Message, etc.)
├── lib/                        # Amplify configuration & helper functions
├── styles/                     # CSS / styling files
├── amplify/                    # Amplify backend directory (auto-generated)
│   └── backend/                # Amplify stack definitions
├── .env                        # Environment variables (not committed)
├── README.md
├── package.json
└── next.config.js

````

---

## Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/jarrodwatts/amplify-live-chat.git
cd amplify-live-chat
````

### 2. Install dependencies

```bash
npm install
```

### 3. Configure Amplify

Create a `.env.local` file (or `.env`) in the root with required Amplify configuration values:

```env
NEXT_PUBLIC_AWS_PROJECT_REGION=your_amplify_region
NEXT_PUBLIC_AWS_COGNITO_REGION=your_region
NEXT_PUBLIC_AWS_USER_POOL_ID=your_user_pool_id
NEXT_PUBLIC_AWS_USER_POOL_WEB_CLIENT_ID=your_client_id
NEXT_PUBLIC_GRAPHQL_ENDPOINT=your_graphql_endpoint
NEXT_PUBLIC_GRAPHQL_SUBSCRIPTION_ENDPOINT=your_subscription_endpoint
```

Additionally, you might need to pull or configure the Amplify backend:

```bash
amplify pull
# or if not initialized, run:
amplify init
amplify push
```

### 4. Run the development server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

---

## How It Works (High-Level Flow)

1. User logs in via Amplify Auth (Cognito)
2. On the chat page, the client sends messages via GraphQL mutations
3. GraphQL subscriptions push new messages to all connected clients in real time
4. The UI component listens for subscription events and updates the chat feed automatically

---

## Future Enhancements

* Add user presence indicators (online/offline)
* Support multiple chat rooms / channels
* Persist message history with paging / infinite scroll
* Upload attachments (images, files)
* Dark mode / theming
* Better error handling and validation

---

