# Cura-AI-Agent

## Overview
The 3-in-1 AI Agent is an intelligent web application designed to provide comprehensive support, manage community engagement, and implement a credit & reward system. Leveraging **Laravel**, **OpenAI**, and **GaiaNet APIs**, this application offers seamless interactions, dynamic community management, and incentivizes user participation through a robust reward system.

## Features

### Support Agent
- **Chat Interface:** Engage in real-time conversations with the AI Support Agent.
- **AI Responses:** Receive intelligent, context-aware answers powered by OpenAI.
- **Feedback Mechanism:** Rate AI responses to facilitate continuous learning.

### Autonomous Community Manager
- **Community Dashboard:** Monitor user engagement and manage community interactions.
- **Content Moderation:** Approve or reject flagged content to maintain community standards.
- **Event Management:** Create and manage community events.

### Credit & Reward System
- **Credits Overview:** Track earned credits through participation and contributions.
- **Reward Redemption:** Redeem credits for exclusive rewards.
- **Transaction History:** View detailed transaction logs for transparency.

## Installation

### Prerequisites
- PHP >= 8.0
- Composer
- Node.js and NPM
- MySQL or another supported database

### Steps
1. **Clone the Repository:**
    ```bash
    git clone https://github.com/yourusername/3-in-1-ai-agent.git
    cd 3-in-1-ai-agent
    ```

2. **Install Dependencies:**
    ```bash
    composer install
    npm install
    npm run dev
    ```

3. **Configure Environment Variables:**
    - Duplicate `.env.example` to `.env` and update the following variables:
      ```
      APP_NAME=3-in-1 AI Agent
      APP_ENV=local
      APP_KEY=base64:your_generated_key
      APP_DEBUG=true
      APP_URL=http://localhost

      LOG_CHANNEL=stack

      DB_CONNECTION=mysql
      DB_HOST=127.0.0.1
      DB_PORT=3306
      DB_DATABASE=your_database
      DB_USERNAME=your_username
      DB_PASSWORD=your_password

      GAIANET_BASE_URL=https://api.gaianet.ai
      GAIANET_API_KEY=your_gaianet_api_key
      OPENAI_API_KEY=your_openai_api_key
      ```

4. **Run Migrations and Seeders:**
    ```bash
    php artisan migrate
    php artisan db:seed --class=RewardSeeder
    ```

5. **Start the Development Server:**
    ```bash
    php artisan serve
    ```

## Deployment

Follow the deployment steps outlined in the [Deployment Guide](#deploying-your-web-application).

## API Documentation

### Authentication
- **POST /api/login**
  - **Body:**
    ```json
    {
        "email": "user@example.com",
        "password": "password123"
    }
    ```
  - **Response:**
    ```json
    {
        "token": "your_generated_token"
    }
    ```

### Support Queries
- **POST /api/support/query**
  - **Headers:** `Authorization: Bearer YOUR_TOKEN`
  - **Body:**
    ```json
    {
        "user_id": 1,
        "query": "How do I integrate with GaiaNet APIs?"
    }
    ```
  - **Response:**
    ```json
    {
        "query_id": 1,
        "response": "AI-generated answer."
    }
    ```

### Submit Feedback
- **POST /api/support/feedback**
  - **Headers:** `Authorization: Bearer YOUR_TOKEN`
  - **Body:**
    ```json
    {
        "query_id": 1,
        "is_helpful": false,
        "comments": "The response was unclear."
    }
    ```
  - **Response:**
    ```json
    {
        "message": "Feedback submitted successfully"
    }
    ```

### Redeem Rewards
- **POST /api/credits/redeem**
  - **Headers:** `Authorization: Bearer YOUR_TOKEN`
  - **Body:**
    ```json
    {
        "reward_id": 1
    }
    ```
  - **Response:**
    ```json
    {
        "message": "Reward redeemed successfully!"
    }
    ```

## Usage Guide

1. **Register an Account:**
   - Navigate to the registration page and create a new account.

2. **Login:**
   - Access the login page and authenticate using your credentials.

3. **Access Support Desk:**
   - Navigate to the **Support** section to chat with the AI Support Agent.

4. **Manage Community:**
   - Navigate to the **Community** section to monitor engagement and moderate content.

5. **Track and Redeem Rewards:**
   - Navigate to the **Credits & Rewards** section to view your credits and redeem rewards.

## Technologies Used
- **Laravel:** PHP framework for backend development.
- **Laravel Sanctum:** API authentication.
- **OpenAI API:** Natural language processing and AI responses.
- **GaiaNet API:** Integration for submission and improvements.
- **Bootstrap:** Frontend styling and responsiveness.
- **JavaScript:** Handling frontend interactions and API requests.
- **Chart.js:** Data visualization for analytics.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any enhancements or bug fixes.

## License

[MIT](LICENSE)

