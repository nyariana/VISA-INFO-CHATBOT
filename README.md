# VISA-INFO-CHATBOT
Chatbot application for providing visa information, guidance, and support to users seeking information about different visa types, requirements, and processes.
## Features

- **User Authentication**: Secure registration and login with JWT tokens
- **Chat System**: Interactive chat sessions for visa inquiries
- **Chat History**: Persistent storage of chat conversations
- **Document Upload**: Users can upload documents related to visa applications
- **Visa Information**: Comprehensive database of visa types and requirements
- **Application Forms**: Support for visa application forms
- **RESTful API**: Well-documented API endpoints

## Technology Stack

### Backend
- **Framework**: FastAPI (Python)
- **Database**: SQLAlchemy ORM with SQLite (development) / PostgreSQL (production)
- **Authentication**: JWT with bcrypt password hashing
- **Server**: Uvicorn

### Frontend
- **Framework**: React (in development)
- **HTTP Client**: Axios
- **UI Framework**: Material-UI or Tailwind CSS (TBD)

## Project Structure

```
visainfochatbot/
├── backend/
│   ├── app/
│   │   ├── __init__.py
│   │   ├── config.py              # Configuration settings
│   │   ├── database.py            # Database connection
│   │   ├── models/                # SQLAlchemy models
│   │   │   ├── user.py
│   │   │   ├── chat.py
│   │   │   ├── document.py
│   │   │   └── visa_info.py
│   │   ├── routes/                # API endpoints
│   │   │   ├── auth.py            # Authentication endpoints
│   │   │   ├── chat.py            # Chat endpoints
│   │   │   ├── visa_info.py       # Visa info endpoints
│   │   │   └── documents.py       # Document upload endpoints
│   │   ├── schemas/               # Pydantic schemas
│   │   │   ├── user.py
│   │   │   ├── chat.py
│   │   │   ├── document.py
│   │   │   └── visa_info.py
│   │   └── utils/                 # Utility functions
│   │       ├── auth.py            # Authentication helpers
│   │       ├── visa_knowledge.py  # Visa information database
│   │       └── document_processor.py
│   ├── tests/                     # Test suite
│   ├── main.py                    # FastAPI application entry
│   ├── requirements.txt           # Python dependencies
│   └── .env.example               # Environment variables example
├── frontend/                      # React frontend (TBD)
└── README.md
```

## Installation

### Backend Setup

1. **Clone/Navigate to the project**:
   ```bash
   cd backend
   ```

2. **Create virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Setup environment variables**:
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

5. **Run database migrations** (if using Alembic):
   ```bash
   alembic upgrade head
   ```

6. **Start the server**:
   ```bash
   python main.py
   ```

The API will be available at `http://localhost:8000`

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

```env
DATABASE_URL=sqlite:///./visa_chatbot.db
SECRET_KEY=your-secret-key-here-change-in-production
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
UPLOADS_DIR=./uploads
API_HOST=0.0.0.0
API_PORT=8000
```

## Development

### Running Tests
```bash
pytest tests/
```

### Code Style
- Follow PEP 8 guidelines
- Use type hints
- Write docstrings for all functions

## Future Enhancements

- [ ] AI-powered chatbot with NLP
- [ ] Advanced visa requirement matching
- [ ] Integration with real visa application systems
- [ ] Multi-language support
- [ ] Mobile app
- [ ] Real-time notifications
- [ ] Email notifications
- [ ] Admin dashboard

## Contributing

1. Create a feature branch (`git checkout -b feature/AmazingFeature`)
2. Commit your changes (`git commit -m 'Add AmazingFeature'`)
3. Push to the branch (`git push origin feature/AmazingFeature`)
4. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, email support@visachatbot.com or open an issue on GitHub.

## Roadmap

- **Phase 1** (Current): Backend API development
- **Phase 2**: Frontend React UI
- **Phase 3**: AI/ML integration for intelligent responses
- **Phase 4**: Production deployment and scaling
