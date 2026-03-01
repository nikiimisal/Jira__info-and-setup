<h1 align="center">Jira</h1>

> Previously, we explored monitoring tools like Prometheus and Grafana.
>  
> Now, we will explore Jira — a powerful project management and issue tracking tool widely used in DevOps and Agile environments.
>
> 👉 Jira = Project & Issue Management  
> 👉 DevOps = Planning + Tracking + Delivery  

---

- [About Jira](#about-jira)
- [Jira Architecture](#jira-architecture)
- [Jira in DevOps Workflow](#jira-in-devops-workflow)
- [Jira Installation (Linux Server Setup)](#jira-installation)
- [Creating First Project](#creating-first-project)
- [Conclusion](#conclusion)

---

<p align="center">
  <img src="https://wac-cdn.atlassian.com/dam/jcr:8c2c1f9e-1c8e-4b0e-b7cb-0dfc2c1d9b77/Jira-logo-blue.svg" width="300" alt="Jira Logo">
</p>

---

<a id="about-jira"></a>

## 1️⃣ About Jira

Jira is a project management and issue tracking tool developed by Atlassian.

It is widely used in:

- Agile Development
- DevOps workflows
- Bug tracking
- Sprint planning
- Release management

Jira helps teams:

- Create tasks (Issues)
- Assign work
- Track progress
- Manage sprints
- Monitor release cycles

---

### Key Facts

- Initial Release: 2002
- Developer: Atlassian
- License: Proprietary (Cloud & Self-hosted)
- Primary Purpose: Issue Tracking & Project Management

---

### What Jira Does

✔ Tracks bugs  
✔ Manages user stories  
✔ Sprint planning  
✔ Kanban boards  
✔ Scrum boards  
✔ Workflow automation  
✔ Reporting & analytics  

Jira does NOT deploy applications.  
Jira does NOT monitor infrastructure.  

It manages work and tracks development lifecycle.

---

<a id="jira-architecture"></a>

## 2️⃣ Jira Architecture

Jira works as a web-based application.

---

### Flow:

```
User → Browser → Jira Server → Database
```

---

### Components:

1. **Frontend** → Web Interface  
2. **Backend** → Jira Application  
3. **Database** → Stores project data  
4. **Optional** → SMTP (Email Notifications)

---

### Database Support:

- PostgreSQL
- MySQL
- Oracle
- Microsoft SQL Server

---

### Deployment Types:

1️⃣ Jira Cloud (Managed by Atlassian)  
2️⃣ Jira Server (Self-hosted)  
3️⃣ Jira Data Center (Enterprise Cluster Setup)

For learning & DevOps practice → Server installation is recommended.

---

<a id="jira-in-devops-workflow"></a>

## 3️⃣ Jira in DevOps Workflow

Jira plays a major role in DevOps lifecycle.

---

### DevOps Flow:

```
Requirement → Jira Issue → Development → CI/CD → Deployment → Monitoring
```

---

Example:

1. Product team creates a requirement.
2. Issue is created in Jira.
3. Developer works on that issue.
4. Code pushed to GitHub.
5. Jenkins pipeline runs.
6. Application deployed.
7. Monitoring tools observe performance.

> Even in the Free Tier, we can create Scrum projects, manage sprints, track bugs, and assign tasks to team members.

Jira integrates with:

- GitHub
- Bitbucket
- Jenkins
- Slack
- Docker
- Kubernetes

Jira is the planning and tracking layer of DevOps.

---

---

# 🔹 Jira Cloud Free Workflow (Recommended for Freshers / Students)

> As a fresher or student, we usually do not use Jira paid (Data Center) version.
> The Free Tier is enough to understand dashboards, teams, sprints, backlogs, and task tracking.

---

### Step 1: Create Account on Official Website

Go to:

https://www.atlassian.com/software/jira

Click **Get it free** and sign up.

During signup:

> Select **Software Development** because it enables Scrum boards, sprint management, backlog tracking, and task workflows.

Next screen:  
“How does your team work in Jira?”

Select:

- Work in Scrum  
- Run Sprints  
- Track Bugs  
- Manage Tasks  

This enables Agile project features.

---

### Step 2: Create Team

After Jira web page opens:

Left side → Scroll down → Click **Teams**

Click:

```
Create new team
```

> Creating a team ensures proper access control and issue assignment.

Add team members by entering their email IDs.

They will receive invitation mail.

They must click:

```
Accept Invitation
```

Now team setup is complete.

---

### Step 3: Open Your Project

At top, you will see your project name  
(Example: “My Software Team”)

Click that project.

Select:

```
Scrum Project
```

Now go to:

```
Backlog
```

---

### Step 4: Create Tasks in Backlog

Click:

```
Create Issue
```

Example tasks:

- Create EC2 Instance  
- Create VPC  
- Create RDS  
- Deploy Application  

---

### Step 5: Assign Task

In issue window:

Click **Assignee**

You will see team member names.

Select member.

Set:

- Due Date  
- Priority  
- Time estimation  

Now task is assigned.

---

### Step 6: Board View

Click:

```
Board
```

You will see workflow:

```
To Do → In Progress → Done
```

You can drag & drop tasks.

> In Free Tier, we can create sprints, assign tasks, add subtasks, and track progress using boards.

You can also:

✔ Add Subtasks  
✔ Add Labels  
✔ Track who completed what  
✔ Monitor sprint progress  

---

### Step 7: Sprint Creation

Go to:

```
Backlog → Create Sprint
```

Move tasks into sprint.

Click:

```
Start Sprint
```

Now sprint tracking begins.

---

### Step 8: Dashboard Understanding

Go to main menu → Click **Dashboards**

> Even in the Free Tier, dashboards help visualize assigned issues, sprint progress, and team activity.

Dashboard shows:

- Task status  
- Sprint completion  
- Assigned work  
- Work distribution  

For beginners, understanding dashboard workflow is very important.

---


<a id="jira-installation"></a>

## 4️⃣ Jira Installation (Linux Server Setup)

⚠ Always refer to official documentation for latest version.

For learning, we install Jira Server on Ubuntu EC2 instance.

---

### Step 1: Launch EC2 Instance

Open inbound ports:

| Port | Purpose |
|------|----------|
| 8080 | Jira Web Access |

Source:
```
0.0.0.0/0
```

---

### Step 2: Install Java (Required)

```bash
sudo apt update
sudo apt install openjdk-11-jdk -y
```

Check Java version:

```bash
java -version
```

---

### Step 3: Download Jira

Go to:
https://www.atlassian.com/software/jira/download

On server:

```bash
wget https://product-downloads.atlassian.com/software/jira/downloads/atlassian-jira-software-X.X.X-x64.bin
```

Make executable:

```bash
chmod +x atlassian-jira-software-X.X.X-x64.bin
```

Run installer:

```bash
sudo ./atlassian-jira-software-X.X.X-x64.bin
```

Follow installation wizard.

---

### Step 4: Start Jira

```bash
sudo /etc/init.d/jira start
```

Access in browser:

```
http://YOUR_PUBLIC_IP:8080
```

---

### Step 5: Setup Wizard

- Choose “Set up for me”
- Configure database
- Create admin user
- Complete setup

Jira is now installed successfully.

---

<a id="creating-first-project"></a>

## 5️⃣ Creating First Project

After login:

1. Click “Projects”
2. Click “Create Project”
3. Choose:
   - Scrum template
   - Kanban template
4. Enter project name
5. Create

---

### Create Issue

Click “Create”

Types of issues:

- Story
- Task
- Bug
- Epic

Assign issue to developer and track status:

To Do → In Progress → Done

---

### Boards

Scrum Board → Sprint based  
Kanban Board → Continuous workflow  

---

### Workflow Example:

```
To Do → In Progress → Code Review → Testing → Done
```

Jira helps visualize workflow clearly.

---

<a id="conclusion"></a>

## ✅ Conclusion

Jira is a powerful issue tracking and project management platform.

It helps teams:

- Plan work
- Track progress
- Manage sprints
- Integrate with DevOps tools
- Improve collaboration

---

### Final Understanding

Jira = Planning & Tracking  
GitHub = Code Management  
Jenkins = CI/CD Automation  
Docker/Kubernetes = Deployment  
Prometheus/Grafana = Monitoring  

Together → Complete DevOps Lifecycle

---

### 🎯 Most Important Skill in Jira

✔ Understanding workflows  
✔ Proper issue creation  
✔ Sprint planning  
✔ Integrations with CI/CD  
✔ Logical project structure  

Because tools are powerful only when configured properly.

---

🚀 Now your DevOps stack includes:

✔ Planning (Jira)  
✔ Version Control (GitHub)  
✔ CI/CD (Jenkins)  
✔ Containerization (Docker)  
✔ Monitoring (Prometheus + Grafana)  

Production-ready DevOps foundation complete.
