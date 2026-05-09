# GitHub Training Area

_A hands-on learning repository to master GitHub features, security tools, and collaborative development practices._

## 📚 What is This?

This is a **GitHub Skills Training Repository** where you learn by doing. Each part of this repo teaches you real GitHub features:

- ✅ **Code Security** (CodeQL, Security Policy)
- ✅ **Dependency Management** (Dependabot)
- ✅ **Collaborative Development** (Code of Conduct, CODEOWNERS, Contributing Guidelines)
- ✅ **Project Management** (Issues, Pull Requests, Workflows)
- ✅ **Application Development** (MongoDB + FastAPI)

## 🎯 What You'll Learn

### GitHub Features
- 🔒 **Code Scanning** - CodeQL static analysis (security vulnerabilities)
- 🤖 **Dependabot** - Automated dependency updates
- 📋 **CODEOWNERS** - Assign code ownership and reviews
- 🛡️ **Security Policy** - Report vulnerabilities responsibly
- 📖 **Contributing Guidelines** - Guide collaborators
- 💬 **Code of Conduct** - Foster healthy collaboration
- 🔄 **GitHub Actions** - Automate workflows

### Technology Stack
- **Backend**: Python 3.x with [FastAPI](https://fastapi.tiangolo.com/)
- **Database**: MongoDB
- **Frontend**: JavaScript, HTML, CSS
- **Security**: Argon2 password hashing

## 🚀 Quick Start

### 1. Prerequisites
- Python 3.8+
- MongoDB (running locally or remotely)
- Git

### 2. Installation

```bash
# Clone the repository
git clone https://github.com/BytecodeBrewer/training-area.git
cd training-area

# Install Python dependencies
pip install -r requirements.txt
```

### 3. Configure MongoDB

Update the MongoDB connection in `src/backend/database.py`:

```python
# Connect to MongoDB
client = MongoClient('mongodb://localhost:27017/')  # Change connection string if needed
db = client['mergington_high']
```

Or use MongoDB Atlas:
```python
client = MongoClient('mongodb+srv://username:password@cluster.mongodb.net')
```

### 4. Run the Application

```bash
# Start the FastAPI server
python -m uvicorn src.app:app --reload
```

The application will be available at:
- 🌐 **Frontend**: http://localhost:8000
- 📚 **API Docs**: http://localhost:8000/docs
- 🔄 **Alternative Docs**: http://localhost:8000/redoc

### 5. Access Sample Data

The database initializes with sample activities and teacher accounts:

**Sample Teacher Login:**
- Username: `teacher1`
- Password: `SecurePassword123`

## 📁 Project Structure

```
training-area/
├── src/
│   ├── app.py                 # FastAPI application entry point
│   ├── backend/
│   │   ├── database.py        # MongoDB configuration & setup
│   │   └── routers/
│   │       ├── activities.py  # Activity management endpoints
│   │       └── auth.py        # Authentication endpoints
│   └── static/
│       ├── index.html         # Frontend UI
│       ├── app.js             # Frontend logic
│       └── styles.css         # Styling
├── requirements.txt           # Python dependencies
├── README.md                  # This file
├── CONTRIBUTING.md            # How to contribute
├── CODE_OF_CONDUCT.md         # Community guidelines
├── SECURITY.md                # Security policy
├── CODEOWNERS                 # Code ownership rules
└── .github/workflows/         # GitHub Actions (CodeQL, etc.)
```

## 🔐 Security Features

### CodeQL Analysis
This repository uses **GitHub CodeQL** for automated security scanning:
- Analyzes code for vulnerabilities (JavaScript, Python)
- Runs on every pull request
- Results visible in Security tab → Code scanning alerts

### Dependabot
**Dependabot** automatically creates pull requests for:
- Security updates to dependencies
- Version upgrades

Check the [pull requests tab](../../pulls) to see Dependabot updates.

### Security Policy
Found a vulnerability? Report it securely:
1. Go to the **Security** tab
2. Click **Report a vulnerability**
3. Fill out the form (don't discuss publicly!)

See [SECURITY.md](./SECURITY.md) for details.

## 👥 Contributing

We welcome contributions! Please follow these steps:

1. **Read** [CONTRIBUTING.md](./CONTRIBUTING.md)
2. **Check** [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)
3. **Create** a new branch: `git checkout -b feature/your-feature`
4. **Make** your changes
5. **Test** locally
6. **Submit** a pull request

Code ownership rules are defined in [CODEOWNERS](./CODEOWNERS).

## 📚 API Endpoints

### Activities

**Get all activities:**
```bash
GET /activities
```

**Get activities filtered by day and time:**
```bash
GET /activities?day=Monday&start_time=15:00&end_time=17:00
```

**Sign up for an activity:**
```bash
POST /activities/{activity_name}/signup?email=student@mergington.edu&teacher_username=teacher1
```

See [src/README.md](./src/README.md) for full API documentation.

## 🗄️ Database

The application uses **MongoDB** with two main collections:

### Activities Collection
```javascript
{
  "_id": "Chess Club",
  "description": "Learn strategies and compete in chess tournaments",
  "schedule": "Mondays and Fridays, 3:15 PM - 4:45 PM",
  "schedule_details": {
    "days": ["Monday", "Friday"],
    "start_time": "15:15",
    "end_time": "16:45"
  },
  "max_participants": 12,
  "participants": ["michael@mergington.edu", "daniel@mergington.edu"]
}
```

### Teachers Collection
```javascript
{
  "_id": "teacher1",
  "username": "teacher1",
  "password": "hashed_with_argon2",
  "display_name": "Mr. Smith",
  "role": "admin"
}
```

## 🔄 GitHub Actions Workflows

This repository includes automated workflows:

- **CodeQL Analysis** (`.github/workflows/codeql.yml`)
  - Scans JavaScript-TypeScript and Python code
  - Runs on push and pull request
  - Reports security issues

- **Dependabot** 
  - Configured in `.github/dependabot.yml`
  - Creates PRs for security and version updates

View workflow status in the **Actions** tab.

## 📖 Learning Path

Follow this path to master GitHub:

1. ✅ **Clone & Setup** - Get the app running locally
2. ✅ **Explore CodeQL** - Check Security → Code scanning
3. ✅ **Review Dependabot PRs** - Understand dependency management
4. ✅ **Read Documentation** - CODE_OF_CONDUCT, SECURITY, CONTRIBUTING
5. ✅ **Create a PR** - Make a small change and see the workflow in action
6. ✅ **Check Code Owners** - Understand CODEOWNERS file
7. ✅ **Monitor Actions** - Watch workflows run in real-time

## 🛠️ Troubleshooting

### MongoDB Connection Error
```
pymongo.errors.ServerSelectionTimeoutError
```
**Solution**: Make sure MongoDB is running
```bash
# On macOS with Homebrew
brew services start mongodb-community

# Or use Docker
docker run -d -p 27017:27017 mongo
```

### FastAPI Port Already in Use
```
Address already in use
```
**Solution**: Use a different port
```bash
python -m uvicorn src.app:app --reload --port 8001
```

### CodeQL Warnings
If you see CodeQL errors in Actions:
- Check `.github/workflows/codeql.yml`
- View error logs in the Actions tab
- Make sure supported languages are configured

## 📚 Resources

- 📖 [GitHub Skills Courses](https://skills.github.com/)
- 🔒 [CodeQL Documentation](https://codeql.github.com/)
- 🤖 [Dependabot Documentation](https://docs.github.com/en/code-security/dependabot)
- ⚡ [FastAPI Documentation](https://fastapi.tiangolo.com/)
- 🗄️ [MongoDB Documentation](https://docs.mongodb.com/)
- 🔐 [Argon2 Password Hashing](https://argon2-cffi.readthedocs.io/)

## 📝 License

This project is licensed under the [MIT License](./LICENSE).

---

**Made by** [@BytecodeBrewer](https://github.com/BytecodeBrewer)  
**Last updated**: 2025-05-09  
**Status**: 🟢 Active Learning Repository
