# VISA-INFO-CHATBOT
Chatbot application for providing visa information, guidance, and support to users seeking information about different visa types, requirements, and processes.
**Features**

Here are some of the core features currently implemented:

User Authentication
Secure user registration and login using JWT authentication
Chat System
Interactive chat interface where users can ask visa-related questions
Chat History
Saves previous conversations so users can revisit them anytime
Document Upload
Allows users to upload and manage documents related to visa applications
Visa Information
Structured data on visa types, requirements, and processing details
Application Support
Basic handling of visa-related forms and information
REST API
Clean and organized API endpoints built with FastAPI

## Technology Stack

**Backend**
FastAPI (Python)
SQLAlchemy (ORM)
SQLite (development) / PostgreSQL (production)
JWT Authentication + bcrypt
Uvicorn server

### Frontend
- Framework: React (in development)
- HTTP Client: Axios
- UI Framework: Material-UI or Tailwind CSS (TBD)

## Project Structure

Project Structure
visainfochatbot/
├── backend/
│   ├── app/
│   │   ├── config.py
│   │   ├── database.py
│   │   ├── models/
│   │   ├── routes/
│   │   ├── schemas/
│   │   └── utils/
│   ├── tests/
│   ├── main.py
│   └── requirements.txt
├── frontend/  # (in progress)
└── README.md

## Installation

**Backend Setup**
Navigate to the backend folder:
cd backend**

Create a virtual environment:
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

Install dependencies:
pip install -r requirements.txt

Set up environment variables:
cp .env.example .env

Run the application:

python main.py

The API will run on:
👉 http://localhost:8000

## API Documentation

Once the server is running, access the interactive API documentation:
- **Swagger UI**: http://localhost:8000/docs
- **ReDoc**: http://localhost:8000/redoc

## API Endpoints

### Authentication
- `POST /auth/register` - Register new user
- `POST /auth/login` - Login user

### Chat
- `POST /chat/sessions` - Create new chat session
- `GET /chat/sessions` - Get user's chat sessions
- `GET /chat/sessions/{session_id}` - Get specific session
- `POST /chat/sessions/{session_id}/messages` - Send message
- `DELETE /chat/sessions/{session_id}` - Delete session

### Visa Information
- `GET /visa/categories` - Get all visa categories
- `GET /visa/search` - Search visa information
- `GET /visa/requirements/{visa_type}` - Get visa requirements
- `GET /visa/processing-time/{visa_type}` - Get processing time
- `GET /visa/details/{visa_type}` - Get detailed visa info

### Documents
- `POST /documents/upload` - Upload document
- `GET /documents` - Get user's documents
- `GET /documents/{document_id}` - Get specific document
- `DELETE /documents/{document_id}` - Delete document

## Environment Variables

DATABASE_URL=sqlite:///./visa_chatbot.db 
SECRET_KEY=your-secret-key 
ACCESS_TOKEN_EXPIRE_MINUTES=30 
UPLOADS_DIR=./uploads 
API_PORT=8000

## Future Enhancements

This project is still evolving. Some things I plan to work on next:

Add smarter AI-based responses (NLP)
Improve visa matching based on user profile
Support multiple languages
Build a simple frontend interface
Add notifications (email or in-app)
Create an admin dashboard

## Contributing
This started as a personal project, but contributions and ideas are welcome.

If you'd like to contribute:
Fork the repository
Create a new branch
Make your changes
Submit a pull request

You can also open an issue if you find a bug or have suggestions.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

