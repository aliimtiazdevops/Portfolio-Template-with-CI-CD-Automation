
![Typing Animation](https://readme-typing-svg.herokuapp.com/?font=Righteous&color=9D4EDD&size=35&center=true&vCenter=true&width=600&height=70&duration=3000&lines=Developer+Portfolio+Template;Automated+CI/CD+Deployment;Jenkins+%26+GitHub+Webhooks;)
---
### **DevOps Engineer | CI/CD | Jenkins | GitHub Webhooks | GitHub Pages**

This **Developer Portfolio Template** is a responsive static website designed to showcase developer skills and projects.  
It uses **Jenkins CI/CD** and **GitHub webhooks** for automated deployment to **GitHub Pages** — ensuring every push to `main` triggers instant updates.  

---

## ⚙️ Features
- 🔄 Automated deployment via Jenkins CI/CD pipeline & GitHub webhook triggers  
- 📱 Responsive design for mobile & desktop  
- 🧭 Fixed header with hamburger menu  
- 💼 Project case studies for E-commerce, Task Management, and Portfolio sites  
- ✉️ Contact form (requires backend integration)  
- 🌐 Social media integration (LinkedIn, GitHub, Twitter, YouTube, Instagram)

---

## 🧰 Technologies Used
- **Jenkins** – CI/CD automation  
- **GitHub Webhooks** – Trigger pipelines on push events  
- **GitHub Pages** – Static hosting  
- **Git** – Version control  
- **Frontend:** HTML5, CSS3 (SASS), JavaScript, React, TypeScript, Tailwind CSS    

---

## 🗂️ Project Structure
```plaintext
├── assets
│   ├── jpeg/project-mockup-example.jpeg
│   ├── png/linkedin-ico.png, github-ico.png, twitter-ico.png, yt-ico.png, insta-ico.png
│   └── svg/common-bg.svg, ham-menu.svg, ham-menu-close.svg
├── css/style.css
├── index.html
├── index.js
├── project-1.html
├── project-2.html
├── project-3.html
├── Jenkinsfile
└── README.md
```

---

## 🧩 Jenkinsfile (CI/CD Pipeline)
```groovy
pipeline {
    agent any
    environment {
        GIT_CREDENTIALS_ID = 'your-github-credentials-id'
        REPO_URL = 'https://github.com/aliimtiazdevops/Portfolio-Template-with-CI-CD-Automation'
        BRANCH = 'main'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: "*/${BRANCH}"]],
                    userRemoteConfigs: [[url: "${REPO_URL}", credentialsId: "${GIT_CREDENTIALS_ID}"]]
                ])
            }
        }
        stage('Validate') {
            steps {
                echo 'Validating HTML, CSS, and JS...'
            }
        }
        stage('Deploy to GitHub Pages') {
            steps {
                echo 'Deploying site...'
                bat 'npm install -g gh-pages'
                bat 'gh-pages -d .'
            }
        }
    }
    post {
        success {
            echo 'Site deployed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
```

---

## 🧱 File Overview
- **index.html** → Main portfolio page (Home, About, Projects, Contact)  
- **project-\*.html** → Case study pages  
- **css/style.css** → Responsive styling  
- **index.js** → Mobile navigation logic  
- **Jenkinsfile** → CI/CD automation  
- **assets/** → Images, icons, SVGs  

---

## ⚡ Setup
```bash
git clone https://github.com/aliimtiazdevops/Portfolio-Template-with-CI-CD-Automation.git
cd Portfolio-Template-with-CI-CD-Automation
```

---

## 💻 Run Locally
```bash
npm install -g live-server
live-server .
```

---

## 🧩 CI/CD Setup
1. Install **Jenkins** and the **GitHub plugin**.  
2. Set GitHub webhook → `http://<jenkins-url>/github-webhook/` for `main` branch pushes.  
3. Update Jenkinsfile with your credentials and repo URL.  
4. Push to `main` → automatic deployment.  

---

## 🧠 Usage
- Edit `index.html`, `project-*.html`, and `style.css` for customization.  
- Update your social media links.  
- Push to main → Jenkins auto-deploys.  

---

## 📬 Contact
- **Email:** aliimtiaz.dev@gmail.com  
- **GitHub:** (https://www.linkedin.com/in/ali-imtiaz1/)

---


🧑‍💻 *Deployed by Ali Imtiaz, DevOps Engineer*
