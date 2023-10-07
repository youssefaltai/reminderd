# reminderd

**reminderd** is a simple daemon designed to keep you organized by sending notifications for due reminders.

## Overview

### Features

- **Reminder Notifications**: reminderd periodically checks for due reminders and sends notifications using `dunstify`.
- **Easy-to-Use**: Add, remove, and list reminders using the companion script, **reminderctl**.

### Usage Scenario

The typical use case for **reminderd** is to run it on startup in your `~/.xinitrc` or a similar startup script. Once running, it continuously checks for reminders and displays notifications when they are due.

## Getting Started

### Prerequisites

Before using **reminderd**, ensure you have the following:

- **dunstify**: This tool is used to display notifications. Make sure it is installed and configured on your system.

### Installation

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/reminderd.git
   ```

2. Make the scripts executable:

   ```bash
   cd reminderd
   chmod +x reminderd reminderctl
   ```

3. Move the scripts to a location in your PATH, so you can easily access them:

   ```bash
   sudo mv reminderd reminderctl /usr/local/bin/
   ```

### Usage

#### Adding a Reminder

To add a reminder, use the `reminderctl` script as follows:

```bash
reminderctl add <due> <summary> [body] [icon]
```

- `<due>`: The due date and time for the reminder in a valid date format.
- `<summary>`: A short summary or title for the reminder.
- `[body]`: Optional - Additional details or description of the reminder.
- `[icon]`: Optional - An icon associated with the reminder.

#### Removing a Reminder

To remove a reminder, use the `reminderctl` script as follows:

```bash
reminderctl remove <reminder_id>
```

- `<reminder_id>`: The unique identifier of the reminder you want to remove.

#### Listing Reminders

To list all existing reminders, simply run:

```bash
reminderctl list
```

### Configuration

By default, **reminderd** stores reminders in the `$HOME/.local/share/reminders` directory. You can customize this directory by modifying the `REMINDERS_DIR` variable in both `reminderd` and `reminderctl` scripts.

### Running on Startup

To ensure that **reminderd** runs on startup, add the following line to your `~/.xinitrc` or similar startup script:

```bash
/usr/local/bin/reminderd &
```

This will start **reminderd** in the background, and it will continuously check for due reminders.

## Example

Here's an example of how to use **reminderctl** to add a reminder:

```bash
reminderctl add "2023-12-31 23:59" "New Year's Eve Party" "Don't forget to bring snacks and drinks!" "party-icon.png"
```

This command adds a reminder for a New Year's Eve party, displaying a notification with the specified details and icon when the time comes.

## Contributing

Contributions to this project are welcome! Feel free to open issues, submit pull requests, or share your ideas and suggestions.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to the [dunst](https://dunst-project.org/) project for providing a simple and effective way to display notifications.

---

Enjoy staying organized with **reminderd**! If you have any questions or encounter issues, feel free to [open an issue](https://github.com/yourusername/reminderd/issues).
