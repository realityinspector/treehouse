# treehouse
make trees - file structure trees - to feed to llms. 

the output markdown file explains app architecture in e.g. cursor which helps get better performance in context. 


# Treehouse

Treehouse is a Python-based documentation generator that creates comprehensive documentation of your codebase structure, including directory trees, database relationships, and configuration mappings.

## Features

- **Directory Tree Generation**: Automatically creates a visual tree representation of your project structure
- **Smart Filtering**: Ignores common development artifacts and directories (like `.git`, `__pycache__`, etc.)
- **Image File Detection**: Automatically counts and summarizes image files in directories
- **Database Model Visualization**: Generates Mermaid diagrams of your database models and their relationships
- **Configuration Mapping**: Creates a structured overview of your project's configuration settings
- **Project Dependencies**: Extracts and displays project dependencies from pyproject.toml

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/treehouse.git

# Navigate to the project directory
cd treehouse

# Install dependencies (requires Python 3.9+)
pip install -r requirements.txt
```

## Usage

Run treehouse in your project directory:

```bash
python treehouse.py
```

This will generate a `tree.md` file containing:
- A complete directory tree of your project
- Database model relationships diagram
- Configuration settings map
- Project dependency information

### Configuration

Treehouse comes with default settings for ignoring common development files and directories. You can customize these by modifying the following constants in the script:

```python
IGNORE_PATTERNS = [
    r'\.pyc$',
    r'\.pyo$',
    # Add your custom patterns here
]

IMAGE_EXTENSIONS = {'.png', '.jpg', '.jpeg', '.gif', '.svg', '.ico', '.webp'}
RELEVANT_EXTENSIONS = {'.py', '.html', '.js', '.json', '.css', '.md'}
```

## Output Example

The generated `tree.md` will contain sections like:

```
# Project Structure and Documentation

## Directory Tree
├── src/
│   ├── models/
│   ├── controllers/
│   ├── templates/
│   └── [3 image files]

## Database Models and Relationships
[Mermaid diagram of database relationships]

## Configuration Map
Environment:
  - FLASK_ENV
  - SECRET_KEY
  - DATABASE_URL
...
```

## Requirements

- Python 3.9 or higher
- Operating system: Windows, macOS, or Linux
- Write permissions in the target directory

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Known Limitations

- Currently only supports Python projects using SQLAlchemy for database models
- Image file counting is limited to common web image formats
- Configuration mapping requires manual updates for new config categories

## Support

For issues, questions, or contributions, please:
1. Check the existing issues in the repository
2. Open a new issue if your problem hasn't been addressed
3. Provide as much context as possible, including your operating system and Python version
