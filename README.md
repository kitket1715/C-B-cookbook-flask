# Online Cookbook

An interactive recipe-sharing platform for home cooks and chefs. Users can browse, add, edit, and delete recipes while exploring featured kitchen tools.

## 🚀 Project Goals

- **User goal**: Find and share creative recipes.
- **Site owner goal**: Promote a brand of cooking tools.

## 🎯 Features

- Add, edit, delete, and view detailed recipes (CRUD)
- Include ingredients, steps, cuisine type, and recipe images
- Filtered recipe list and individual detail pages
- Image fallback for missing pictures
- Tool promotion page (nice-to-have)
- Dashboard with recipe statistics using Chart.js
- Export dashboard reports as PDF and CSV in ZIP
- Responsive and accessible UI using Bootstrap

## 🗂️ Tech Stack

- Python + Flask
- HTML, CSS, Bootstrap
- PostgreSQL (or SQLite for dev)
- WTForms, SQLAlchemy
- Chart.js for dashboard
- Hosted on Heroku

## 🗃️ Data Model

### Tables

- `Recipe`: title, ingredients, steps, cuisine, image_url, is_featured
- `Tool`: name, image, brand_url
- `RecipeTool`: link between recipes and tools (many-to-many)

## 🧪 Testing

- Manual testing performed across all CRUD routes and forms
- Validation for all input fields
- UI tested on desktop and mobile
- Custom color scheme: red, black, gold, white

## 🔐 Security

- `.env` file used to store `SECRET_KEY` and DB URI
- `.gitignore` protects secrets from version control
- No credentials or debug code in repo

## 🛠️ Deployment

### 🔧 Prerequisites
- Git
- Heroku CLI
- Python 3

### 📤 Deployment Steps

```bash
# Create virtual environment and install dependencies
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt

# Run locally
export FLASK_APP=run.py  # or set FLASK_APP=run.py on Windows
flask run

# Initialize Git and deploy
git init
git add .
git commit -m "Initial commit"
heroku login
heroku create online-cookbook-app-name
heroku addons:create heroku-postgresql:hobby-dev
heroku config:set SECRET_KEY='yoursecretkey'
git push heroku main  # or 'master' if using master
heroku open

# Migrate database if needed
heroku run flask db upgrade
```

## 🧭 UX & Design

- Responsive design with Bootstrap
- Clear information hierarchy
- Accessible forms and feedback
- Fallback images ensure visual consistency

## 📸 Screenshots

Add screenshots of:
- Home page
- Add recipe form
- Recipe list and detail
- Dashboard
- Tools page

## 📥 Dashboard Export Feature

- From the dashboard, users can click a button to download statistics
- ZIP file contains:
  - `recipe_stats.csv`: cuisine breakdown
  - `recipe_dashboard.pdf`: total/featured summaries

## 📦 How to Run Locally

```bash
git clone https://github.com/Kitket1715/online-cookbook.git
cd online-cookbook
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
flask run
```

## 🤝 Attribution

- Chart.js from https://www.chartjs.org/
- Bootstrap from https://getbootstrap.com/
- Default image via placeholder.com
- Code snippets noted where reused (comments + links)

## 📌 License

MIT License or custom license info.
