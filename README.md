. CI/CD Pipeline for Node.js Web App using GitHub Actions & Docker
 Tools & Technologies
GitHub – Version control and CI/CD automation

GitHub Actions – Workflow automation

Node.js – Sample web application

Docker – Containerization

DockerHub – Image registry for deployment

🔄 Workflow Overview
CI/CD pipeline is defined in .github/workflows/main.yml.
The pipeline performs the following steps automatically when you push to the main branch:

Checkout Code – Pulls the latest code from the repository.

Set up Node.js – Installs Node.js environment.

Install Dependencies – Runs npm install.

Run Tests – Executes test cases (if available).

Build Docker Image – Uses Dockerfile to build the app image.

Push to DockerHub – Uploads the image to your DockerHub repository.

🧾 How to Use
Fork/clone this repository.

Add your DockerHub credentials in GitHub:

Go to Settings > Secrets and variables > Actions

Add:

DOCKER_USERNAME

DOCKER_PASSWORD

Update main.yml with your DockerHub image name.

Push changes to the main branch.

Check Actions tab to monitor pipeline status.

📁 Project Structure
bash
Copy
Edit
.
├── .github
│   └── workflows
│       └── main.yml        # CI/CD workflow
├── Dockerfile              # Docker build instructions
├── index.js                # Sample Node.js app
├── package.json
└── README.md
📦 Sample Node.js App
A simple “Hello World” web server using Express:

js
Copy
Edit
const express = require('express');
const app = express();
const PORT = 3000;
app.get('/', (req, res) => res.send('Hello World!'));
app.listen(PORT, () => console.log(`App running on port ${PORT}`));
✅ Output
On every commit to main:

Code is tested and built.

Docker image is pushed to DockerHub.
