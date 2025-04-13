# AI Multi-Agent Systems

This project demonstrates five different implementations of multi-agent systems using CrewAI:

1. Content Creation Pipeline
2. Customer Support System
3. Event Planning System
4. Customer Outreach System
5. Financial Analysis System

## Overview

### 1. Content Creation Pipeline (`ResearchWriteArticle.ipynb`)

A three-agent system that collaboratively creates blog articles:

- **Content Planner**: Plans and researches content, creating detailed outlines
- **Content Writer**: Writes the article based on the planner's outline
- **Editor**: Proofreads and polishes the final content

### 2. Customer Support System (`CustomerSupport.ipynb`)

A two-agent system that handles customer inquiries:

- **Senior Support Representative**: Handles customer inquiries and provides detailed responses
- **Support Quality Assurance Specialist**: Reviews and ensures the quality of responses

### 3. Event Planning System (`EventPlanning.ipynb`)

A multi-agent system for comprehensive event planning:

- **Event Planner**: Coordinates and plans event details
- **Venue Manager**: Handles venue selection and management
- **Marketing Specialist**: Creates marketing strategies and materials
- **Budget Analyst**: Manages financial aspects and budgeting

### 4. Customer Outreach System (`CustomerOutreach.ipynb`)

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

## Prerequisites

- Python 3.x
- OpenAI API key
- Required packages:
  ```bash
  pip install crewai python-dotenv langchain-openai
  ```

## Setup

1. Clone the repository
2. Create a `.env` file in the project root with your OpenAI API credentials:
   ```
   OPENAI_API_KEY=your_api_key_here
   OPENAI_MODEL_NAME=your_preferred_model  # Optional
   ```

## Usage

### Content Creation Pipeline

1. Open `ResearchWriteArticle.ipynb`
2. Run the cells to initialize the agents and crew
3. Generate content by providing a topic:
   ```python
   result = crew.kickoff(inputs={"topic": "Your Topic Here"})
   ```

### Customer Support System

1. Open `CustomerSupport.ipynb`
2. Run the cells to initialize the support agents and crew
3. Handle customer inquiries by providing customer details:
   ```python
   inputs = {
       "customer": "CustomerName",
       "person": "ContactPerson",
       "inquiry": "Customer's question or issue"
   }
   result = crew.kickoff(inputs=inputs)
   ```

### Event Planning System

1. Open `EventPlanning.ipynb`
2. Run the cells to initialize the event planning agents and crew
3. Plan events by providing event details:
   ```python
   inputs = {
       "event_type": "Type of Event",
       "date": "Event Date",
       "budget": "Budget Range",
       "attendees": "Expected Number of Attendees"
   }
   result = crew.kickoff(inputs=inputs)
   ```

### Customer Outreach System

1. Open `CustomerOutreach.ipynb`
2. Run the cells to initialize the outreach agents and crew
3. Manage customer outreach by providing campaign details:
   ```python
   inputs = {
       "campaign_type": "Type of Campaign",
       "target_audience": "Target Audience",
       "message": "Key Message",
       "timeline": "Campaign Timeline"
   }
   result = crew.kickoff(inputs=inputs)
   ```

### Financial Analysis System

1. Open `financialAnalysis.ipynb`
2. Run the cells to initialize the financial analysis agents and crew
3. Analyze financial data using the hierarchical process:
   ```python
   financial_trading_crew = Crew(
       agents=[
           data_analyst_agent,
           trading_strategy_agent,
           execution_agent,
           risk_management_agent,
       ],
       tasks=[
           data_analysis_task,
           strategy_development_task,
           execution_planning_task,
           risk_assessment_task,
       ],
       manager_llm=ChatOpenAI(model="gpt-3.5-turbo", temperature=0.7),
       process=Process.hierarchical,
       verbose=True,
   )
   result = financial_trading_crew.kickoff()
   ```

## Features

### Content Creation Pipeline

- Sequential task execution
- SEO optimization
- Source citation
- Markdown output format
- Detailed content planning
- Quality assurance through editing

### Customer Support System

- Quality assurance review process
- Documentation scraping capabilities
- Memory-enabled responses
- Professional and friendly tone
- Comprehensive inquiry resolution

### Event Planning System

- Venue selection and management
- Budget optimization
- Marketing strategy development
- Timeline management
- Resource allocation
- Vendor coordination

### Customer Outreach System

- Campaign strategy development
- Content creation and optimization
- Response management
- Analytics and reporting
- Multi-channel outreach
- Engagement tracking

### Financial Analysis System

- Data analysis and processing
- Trading strategy development
- Execution planning
- Risk assessment and management
- Hierarchical coordination
- Specialized financial tools

## Configuration

All systems support:

- Verbosity levels (1 or 2) for detailed logging
- Custom agent roles and tasks
- Tool integration
- Memory management
- Different process types (sequential, hierarchical)

## Model Configuration

### Temperature Settings

- **Temperature = 0.0**: Deterministic outputs, most consistent
- **Temperature = 0.7**: Balanced creativity and consistency (default for many tasks)
- **Temperature = 1.0**: More creative and diverse outputs

## Tools and Integration

### Available Tools

- SerperDevTool: Google search integration
- ScrapeWebsiteTool: Web content scraping
- WebsiteSearchTool: Website-specific search
- Custom tool support for all systems

## Best Practices

1. **Agent Configuration**

   - Define clear roles and goals
   - Set appropriate delegation permissions
   - Enable verbose mode for debugging

2. **Task Management**

   - Create detailed task descriptions
   - Set clear expected outputs
   - Assign appropriate tools to tasks

3. **Process Selection**

   - Use sequential process for simple workflows
   - Use hierarchical process for complex, coordinated tasks
   - Consider agent specializations when choosing process type

4. **Quality Assurance**
   - Implement review processes
   - Enable memory for context retention
   - Use appropriate tools for verification

## Note

This project uses OpenAI's API by default. Ensure you have sufficient API credits and a valid API key before running any of the systems.

## License

[Add your license information here]
