# Discord Mass Token Reactor

This Python script allows you to add reactions (both standard and custom emojis) to a specific Discord message using multiple accounts (tokens). The bot uses `tls-client` for the session and proxies to avoid rate limits. It supports both standard and custom Discord emojis.

## Features

- **Mass Reaction**: Automatically reacts to a message with multiple Discord tokens.
- **Supports Custom Emojis**: Works with both standard Unicode emojis and custom server emojis.
- **Proxy Support**: Uses proxies to bypass rate limits and make requests appear from different IP addresses.
- **Color-Coded Console Output**: The script provides colorful feedback, indicating success or failure of reactions for each token.

## Requirements

- Python 3.x
- Required Libraries:
  - `tls-client`
  - `colorama`
  - `pystyle`
  - `shutil` (part of Python standard library)

## How to Use

1. **Install Dependencies**:
   - Install the required Python packages by running:
     ```bash
     pip install tls-client colorama pystyle
     ```

2. **Prepare Token and Proxy Files**:
   - Create a `tokens.txt` file with one Discord token per line:
     ```text
     token1
     token2
     ...
     ```
   - Create a `proxies.txt` file with one proxy per line in the format:
     ```text
     ip:port
     ```

3. **Run the Script**:
   - To execute the script:
     ```bash
     python main.py
     ```

4. **Input Required Information**:
   - The script will prompt you to input the following:
     - **Channel ID**: The Discord channel where the message is located.
     - **Message ID**: The ID of the message you want to react to.
     - **Emoji**: Enter the emoji (either a standard Unicode emoji or a custom Discord emoji, e.g., `<:emoji_name:emoji_id>`).

5. **Results**:
   - The script will attempt to add reactions to the message using each token, showing a color-coded output:
     - **Green**: Reaction added successfully.
     - **Red**: Failed to add the reaction.

## Custom Emoji Format

If you are using a custom emoji, use the following format:
```text
<:emoji_name:emoji_id>
```
For example:
```text
<:smiley:123456789012345678>
```

## Notes

- **Proxy Usage**: Make sure to populate your `proxies.txt` file with working proxies to avoid hitting Discord’s rate limits.
- **Token Format**: Ensure that the `tokens.txt` file is properly formatted with one valid Discord token per line.
- **Error Handling**: If a reaction fails for a token, the script will continue processing the remaining tokens.
