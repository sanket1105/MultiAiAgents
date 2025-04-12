## Usage

1. Import the required libraries:

```python
from crewai import Agent, Task, Crew
from dotenv import load_dotenv
```

2. Run the content creation pipeline:

```python
# Initialize the crew
crew = Crew(agents=[planner, writer, editor], tasks=[plan, write, edit], verbose=2)

# Generate content
result = crew.kickoff(inputs={"topic": "Your Topic Here"})
```

## Agent Roles

### Content Planner

- Plans engaging and factually accurate content
- Creates comprehensive outlines
- Identifies target audience and SEO keywords
- Provides research and resources

### Content Writer

- Writes insightful and factually accurate articles
- Follows the planner's outline
- Incorporates SEO keywords naturally
- Maintains balanced viewpoints

### Editor

- Reviews and proofreads content
- Ensures alignment with brand voice
- Checks for balanced viewpoints
- Maintains journalistic best practices

## Features

- Sequential task execution
- Detailed logging with verbose mode
- Customizable agent roles and tasks
- Markdown output format
- SEO optimization
- Source citation

## Configuration

You can adjust the verbosity level of the crew:

- `verbose=1`: Basic logging
- `verbose=2`: Detailed logging including agent thinking process

## Output

The pipeline generates a complete blog post in markdown format, including:

- Title and headings
- Well-structured content
- SEO-optimized text
- Conclusion with call-to-action

## Note

This project uses OpenAI's API by default. Ensure you have sufficient API credits and a valid API key before running the pipeline.
