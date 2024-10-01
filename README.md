# GuessMaster API Client

This package provides an easy-to-use client for interacting with the [GuessMaster](https://github.com/MeerUzairWasHere/GuessMaster).
It allows you to register users, log in, manage games, submit guesses, access leaderboards, and retrieve current user.

## Installation

You can install this package via npm:

```bash
npm install guessmasterclient
```

## Usage

To use the API client, first import the necessary services:

```javascript
import { AuthService, GameService, GuessService, LeaderboardService, UserService } from 'guessmasterclient';
```

### Authentication Methods

#### 1. Register a New User

```javascript
const registerUser = async () => {
    try {
        const response = await AuthService.RegisterUser({
            name: 'John Doe',
            email: 'john@example.com',
            password: 'password123'
        });
        console.log(response.msg);
    } catch (error) {
        console.error(error);
    }
};
```

#### 2. Log In an Existing User

```javascript
const loginUser = async () => {
    try {
        const response = await AuthService.LoginUser({
            email: 'john@example.com',
            password: 'password123'
        });
        console.log(response.user);
    } catch (error) {
        console.error(error);
    }
};
```

#### 3. Log Out a User

```javascript
const logoutUser = async () => {
    try {
        const response = await AuthService.LogoutUser();
        console.log(response.msg);
    } catch (error) {
        console.error(error);
    }
};
```

### Game Management Methods

#### 1. Create a New Game

```javascript
const createGame = async () => {
    try {
        const response = await GameService.CreateGame({
            difficulty: 'medium'
        });
        console.log(response);
    } catch (error) {
        console.error(error);
    }
};
```

#### 2. Get All Games of the Current User

```javascript
const getAllGames = async () => {
    try {
        const response = await GameService.GetAllGames();
        console.log(response.games);
    } catch (error) {
        console.error(error);
    }
};
```

#### 3. Delete a Game by ID

```javascript
const deleteGame = async (gameId) => {
    try {
        const response = await GameService.DeleteGame(gameId);
        console.log(response.msg);
    } catch (error) {
        console.error(error);
    }
};
```

### Guess Submission Method

#### 1. Submit a Guess for a Game

```javascript
const createGuess = async (gameId, guess) => {
    try {
        const response = await GuessService.CreateGuess(gameId, {
            guess: guess
        });
        console.log(response.result);
    } catch (error) {
        console.error(error);
    }
};
```

### Leaderboard Methods

#### 1. Get the Easy Level Leaderboard

```javascript
const getEasyLeaderboard = async () => {
    try {
        const response = await LeaderboardService.getLeaderboardEasyLevel();
        console.log(response);
    } catch (error) {
        console.error(error);
    }
};
```

#### 2. Get the Medium Level Leaderboard

```javascript
const getMediumLeaderboard = async () => {
    try {
        const response = await LeaderboardService.getLeaderboardMediumLevel();
        console.log(response);
    } catch (error) {
        console.error(error);
    }
};
```

#### 3. Get the Hard Level Leaderboard

```javascript
const getHardLeaderboard = async () => {
    try {
        const response = await LeaderboardService.getLeaderboardHardLevel();
        console.log(response);
    } catch (error) {
        console.error(error);
    }
};
```

### User Profile Method

#### 1. Get the Current User

```javascript
const getCurrentUser = async () => {
    try {
        const response = await UserService.GetCurrentUser();
        console.log(response.user);
    } catch (error) {
        console.error(error);
    }
};
```

## Contributing

If you'd like to contribute, please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License.
