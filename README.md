# Movie Ticket Booking Bot

This is a Telegram bot that helps users select movies, theaters, and showtimes to book tickets. It provides options to browse available movies, theaters, and times and confirm their selection. The bot uses the `python-telegram-bot` library to handle user interactions.

## Features

- **Browse Movies**: Users can select from a list of movies and theaters.
- **Theater Selection**: Users can choose theaters based on selected movies and times.
- **Time Selection**: Users can browse available showtimes.
- **Interactive Booking Process**: Users select movies, theaters, and times through inline buttons, making the booking process easy.
- **Confirmation**: Users receive a booking confirmation with their selected movie, theater, and showtime.

## Files and Structure

### 1. `bot1.py`

This file initializes the bot and contains the main handlers for interacting with users. It integrates the movie, theater, and time selection modules.

**Key functionality:**
- Initializes the bot using `python-telegram-bot`.
- Sets up handlers for commands like `/start` and `/movie`, and callback queries for interactive messages.
- Links to the `movie_module.py`, `theater_module.py`, and `time_module.py` for movie, theater, and time selection.

### 2. `movie_module.py`

This module handles movie-related interactions. Users can select movies and get a list of available theaters and showtimes based on their choice.

**Key functionality:**
- Shows a list of movies to the user.
- After a movie is selected, the user can choose between theaters or times.
- Dynamically generates the next set of options based on the selected movie.

### 3. `theater_module.py`

This module manages theater selection. It allows users to browse theaters and view available movies and showtimes at each theater.

**Key functionality:**
- Displays a list of theaters to the user.
- Users can select a theater, and the bot shows the available movies or times for that theater.
- Dynamically generates available movies and times based on the selected theater.

### 4. `time_module.py`

This module is responsible for managing time selection. Users can select available times for specific theaters and movies.

**Key functionality:**
- Lists available times for the selected movie or theater.
- Allows users to confirm their selected showtime, movie, and theater.
- Finalizes the booking process.

## Installation

To run the bot locally, follow these steps:

### Prerequisites

- Python 3.7+
- Install `python-telegram-bot` via pip:

  ```bash
  pip install python-telegram-bot
  ```

### Clone the Repository

```bash
git clone https://github.com/your-username/movie-ticket-bot.git
cd movie-ticket-bot
```

### Setup Your Telegram Bot

1. Get your bot token from [BotFather](https://core.telegram.org/bots#botfather).
2. Replace `YOUR_BOT_TOKEN` in `bot1.py` with your token.

```python
application = ApplicationBuilder().token("YOUR_BOT_TOKEN").build()
```

### Run the Bot

```bash
python bot1.py
```

### Available Commands

- `/start`: Start interacting with the bot.
- `/movie`: Browse movies and start the booking process.
- `/theater`: Browse theaters and their available movies.

## How It Works

1. **Start the Bot**: Users can start by typing `/start`. 
2. **Movie Selection**: Once they select `/movie`, the bot shows a list of available movies. After selecting a movie, users can choose a theater or time.
3. **Theater and Time Selection**: The user is guided through the theater and time selection, showing available options based on their previous choices.
4. **Confirmation**: Once a theater, movie, and time are selected, the bot confirms the booking details.

## Example Usage

```plaintext
User: /start
Bot: Welcome to the Movie Ticket Booking Bot!

User: /movie
Bot: Select a Movie: [Movie A] [Movie B] [Movie C]

User: Movie A
Bot: Selected Movie: Movie A. Choose an option:
     [THEATER] [TIME]

User: Theater
Bot: Select a theater: [Theater 1] [Theater 2]
```

## License

This project is licensed under the MIT License.

---

