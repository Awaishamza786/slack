# Slack

## Description

This project aims to provide a comprehensive and user-friendly messaging platform named "Slack" that allows users to communicate efficiently within workspaces. It supports user registration, login, workspace creation, and messaging features. The messaging system utilizes Redis to store and retrieve messages efficiently. Messages are first fetched from Redis, excluding the messages in Redis, and if the number of sent messages exceeds 10, the messages are stored in the database. If there's a failure during message delivery, the message is temporarily saved in Redis for a subsequent attempt. Once all sent messages are stored in the database, the "all messages" object is cleared, and all message events are triggered, updating the message records in the "all messages" object.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [License](#license)

## Installation

To get started with the project, follow these steps:

```bash
# Clone the repository
git clone https://github.com/Awaishamza786/slack.git

# Navigate to the project directory
cd slack

# Install dependencies
pnpm install

# Run the application
pnpm run dev
```

## Usage

To use the Slack application, you need to have the server up and running after installation. Once the application is running, you can access the API routes to register, log in, create workspaces, and send messages to other users.

## API Documentation

### User Routes

#### Login

- **Route:** POST /api/user/login
- **Description:** Logs in a user.
- **Request Body:**
  - email: User's email address.
  - password: User's password.
- **Response:**
  - Success: Returns the user's ID, email, role, and authentication token.
  - Error: Returns an error message if the login fails.

#### Register

- **Route:** POST /api/user/register
- **Description:** Registers a new user.
- **Request Body:**
  - name: User's name.
  - email: User's email address.
  - password: User's password.
- **Response:**
  - Success: Returns the newly created user's ID and email.
  - Error: Returns an error message if the registration fails.

### Workspace Routes

#### Create Workspace

- **Route:** POST /api/workspace/create
- **Description:** Creates a new workspace.
- **Request Body:**
  - w_name: Workspace name.
  - token: User authentication token.
- **Response:**
  - Success: Returns the created workspace ID, name, and other details.
  - Error: Returns an error message if the creation fails.

### Message Routes

#### Send Message

- **Route:** POST /api/message/send
- **Description:** Sends a message to a user.
- **Request Body:**
  - to: User ID to send the message to.
  - message: The message content.
- **Response:**
  - Success: Returns a success message if the message is sent.
  - Error: Returns an error message if the sending fails.




## Contributing

Contributions to this project are welcome. If you find any issues or have suggestions for improvements, please feel free to submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE). For detailed information, please refer to the [License](LICENSE) file.

For further details, contact through email awaishamza579@gmail.com.
