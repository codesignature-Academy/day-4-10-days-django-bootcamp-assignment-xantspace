# Django Models and Database Assignment

## Assignment Overview
In this assignment, you will practice creating Django models and working with the database layer. You'll define models, create migrations, and successfully run migrations to set up the database schema for your application.

## Learning Objectives
- Create Django models with appropriate fields and relationships
- Understand field types and constraints in Django models
- Run `makemigrations` to generate migration files
- Run `migrate` to apply migrations to the database
- Register models in the Django admin interface

---

## Setup Instructions

### Step 1: Clone the Repository
Clone the repository to your local machine:
```bash
git clone <repository-url>
```

### Step 2: Navigate to the Project Directory
Change into the project directory:
```bash
cd day-4-assignment
```

### Step 3: Install Dependencies
Ensure the required Python packages are installed:
```bash
pip install -r requirements.txt
```

---

## Assignment Tasks

### Task 1: Create Book Model

#### 1.1 Define Book Model in `myapp/models.py`
Create a Book model in your Django application:

```python
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=200)
    author = models.CharField(max_length=100)
    published_date = models.DateField()
    pages = models.IntegerField()
    isbn = models.CharField(max_length=13)
    description = models.TextField()
```

#### 1.2 Model Requirements
Ensure your model has:
- `title` field as CharField with max_length=200
- `author` field as CharField with max_length=100
- `published_date` field as DateField
- `pages` field as IntegerField
- `isbn` field as CharField with max_length=13
- `description` field as TextField

---

### Task 2: Make Migrations

#### 2.1 Generate Migration Files
Create migration files based on your Book model definition:
```bash
python manage.py makemigrations
```

You should see output like:
```
Migrations for 'myapp':
  myapp/migrations/0001_initial.py
    - Create model Book
```

---

## Submission Checklist

- [ ] Book model created in `myapp/models.py` with all required fields
- [ ] `makemigrations` command runs successfully without errors
- [ ] `migrate` command runs successfully and applies all migrations
- [ ] Database tables created successfully
- [ ] Changes committed and pushed to GitHub

---

### Task 3: Migrate to Database

#### 3.1 Apply Migrations
Run the migrations to create the database tables:
```bash
python manage.py migrate
```

You should see output indicating successful migration:
```
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, myapp, sessions
Running migrations:
  Applying myapp.0001_initial... OK
```

---

### Task 4: Push to GitHub

#### 4.1 Check Git Status
View the changes you've made:
```bash
git status
```

#### 4.2 Stage Changes
Add your changes to the staging area:
```bash
git add .
```

#### 4.3 Commit Changes
Commit your changes with a descriptive message:
```bash
git commit -m "Add Book model with migrations"
```

#### 4.4 Push to GitHub
Push your changes to the remote repository:
```bash
git push origin main
```

---

## Key Concepts

### Django Models
- Models are Python classes that define the structure of database tables
- Each model corresponds to a single database table
- Model fields define the columns in the table

### Field Types
- `CharField`: String field with maximum length requirement
- `TextField`: Larger text field without maximum length
- `DateField`: Date field (YYYY-MM-DD format)
- `IntegerField`: Integer field

### Migrations
- Migrations are version control for your database schema
- `makemigrations` detects changes in your models and creates migration files
- `migrate` applies those migrations to the database
- Migrations allow you to track schema changes over time

---

## Troubleshooting

**Issue: No changes detected when running makemigrations**
- Ensure your models are defined in `models.py`
- Check that your app is included in `INSTALLED_APPS` in `settings.py`

**Issue: Migration errors**
- Delete problematic migration files and start fresh
- Ensure all model field definitions are correct
- Check for syntax errors in `models.py`

**Issue: Database locked error**
- Stop the development server and try migrating again
- If error persists, delete `db.sqlite3` and run migrations from scratch

---

## Summary

By completing this assignment, you will have:
1. ✓ Created a Django Book model with appropriate fields
2. ✓ Generated migrations using `makemigrations`
3. ✓ Applied migrations successfully using `migrate`
4. ✓ Pushed your code to GitHub
5. ✓ Understood the Django ORM and database schema design

Happy coding! 🚀
