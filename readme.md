# News Reporter AI

News Reporter AI is an automated content generation tool designed to streamline the process of researching and writing news articles. This Python-based system organizes a team of agents to perform tasks sequentially, providing a smooth workflow from topic research to article creation, specifically tailored for news reporting.

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

News Reporter AI leverages the power of automated agents to research topics and generate news articles. By organizing these agents into a crew that performs specific tasks, this project is particularly useful for producing timely and accurate news content with minimal human intervention.

## Features

- **Automated News Research**: Utilizes the `news_researcher` agent to gather comprehensive information on a given topic.
- **Automated News Writing**: Uses the `news_writer` agent to craft detailed, well-structured news articles based on the research.
- **Sequential Task Execution**: Ensures a logical flow from research to writing using a sequential process configuration.
- **Enhanced Feedback**: Provides detailed feedback after each task to improve content quality and workflow efficiency.

## Installation

### Prerequisites

- Python 3.7 or higher
- Git

### Setup

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/news-reporter-ai.git
    cd news-reporter-ai
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

4. Ensure that your `.gitignore` file is set up to ignore sensitive files such as environment variables or temporary files.

## Usage

To run the news generation process:

```python
from crewai import Crew, Process
from tasks import research_task, write_task
from agents import news_researcher, news_writer

# Set up the crew with the research and writing tasks
crew = Crew(
    agents=[news_researcher, news_writer],
    tasks=[research_task, write_task],
    process=Process.sequential,
)

# Execute the task with the specified topic
result = crew.kickoff(inputs={'topic': 'AI in healthcare'})
print(result)

## How It Works:

- **Research Task**: The `news_researcher` agent performs a thorough investigation on the provided topic.
- **Writing Task**: The `news_writer` agent uses the research data to create a comprehensive news article.
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
- `bitsandbytes`: For optimizing memory usage during training.
- `peft`: Parameter-efficient fine-tuning of models.
- `trl`: Tools for Reinforcement Learning with Transformers.
- `accelerate`: A library to optimize and accelerate model training.
- `datasets`: For managing and processing datasets.
- `transformers`: Hugging Face's Transformers library for handling various NLP tasks.

For a full list of dependencies, please refer to the `requirements.txt` file.

## License

This project is licensed under the MIT License - see the `LICENSE` file for details.

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.


