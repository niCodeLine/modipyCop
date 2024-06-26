# ModipyCop

ModipyCop is a Python tool that allows you to track modifications made to files or directories. Ideal for projects where monitoring changes in files is crucial, ModipyCop offers a simple and efficient way to get information on when files were last modified.

## Installation

You can easily install `modipyCop` using pip:

```bash
pip install modipyCop
```
or via git:

```bash
git clone https://github.com/niCodeLine/modipyCop.git
```
or just copy-paste it into your code.

## Usage

To use ModipyCop, first import the Cop class into your Python project and then follow these steps:

```python
from modipyCop import Cop

# Create an instance of the Cop class for a specific 
# directory or file and save the current state of files
directory = Cop("your/directory/path")
directory.prev_revision()

# Making changes in the directory files...

# Check and get a list of the modified files
directory.post_revision()
```

Or be used as a decorator:

```python
from modipyCop import decoprator

@decoprator('your/directory/path')
def some_function(var,var_1):
    # some_function code...

```

## Outputs
Depending on whether a path to a folder or a specific file is given, you can get different outputs:

### Folder
For a folder path:
```markdown
No file was modified in your/directory/path
```
and
```markdown
Modified files in your/directory/path:

file_1.py, 1.23 seconds ago.
text_1.txt, 4.56 seconds ago.
```

### File
For an individual file path:

```markdown
No modifications in file_1.py
```
and
```markdown
file_1.py modified 7.89 seconds ago.
```

## Features

- **Modification Tracking**: Allows tracking of the latest modifications of files or directories.
- **Easy to Use**: A simple and straightforward interface for reviewing file changes.
- **Usable as Decorator**: Avoid unneceserly writing and use the decorator module.

## Reminder
Before using `post_revision()`, it's important to call `prev_revision()` to save the current state of the files. This ensures that `post_revision()` can accurately detect and report any changes made.

*You can forget about this concern by just using the decoprator module as a decorator.*

## Contributions

Contributions are welcome! If you have improvements or fixes, please feel free to send a pull request or open an issue in the GitHub repository.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Contact

Nico Spok - nicospok@hotmail.com
GitHub: niCodeLine
