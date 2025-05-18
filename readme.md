# AI Multi-Agent Systems

This project demonstrates eight different implementations of multi-agent systems using CrewAI:

1. Content Creation Pipeline
2. Customer Support System
3. Event Planning System
4. Customer Outreach System
5. Financial Analysis System
6. Job Application System
7. Automated Planning System
8. Agentic Sales Pipeline

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

### 6. Job Application System (`jobApplication.ipynb`)

A specialized system for job application preparation:

- **Profiler**: Compiles comprehensive personal and professional profiles
- **Resume Writer**: Creates tailored resumes based on job requirements
- **Cover Letter Writer**: Drafts personalized cover letters
- **Application Reviewer**: Reviews and refines application materials

### 7. Automated Planning System (`automatedPlanning.ipynb`)

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

### Automated Planning System

1. Open `automatedPlanning.ipynb`
2. Run the cells to initialize the planning agents and crew
3. Create automated plans by providing project details:
   ```python
   inputs = {
       "project_scope": "Project Scope",
       "resources": "Available Resources",
       "timeline": "Project Timeline",
       "constraints": "Project Constraints",
       "objectives": "Project Objectives"
   }
   result = crew.kickoff(inputs=inputs)
   ```

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

### Job Application System

1. Open `jobApplication.ipynb`
2. Run the cells to initialize the job application agents and crew
3. Prepare job application materials by providing personal information:
   ```python
   profile_task = Task(
       description=(
           "Compile a detailed personal and professional profile "
           "using the GitHub ({github_url}) URLs, and personal write-up "
           "({personal_writeup}). Utilize tools to extract and "
           "synthesize information from these sources."
       ),
       expected_output=(
           "A comprehensive profile document that includes skills, "
           "project experiences, contributions, interests, and "
           "communication style."
       ),
       agent=profiler
   )
   ```

### Automated Planning System

- Dynamic resource allocation
- Intelligent schedule optimization
- Constraint-based planning
- Real-time progress monitoring
- Risk assessment and mitigation
- Automated dependency resolution
- Multi-objective optimization
- Adaptive planning capabilities

### Agentic Sales Pipeline

1. Open `AgenticSalesPipeline.ipynb`
2. Run the cells to initialize the sales pipeline agents and crew
3. Manage sales pipeline by providing lead details:
   ```python
   inputs = {
       "target_market": "Target Market Segment",
       "product_details": "Product/Service Information",
       "sales_goals": "Sales Objectives",
       "timeline": "Sales Timeline"
   }
   result = crew.kickoff(inputs=inputs)
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

### Job Application System

- Profile compilation from multiple sources
- Resume customization for specific jobs
- Cover letter personalization
- Application material review and refinement
- GitHub integration for project showcase
- Professional tone and formatting

### Automated Planning System

- Dynamic resource allocation
- Intelligent schedule optimization
- Constraint-based planning
- Real-time progress monitoring
- Risk assessment and mitigation
- Automated dependency resolution
- Multi-objective optimization
- Adaptive planning capabilities

### Agentic Sales Pipeline

- Lead generation and qualification
- Personalized sales strategy development
- Automated proposal creation
- Follow-up management
- Sales pipeline optimization
- Customer engagement tracking
- Performance analytics
- Multi-channel sales coordination

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
