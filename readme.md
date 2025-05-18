# AI Multi-Agent Systems

This project demonstrates various implementations of multi-agent systems using CrewAI:

1. Content Creation Pipeline
2. Customer Support System
3. Event Planning System
4. Customer Outreach System
5. Financial Analysis System
6. Job Application System
7. Automated Planning System
8. Agentic Sales Pipeline
9. Performance Optimization System
10. Progress Reporting System
11. Content at Scale System

## Overview

### 1. Content Creation Pipeline (`researchWriteArticle.ipynb`)

A three-agent system that collaboratively creates blog articles:

- **Content Planner**: Plans and researches content, creating detailed outlines
- **Content Writer**: Writes the article based on the planner's outline
- **Editor**: Proofreads and polishes the final content

### 2. Customer Support System (`customerSupport.ipynb`)

A two-agent system that handles customer inquiries:

- **Senior Support Representative**: Handles customer inquiries and provides detailed responses
- **Support Quality Assurance Specialist**: Reviews and ensures the quality of responses

### 3. Event Planning System (`eventPlanning.ipynb`)

A multi-agent system for comprehensive event planning:

- **Event Planner**: Coordinates and plans event details
- **Venue Manager**: Handles venue selection and management
- **Marketing Specialist**: Creates marketing strategies and materials
- **Budget Analyst**: Manages financial aspects and budgeting

### 4. Customer Outreach System (`customerOutreach.ipynb`)

A specialized system for customer engagement and outreach:

- **Outreach Coordinator**: Manages customer communication strategies
- **Content Creator**: Develops engaging outreach materials
- **Response Handler**: Processes and manages customer responses

### 5. Financial Analysis System (`financialAnalysis.ipynb`)

A hierarchical system for financial trading analysis:

- **Data Analyst**: Processes and analyzes financial data
- **Trading Strategy Agent**: Develops trading strategies based on analysis
- **Execution Agent**: Plans the execution of trading strategies
- **Risk Management Agent**: Assesses and manages trading risks

### 6. Job Application System (`jobApplication.ipynb`)

A specialized system for job application preparation:

- **Profiler**: Compiles comprehensive personal and professional profiles
- **Resume Writer**: Creates tailored resumes based on job requirements
- **Cover Letter Writer**: Drafts personalized cover letters
- **Application Reviewer**: Reviews and refines application materials

### 7. Automated Planning System (`AutomatedPlanning_crew.ipynb`)

A sophisticated system for automated task and project planning:

- **Planning Coordinator**: Oversees and coordinates the planning process
- **Resource Allocator**: Manages and optimizes resource distribution
- **Schedule Optimizer**: Creates and optimizes project timelines
- **Constraint Manager**: Handles dependencies and constraints
- **Progress Monitor**: Tracks and reports on plan execution

### 8. Agentic Sales Pipeline (`AgenticSalesPipeline.ipynb`)

A specialized system for automated sales pipeline management:

- **Sales Lead Generator**: Identifies and qualifies potential leads
- **Sales Strategist**: Develops personalized sales strategies
- **Proposal Creator**: Generates tailored sales proposals
- **Follow-up Coordinator**: Manages customer follow-ups and engagement

### 9. Performance Optimization System (`PerformanceOptimization.ipynb`)

A system focused on optimizing agent performance and efficiency:

- **Performance Analyzer**: Monitors and analyzes system performance
- **Optimization Strategist**: Develops optimization strategies
- **Implementation Specialist**: Implements performance improvements

### 10. Progress Reporting System (`ProgressReport.ipynb`)

A system for tracking and reporting project progress:

- **Progress Tracker**: Monitors ongoing tasks and milestones
- **Report Generator**: Creates comprehensive progress reports
- **Analytics Specialist**: Analyzes progress data and trends

### 11. Content at Scale System (`ContentAtScale.ipynb`)

A system for generating and managing large-scale content production:

- **Content Strategist**: Plans and coordinates content production
- **Content Generator**: Creates high-quality content at scale
- **Quality Controller**: Ensures content meets standards
- **Distribution Manager**: Manages content distribution

## Project Structure

```
.
├── config/                 # Configuration files
├── db/                    # Database files
├── InterviewPrep/         # Interview preparation materials
├── Resume/               # Resume-related files
├── *.ipynb               # Jupyter notebooks for each system
├── requirements.txt      # Python dependencies
└── readme.md            # Project documentation
```

## Prerequisites

- Python 3.x
- OpenAI API key
- Required packages (see requirements.txt):
  ```bash
  pip install -r requirements.txt
  ```

## Setup

1. Clone the repository
2. Create a `.env` file in the project root with your API credentials:
   ```
   OPENAI_API_KEY=your_api_key_here
   OPENAI_MODEL_NAME=your_preferred_model  # Optional
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

Each system is implemented as a Jupyter notebook. To use a specific system:

1. Open the corresponding `.ipynb` file
2. Run the cells to initialize the agents and crew
3. Follow the specific usage instructions in each notebook

## Process Types

### Sequential Process

- Agents work in a linear sequence
- Each agent passes work to the next agent
- Simple workflow with clear handoffs

### Hierarchical Process

- Manager-Employee structure with centralized decision-making
- Manager LLM coordinates and delegates tasks
- Allows for complex workflows with dependencies
- Enables feedback loops and revisions
- Ideal for specialized tasks requiring coordination

## Contributing

Feel free to contribute to this project by:

1. Forking the repository
2. Creating a feature branch
3. Making your changes
4. Submitting a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
