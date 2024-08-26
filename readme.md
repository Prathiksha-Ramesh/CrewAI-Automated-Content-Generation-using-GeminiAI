# CrewAI Automated Content Generation

This project leverages CrewAI to automate the process of researching and writing tech-focused content. The system is designed to orchestrate a series of tasks performed by specialized agents, streamlining the content creation workflow from topic research to final write-up.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Dependencies](#dependencies)
- [License](#license)
- [Contributing](#contributing)

## Overview

CrewAI Automated Content Generation is a Python-based tool that automates the creation of content by organizing agents into a crew that performs specific tasks. This project is particularly suited for generating tech-focused articles with a streamlined, sequential process.

## Features

- **Automated Research**: Uses `news_researcher` to gather information on a given topic.
- **Automated Writing**: Uses `news_writer` to generate well-structured content based on the research.
- **Sequential Process**: Tasks are performed in sequence, ensuring a smooth workflow from research to content creation.
- **Enhanced Feedback**: The system provides feedback after each task, allowing for monitoring and fine-tuning.

## Installation

### Prerequisites

- Python 3.7 or higher
- Git

### Setup

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/crewai-content-generation.git
    cd crewai-content-generation
    ```

2. Create a virtual environment and activate it:

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

4. Ensure that your `.gitignore` file is set up to ignore sensitive files like environment variables or temporary files.

## Usage

To run the content generation process:

```python
from crewai import Crew, Process
from tasks import research_task, write_task
from agents import news_researcher, news_writer

# Formatting the tech-focused crew with enhanced configurations:
crew = Crew(
    agents=[news_researcher, news_writer],
    tasks=[research_task, write_task],
    process=Process.sequential,
)

# Starting the task execution process with enhanced feedback:
result = crew.kickoff(inputs={'topic': 'AI in healthcare'})
print(result)

## How It Works:

- **Research Task**: The `news_researcher` agent performs a thorough investigation on the provided topic.
- **Writing Task**: The `news_writer` agent uses the research data to create a comprehensive article.
- **Sequential Execution**: Tasks are executed in the order specified by the process configuration, ensuring a logical flow.

## Project Structure

- `crew.py`: Defines the `Crew` and `Process` classes that manage the agents and tasks.
- `agents.py`: Contains the agents like `news_researcher` and `news_writer` that perform specific tasks.
- `tasks.py`: Defines the tasks such as `research_task` and `write_task`.
- `tools.py`: Additional utilities or tools that might be used by agents.
- `new-blog-post.md`: Example of generated content output.
- `requirements.txt`: Lists all the dependencies required to run the project.
- `.gitignore`: Specifies files and directories to be ignored by Git.

## Dependencies

The project uses the following dependencies:

- `crewai`: The core library for managing crews, agents, and tasks.
- `other-dependencies`: Other necessary packages for running the agents and tasks (listed in `requirements.txt`).

For a full list of dependencies, please refer to the `requirements.txt` file.

## License

This project is licensed under the MIT License - see the `LICENSE` file for details.

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.
