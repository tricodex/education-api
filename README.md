# Education API

## Overview

Education API is a backend system designed to support an intelligent tutoring platform. It uses AI technologies to provide personalized learning experiences, curriculum optimization, peer matching, and resource recommendations.

## Features

- AI-powered tutoring with multiple character personas
- Dynamic curriculum generation and optimization
- Peer matching for collaborative learning
- Personalized resource recommendations
- Gamification system with achievements and challenges
- Interactive learning environments
- User profile management
- Engagement tracking and analysis

## Tech Stack

- FastAPI
- SQLAlchemy
- Pydantic
- OpenAI API
- AI71 API (Falcon 180B)
- PostgreSQL 

## Project Structure

```
ai71/
├── __init__.py
├── main.py
├── api.py
├── models.py
├── database.py
├── dialogue_management/
│   ├── __init__.py
│   └── manager.py
├── curriculum/
│   ├── __init__.py
│   └── curriculum_gen.py
├── academica/
│   ├── __init__.py
│   └── environment_generator.py
├── gamification/
│   ├── __init__.py
│   └── system.py
├── peer_matching/
│   ├── __init__.py
│   └── matcher.py
├── recommender_system/
│   ├── __init__.py
│   └── recommender.py
├── element_lab/
│   └── element_gen.py
└── tests/
    └── api_test.py
```

## Setup

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/education-api.git
   cd education-api
   ```

2. Create a virtual environment and activate it:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

4. Set up environment variables:
   Create a `.env` file in the root directory and add the following variables:
   ```
   DATABASE_URL=your_database_url
   AI71_API_KEY=your_ai71_api_key
   OPENAI_API_KEY=your_openai_api_key
   ```

5. Initialize the database:
   ```
   alembic upgrade head
   ```

## Running the Application

To run the application locally:

```
uvicorn ai71.main:app --reload
```

The API will be available at `http://localhost:8000`.

## API Documentation

Once the application is running, you can access the interactive API documentation at:

- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

## Testing

To run the tests:

```
pytest ai71/tests
```

## Logic and Prompt Engineering

The Education API uses AI models and prompt engineering to create a dynamic and personalized learning experience. Here are some key aspects of the logic and prompt engineering used in the project:

1. Dialogue Management:
   - The system uses character personas (e.g., Wake, Levo, Mina) to create varied interactions.
   - Prompts are generated to maintain context and personality across conversations.
   - The AI model provides responses that are educational and aligned with the character's traits.

2. Curriculum Optimization:
   - The system analyzes student performance data and learning goals to generate curricula.
   - Prompts instruct the AI to create structured learning paths.
   - The AI considers factors like skill gaps, learning styles, and difficulty progression.

3. Peer Matching:
   - The system calculates compatibility between users based on skills, learning styles, and interests.
   - It uses a Monte Carlo method to form groups.
   - Prompts guide the AI in evaluating peer groups.

4. Gamification:
   - The AI generates achievement systems and challenges based on the curriculum and student progress.
   - Prompts are used to create content that encourages continued learning.
   - The system adjusts difficulty and rewards based on student engagement and performance.

5. Resource Recommendation:
   - The AI analyzes user profiles and learning contexts to recommend educational resources.
   - Prompts guide the AI in filtering and enhancing resource descriptions.
   - The system combines external search results with AI-generated content for recommendations.

6. Interactive Learning Environments:
   - The AI generates learning environments based on topics and complexity levels.
   - Prompts are used to create scenarios, challenges, and interactive elements.
   - The system adapts the environment based on student interactions and progress.

7. Engagement Analysis:
   - Prompts guide the AI in analyzing student activity data to calculate engagement scores.
   - The system considers factors like login frequency, time spent, topic diversity, and achievement progress.
   - Prompts are used to generate insights and recommendations for improving engagement.

The approach to prompt engineering in this project allows for:
- Contextual awareness across different modules of the system
- Personality consistency in character-based interactions
- Adaptive difficulty scaling based on student performance
- Generation of learning content and challenges
- Balancing of factors in peer group formation and resource recommendations

By using the AI71 API (Falcon 180B) and OpenAI's models, the system provides personalized, adaptive learning experiences.

## License

This project is licensed under the Apache License 2.0. For more details, see the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) page.