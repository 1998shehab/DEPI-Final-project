# Depi-Recommendation
 A simple distributed application running with an Automated Deployment Pipeline using Jenkins, Docker, Docker Compose, Ansible, and AWS.

## Architecture

![napkin-selection (7)](https://github.com/user-attachments/assets/d5fff263-926b-4045-9dec-a51512bc02d5)

* A front-end web app in [Python](/vote) which lets you vote between two options
* A [Redis](https://hub.docker.com/_/redis/) which collects new votes
* A [.NET](/worker/) worker which consumes votes and stores them in…
* A [Postgres](https://hub.docker.com/_/postgres/) database backed by a Docker volume
* A [Node.js](/result) web app which shows the results of the voting in real time

## Technologies Used 
1. **Docker**: Containerizes the backend and frontend applications for isolated and consistent environments.
2. **Jenkins**: Manages the CI/CD pipeline to automate builds, tests, and deployments.
3. **Ansible**: Automates server setup and deployment tasks. 
3. **Docker Compose**: Orchestrates multi-container Docker applications, simplifying the deployment process without Kubernetes. 
3. **AWS**: Provides cloud infrastructure for hosting the application.

## CI/CD Process 
### The updated deployment pipeline includes:
- **`Jenkins`**: Automated build and deployment process. 
- **`Docker`**: Containerization of the backend and frontend applications. 
- **`Docker Compose`**: Runs multi-container applications run smoothly. 
- **`Ansible`**: Automates server setup, Docker installation, and deployment of the app using Docker Compose on AWS. 
- **`AWS (EC2 instance)`**: Hosts the Docker containers using Docker Compose for orchestration.
  
![napkin-selection (3)](https://github.com/user-attachments/assets/8f461cd6-56a5-41df-a904-8a4e6e593141)


## Getting Started 
### Prerequisites To set up and run this project, you will need the following:

- Docker and Docker Compose installed on your local machine.
- Jenkins installed and running (either locally or on a server). 
- Ansible installed on the Jenkins server. 
- AWS account with EC2.

  For detailed deployment steps: Please, check the Requirements.md file.

## Deployment Process 
### Jenkins Pipeline Setup 
#### The pipeline is managed via Jenkins and includes the following stages:

1. Checkout code: Fetches the latest version of code from the Git repository.

2. Build Docker images: Builds Docker images for frontend, worker, and backend applications.

3. Push Docker images: Pushes the built images to Docker Hub.

4. Deploy with Ansible: Ansible Configures EC2 instances, sets up Docker, and deploys the application using Docker Compose.

## Security Measures 
### The following security practices are applied:

- Jenkins Credentials: Stores Passwords Securely.
- SSH Keys: Only SSH key-based authentication is allowed for server access.

## Contributing
We welcome contributions to improve this project.
### Please follow these steps:

- Fork the repository.
- Create a feature branch. Commit your changes. 
- Push the branch to your fork. 
- Open a pull request.
