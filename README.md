# 🚀 Django Project

## 📌 Project Overview
This is a **Django-based web application** that demonstrates fundamental concepts such as **class-based views (CBV), URL routing, templates, and testing.**

## 📜 Table of Contents
- [🛠 Installation](#installation)
- [📂 Project Structure](#project-structure)
- [📌 Usage](#usage)
- [✨ Features](#features)
- [📖 Code Explanation](#code-explanation)
- [🔧 Git Commands](#git-commands)
- [⚙ Django Commands](#django-commands)
- [📜 License](#license)

---

## 🛠 Installation
To set up this project, follow these steps:

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Amin-moniry-pr7/DJANGO_CODES.git
   cd DJANGO_CODES
   ```

2. **Create and Activate Virtual Environment**
   - **Windows:**
     ```bash
     python -m venv .amin
     .amin\Scripts\Activate
     ```
   - **Mac/Linux:**
     ```bash
     python3 -m venv .amin
     source .amin/bin/activate
     ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run Migrations**
   ```bash
   python manage.py migrate
   ```

5. **Start the Development Server**
   ```bash
   python manage.py runserver
   ```

---

## 📂 Project Structure
```
Django_Project/
│── 📁 Amin_message/       # Django App
│   ├── 📁 migrations/     # Database Migrations
│   ├── 📁 templates/      # HTML Templates
│   ├── 📜 urls.py         # URL Routing
│   ├── 📜 views.py        # View Functions
│── 📁 config_amin/        # Django Project Config
│   ├── ⚙ settings.py      # Project Settings
│   ├── 📜 urls.py         # Main URL Config
│── 📁 templates/          # Global Templates
│── 🔧 manage.py           # Django Management Script
```

---

## 📌 Usage
Once the server is running, open your browser and visit:
```
http://127.0.0.1:8000/
```
You should see a **Welcome Message** rendered from the **home.html** template.

---

## ✨ Features
✅ **Class-Based Views (CBV)** for better structure.
✅ **Template Rendering** to dynamically display content.
✅ **URL Routing** for navigation.
✅ **Unit Testing** to ensure application stability.

---

## 📖 Code Explanation
### 📝 **1. Views (views.py)**
This project uses **Class-Based Views (CBV)** instead of **Function-Based Views (FBV)** for better scalability:
```python
from django.views.generic import TemplateView

class MessageView(TemplateView):
    template_name = 'home.html'
```

### 🔗 **2. URL Routing (urls.py)**
The URL configuration routes the base URL to the **MessageView**:
```python
from django.urls import path
from .views import MessageView

urlpatterns = [
    path('', MessageView.as_view(), name='Amin_message'),
]
```

### 🎨 **3. Templates (home.html)**
The template extends a base layout and renders a **Welcome Message**:
```html
{% extends 'base.html' %}

{% block content %}
    <h1><b><i>🎉 WELCOME TO OUR SITE 🎉</i></b></h1>
    <small>In this site, you can learn <strong>HTML & CSS</strong>.</small>
{% endblock content %}
```

### 🧪 **4. Testing (tests.py)**
Unit test to check if the correct template is rendered:
```python
from django.test import TestCase
from django.urls import reverse

class TemplateTestCase(TestCase):
    def test_contains_correct_template(self):
        response = self.client.get(reverse('Amin_message'))
        self.assertContains(response, '<h1><b><i>🎉 WELCOME TO OUR SITE 🎉</i></b></h1>')
```

---

## 🔧 Git Commands
To set up a Git repository and push changes:
```bash
🚀 git init
📌 git add *
📝 git commit -m "Django_Project"
🔗 git remote add amin "repository_address"
⬆ git push amin master
```

---

## ⚙ Django Commands
- **Check Django version:**
  ```bash
  python -m django --version
  ```
- **Create a new Django project:**
  ```bash
  python -m django startproject config_amin
  ```
- **Run the development server:**
  ```bash
  python manage.py runserver
  ```

---

## 🆚 Function-Based Views (FBV) vs. Class-Based Views (CBV)
- **FBV (Function-Based Views)** are simple and easy to understand but can become difficult to manage in large applications.
- **CBV (Class-Based Views)** provide better modularity and reusability.
- In this project, **CBV is used**, but in some cases, **FBV might be better** for simple views.

---

## 📜 License
🔖 This project is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International License.**

```
Copyright (c) 2025 Amin Moniry
You are free to use and modify this code for non-commercial purposes.
```

---

✨ **Happy Coding!** 🚀🎉

