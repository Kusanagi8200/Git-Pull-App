# Git Repositories Update Script

This bash script is designed to automatically update a list of local Git repositories. It uses colors to highlight different stages and outcomes of the operations.
Equivalent as --> find . -maxdepth 3 -name .git -type d | rev | cut -c 6- | rev | xargs -I {} git -C {} pull

## Functionality

The script iterates through a list of paths to local Git repositories. For each repository, it attempts to execute `git pull` to update it. If a repository contains uncommitted changes, the script displays a warning and moves on to the next repository.

## Text Formatting

Color variables are defined to enhance message readability:

- `HIGHLIGHT`: Orange background with bold black text.
- `ERROR`: Red background with bold white text.
- `SUCCESS`: Purple background with bold white text.
- `NC` (No Color): Resets the color to normal.

## Repositories List

Repositories are defined in an array `REPOS`, with each path to a repository on a separate line.

## Update Loop

The script iterates over each repository:

- Changes to the repository directory (`cd`).
- Checks if there are uncommitted changes.
  - If yes, displays an error message and continues with the next repository.
  - Otherwise, executes `git pull` to update the repository.

## Example Output

- Messages in orange indicate the start of updating a repository.
- Messages in red indicate the presence of uncommitted changes.
- The final message in purple indicates that the update of all repositories is complete.

## Usage

To use this script, make sure it is executable:

```bash
chmod +x script_name.sh
