# to-do-app-project

A simple **To-do list web application** built with **ASP.NET Core MVC** and **Entity Framework Core**, integrated with **AWS services** for authentication, database, and deployment.

This project demonstrates how to build, secure, and deploy a modern .NET web application using cloud infrastructure.

---

## ✨ Features

- User authentication with **Amazon Cognito (JWT)**
- Task management (CRUD: Create, Read, Update, Delete)
- Each user sees only their own tasks
- Dashboard with pending/overdue tasks
- Responsive UI (Bootstrap)
- Cloud-ready deployment on **AWS Elastic Beanstalk**
- Persistent database using **Amazon RDS**
- Optional: Static files hosted on **Amazon S3**, logs monitored via **CloudWatch**, and HTTPS with **Route 53 + ACM**

---

## 🏗 Architecture

```text
               +------------------+
               |      Client      |
               | (Web Browser)    |
               +--------+---------+
                        |
                        v
             +----------+-----------+
             | Elastic Beanstalk    |
             | (.NET MVC App)       |
             +----+------------+----+
                  |            |
                  |            |
                  v            v
        +---------+--+   +-----+-----------------+
        | Amazon RDS |   | Amazon Cognito       |
        | (SQL DB)   |   | (User Auth, JWT)     |
        +------------+   +----------------------+
                                |
                                v
                        +-------+-------+
                        | Authenticated |
                        | User Identity |
                        +---------------+

   [Optional extras]
       • S3 → Static Files (CSS/JS/Images)
       • CloudWatch → Logs & Monitoring
       • Route53 + ACM → Custom Domain + HTTPS