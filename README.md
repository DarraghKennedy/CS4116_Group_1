# CS4116_Group_1
# CS4116_Group_1 - Business Service Marketplace

## 1. Introduction
This project involves developing a business service marketplace where businesses can advertise their services, and users can connect with businesses to negotiate and arrange services. The project will be built using HTML, CSS, Bootstrap, PHP, and MySQL.

## 2. Technical Specification

### 2.1 Simplified Technology Stack
- **Frontend**: Bootstrap 5 with basic CSS
- **JavaScript**: Vanilla JS for interactivity
- **Backend**: PHP with MySQL
- **Search**: Basic SQL search with filters
- **Email**: PHP mail() function for basic notifications

### 2.2 Simplified Database Schema
```sql
CREATE TABLE Users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password_hash VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE Coaches (
    coach_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    expertise VARCHAR(255),
    availability TEXT,
    FOREIGN KEY (user_id) REFERENCES Users(user_id)
);

CREATE TABLE Sessions (
    session_id INT PRIMARY KEY AUTO_INCREMENT,
    learner_id INT,
    coach_id INT,
    scheduled_time DATETIME,
    status ENUM('scheduled', 'completed', 'cancelled'),
    FOREIGN KEY (learner_id) REFERENCES Users(user_id),
    FOREIGN KEY (coach_id) REFERENCES Coaches(coach_id)
);
```

### 2.3 Core API Endpoints
```php
// User Authentication
POST /auth/login
POST /auth/register

// Session Management
POST /sessions
GET /sessions/{user_id}

// Search
GET /search?q={query}
```

### 2.4 Core Features Implementation

#### 2.4.1 User Registration and Profiles
- Basic registration form
- Simple profile pages
- Role-based access (learner/coach)

#### 2.4.2 Search and Matching
- Basic search by expertise
- Simple filtering by availability

#### 2.4.3 Booking and Scheduling
- Basic calendar interface
- Simple session management
- Email notifications using PHP mail()

#### 2.4.4 Communication Tools
- Basic messaging system
- External video links (e.g., Zoom/Google Meet)

#### 2.4.5 Payment Processing
- Mock payment system
- Simple session tracking

#### 2.4.6 Review and Rating System
- Basic star rating system
- Simple review submission

### 2.5 Security Measures
- Basic input validation
- Password hashing
- Session management

### 2.6 Testing Requirements
- Basic functionality testing
- Cross-browser testing (Chrome, Firefox)
- Database integrity checks

### 2.7 Deployment Strategy
- Simple shared hosting
- Basic database backup
- Manual deployment process

## 3. Simplified Project Timeline
1. Week 1: Requirements & Database Design
2. Week 2: User Registration & Profiles
3. Week 3: Search & Booking System
4. Week 4: Messaging & Reviews
5. Week 5: Testing & Final Touches

## 4. Team Responsibilities
1. Frontend Development: [Name]
2. Backend Development: [Name]
3. Database & API: [Name]
4. Testing & Documentation: [Name]

## 5. Additional Features (Optional)
- AI-driven recommendations
- Advanced search filters
- Payment system integration
- Mobile responsiveness

## 6. Getting Started Guide

### 6.1 Initial Setup
1. **Set up version control**:
   - Create a GitHub repository
   - Set up .gitignore for PHP projects
   - Create main and development branches

2. **Local development environment**:
   - Install XAMPP/WAMP for PHP and MySQL
   - Set up database connection
   - Create basic project structure:
     ```
     /project
     ├── assets/
     │   ├── css/
     │   ├── js/
     │   └── images/
     ├── includes/
     ├── pages/
     └── index.php
     ```

### 6.2 First Week Tasks
1. **Database Setup**:
   - Create database schema
   - Populate with sample data
   - Write basic CRUD operations

2. **User Authentication**:
   - Create login/register forms
   - Implement basic session management
   - Add role-based access control

3. **Basic Frontend**:
   - Set up Bootstrap template
   - Create navigation bar
   - Add basic styling

### 6.3 Development Workflow
1. **Daily Standups**:
   - 15-minute meetings to discuss progress
   - Identify blockers
   - Assign tasks for the day

2. **Task Breakdown**:
   - Frontend: [Name] - Focus on UI components
   - Backend: [Name] - Work on API endpoints
   - Database: [Name] - Manage schema and queries
   - Testing: [Name] - Write test cases and documentation

3. **Code Reviews**:
   - Review each other's pull requests
   - Maintain coding standards
   - Ensure security best practices

### 6.4 Recommended Tools
- **Version Control**: GitHub
- **Project Management**: Trello or GitHub Projects
- **Communication**: Discord or Slack
- **Code Editor**: VS Code with PHP extensions

### 6.5 Milestones
1. **Week 1**: Basic authentication and user profiles
2. **Week 2**: Search functionality and coach listings
3. **Week 3**: Booking system and session management
4. **Week 4**: Messaging and review system
5. **Week 5**: Final testing and deployment

## 7. Branching Strategy

### 7.1 Branch Overview
- **main**: Stable production-ready code
- **Todor-dev**: Todor's development branch
- **Fionn-dev**: Fionn's development branch
- **Darragh-dev**: Darragh's development branch
- **Rian-dev**: Rian's development branch

### 7.2 Daily Workflow

#### Starting Work
```bash
# Switch to main branch and get latest changes
git checkout main
git pull origin main

# Switch to your development branch
git checkout YourName-dev

# Merge latest changes from main
git merge main
```

#### Making Changes
```bash
# Stage your changes
git add .

# Commit with a descriptive message
git commit -m "Brief description of changes"

# Push to your remote branch
git push origin YourName-dev
```

### 7.3 Creating a Pull Request
1. Complete your feature
2. Push final changes
3. On GitHub:
   - Go to "Pull Requests"
   - Click "New Pull Request"
   - Select `YourName-dev` as the source branch
   - Select `main` as the target branch
   - Add a clear description of changes
   - Request review from team members

### 7.4 Reviewing a Pull Request
1. Review the code changes
2. Add comments for improvements if needed
3. Approve when changes meet quality standards
4. Author merges the PR after approval

### 7.5 After Merging
```bash
# Switch to main and pull latest changes
git checkout main
git pull origin main

# Update your development branch
git checkout YourName-dev
git merge main
```

### 7.6 Resolving Merge Conflicts
1. When conflicts occur during merge:
```bash
# Open affected files
# Look for conflict markers (<<<<<<<, =======, >>>>>>>)
# Resolve conflicts by choosing correct changes
# Remove conflict markers

# After resolving:
git add .
git commit -m "Resolved merge conflicts"
```

### 7.7 Best Practices
1. Commit often with clear messages
2. Keep your branch updated with main
3. Test before creating PRs
4. Review others' code thoroughly
5. Delete merged feature branches
6. Communicate about major changes

### 7.8 Common Commands
```bash
# Check current branch
git branch

# View commit history
git log

# Discard local changes
git checkout -- .

# Stash changes temporarily
git stash
git stash pop
```
