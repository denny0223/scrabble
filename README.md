# scrabble

A simple tool to recover Git repositories from exposed `.git` folders on remote servers.

## Usage

`scrabble <url> [directory]`

### Arguments:

*   `<url>`: The full URL to the repository's `.git` directory (e.g., `http://example.com/my-project.git/`).
*   `[directory]` (Optional): The local directory to clone the repository into.
    *   If not provided, the script defaults to a directory name derived from the URL (e.g., `my-project` from `http://example.com/my-project.git/`).

### Important Notes:

*   You need to make sure the target URL has an exposed `.git` folder.
*   The script will **not** overwrite an existing directory. If the target directory already exists, the script will exit with an error to prevent accidental data loss. Please remove the existing directory or choose a different name.
*   This tool is designed to clone a repository into a **new, empty directory**. Do not run it inside an existing Git repository, as it will overwrite its contents.

## Example

```bash
# Clone to a directory named 'my-project'
scrabble http://example.com/my-project.git/

# Clone to a specific directory named 'my-local-repo'
scrabble http://example.com/my-project.git/ my-local-repo
```