# Wrike-Monitask Integration

This project integrates Wrike, Monitask, and Time Doctor to synchronize tasks, projects, and time tracking data between these platforms.

## Features

- **Wrike Webhook Integration**: Listens for task updates in Wrike and triggers corresponding actions.
- **Monitask Integration**: Creates and manages projects and tasks in Monitask based on Wrike updates.
- **Time Doctor Integration**: Tracks time spent on tasks and synchronizes it with Wrike.
- **MongoDB Storage**: Stores mappings between Wrike, Monitask, and Time Doctor entities.
- **Token Management**: Automatically refreshes and manages API tokens for Monitask and Time Doctor.
- **Scheduler**: Periodically updates Time Doctor tokens using a cron job.

## Prerequisites

- Node.js (v14 or higher)
- MongoDB
- Wrike, Monitask, and Time Doctor API credentials

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/wrike-monitask.git
   cd wrike-monitask
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Configure environment variables:
   - Copy `.env.sample` to `.env`:
     ```bash
     cp .env.sample .env
     ```
   - Fill in the required values in the `.env` file.

4. Start the application:
   ```bash
   npm start
   ```

## Project Structure

```
wrike_monitask/
├── .env                # Environment variables
├── .env.sample         # Sample environment variables
├── .gitignore          # Git ignore file
├── index.js            # Application entry point
├── notes.txt           # Development notes
├── package.json        # Project dependencies and scripts
├── README.md           # Project documentation
├── config/             # Configuration files
│   ├── db.js           # MongoDB connection
│   └── index.js        # Application configuration
├── controllers/        # Controller logic
│   └── wrikeMonitaskController.js
├── models/             # MongoDB models
│   ├── project_map.js
│   ├── task.js
│   ├── token.js
│   └── user_wrike_monitask.js
├── routes/             # API routes
│   ├── index.js
│   └── wrikeRoutes.js
├── services/           # Business logic
│   ├── monitaskService.js
│   ├── timeDocService.js
│   └── wrikeService.js
└── utils/              # Utility functions
    ├── helpers.js
    ├── schelduler.js
    └── tokenManager.js
```

## Key Features and Files

- **Wrike Webhook**: Handled in `wrikeMonitaskController.js` to process task updates.
- **Monitask Service**: Implements project and task management in `monitaskService.js`.
- **Time Doctor Service**: Manages time tracking and task synchronization in `timeDocService.js`.
- **Token Management**: Refreshes API tokens in `tokenManager.js`.
- **Scheduler**: Periodically updates tokens using `schelduler.js`.

## API Endpoints

### Health Check
- **GET** `/health`
  - Returns `200 OK` if the service is running.

### Wrike Webhook
- **POST** `/wrike/webhook`
  - Handles task updates from Wrike.

## Development Notes

Refer to `notes.txt` for additional development insights.

## License

This project is licensed under the MIT License.
# Wrike-MoniTask-Integration
