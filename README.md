# MERN Stack Task Management Application with Kubernetes Deployment

A production-ready, containerized task management application built with the MERN (MongoDB, Express.js, React.js, Node.js) stack, deployed on Amazon EKS with comprehensive CI/CD pipeline implementation.

## Project Overview

This project demonstrates a complete DevOps implementation of a modern web application, featuring:

- **Three-tier architecture** with separate frontend, backend, and database layers
- **Containerized deployment** using Docker and Kubernetes
- **Automated CI/CD pipeline** with Jenkins, SonarQube, and Trivy security scanning
- **Infrastructure as Code** with Kubernetes manifests
- **Production-ready monitoring** with health checks and readiness probes
- **Security best practices** including dependency scanning and image vulnerability assessment

## Architecture

### Application Stack
- **Frontend**: React.js with Material-UI components
- **Backend**: Node.js with Express.js framework
- **Database**: MongoDB with persistent storage
- **API**: RESTful API with CRUD operations for task management

### Infrastructure Components
- **Container Orchestration**: Amazon EKS (Elastic Kubernetes Service)
- **Load Balancer**: AWS Application Load Balancer (ALB)
- **Container Registry**: Amazon ECR (Elastic Container Registry)
- **CI/CD**: Jenkins with automated pipeline stages
- **Security**: SonarQube for code quality, Trivy for vulnerability scanning
- **Monitoring**: Kubernetes health checks and readiness probes

## Features

### Task Management
- Create, read, update, and delete tasks
- Mark tasks as completed/incomplete
- Persistent data storage with MongoDB
- Real-time state management with React

### DevOps Implementation
- Automated build and deployment pipeline
- Code quality analysis with SonarQube
- Security vulnerability scanning with Trivy
- Container image scanning and validation
- Automated deployment to Kubernetes cluster

### Production Features
- Health check endpoints (`/healthz`, `/ready`, `/started`)
- Database connection monitoring
- Load balancer configuration with path-based routing
- Persistent volume management for database
- Secrets management for sensitive data

## Infrastructure Setup

The infrastructure for this project is configured using the [mern-eks-infra-setup](https://github.com/ikramuddin07/mern-eks-infra-setup) repository, which includes:

- **Amazon EKS Cluster**: Managed Kubernetes cluster with auto-scaling node groups
- **VPC Configuration**: Custom VPC with public and private subnets across multiple availability zones
- **Security Groups**: Network security rules for application and database tiers
- **IAM Roles**: Service accounts and permissions for EKS and ECR access
- **Load Balancer**: Application Load Balancer with SSL termination and path-based routing
- **Monitoring**: CloudWatch integration for logs and metrics

## Project Structure

```
mern-eks-project-code/
├── Application-Code/
│   ├── backend/                 # Node.js/Express.js API server
│   │   ├── models/             # MongoDB schemas
│   │   ├── routes/             # API endpoints
│   │   ├── Dockerfile          # Backend container configuration
│   │   └── package.json        # Backend dependencies
│   └── frontend/               # React.js client application
│       ├── src/                # React components and services
│       ├── Dockerfile          # Frontend container configuration
│       └── package.json        # Frontend dependencies
├── Kubernetes-Manifests-file/
│   ├── Backend/                # Backend deployment and service
│   ├── Frontend/               # Frontend deployment and service
│   ├── Database/               # MongoDB deployment, PVC, and secrets
│   └── ingress.yaml           # Load balancer and routing configuration
├── Jenkins-Pipeline-Code/
│   ├── Jenkinsfile-Backend     # Backend CI/CD pipeline
│   └── Jenkinsfile-Frontend    # Frontend CI/CD pipeline
└── assets/                     # Project documentation and diagrams
```

## Technology Stack

### Frontend
- **React.js 17.0.2**: Modern JavaScript library for building user interfaces
- **Material-UI 4.11.4**: React component library for consistent design
- **Axios 0.21.1**: HTTP client for API communication
- **React Scripts 4.0.3**: Build tools and development server

### Backend
- **Node.js**: JavaScript runtime environment
- **Express.js 4.17.1**: Web application framework
- **Mongoose 5.12.14**: MongoDB object modeling tool
- **CORS 2.8.5**: Cross-origin resource sharing middleware

### DevOps & Infrastructure
- **Docker**: Containerization platform
- **Kubernetes**: Container orchestration
- **Amazon EKS**: Managed Kubernetes service
- **Amazon ECR**: Container registry
- **Jenkins**: CI/CD automation server
- **SonarQube**: Code quality analysis
- **Trivy**: Security vulnerability scanner

## API Endpoints

### Task Management
- `GET /api/tasks` - Retrieve all tasks
- `POST /api/tasks` - Create a new task
- `PUT /api/tasks/:id` - Update a task
- `DELETE /api/tasks/:id` - Delete a task

### Health Monitoring
- `GET /healthz` - Basic health check
- `GET /ready` - Readiness probe with database connectivity check
- `GET /started` - Startup status check

## Deployment

### Prerequisites
- AWS CLI configured with appropriate permissions
- kubectl configured for EKS cluster access
- Docker installed and configured
- Jenkins server with required plugins

### Local Development
1. Clone the repository
2. Install dependencies for both frontend and backend
3. Configure MongoDB connection
4. Set environment variables for API endpoints
5. Run development servers

### Production Deployment
1. Infrastructure setup using the mern-eks-infra-setup repository
2. Configure Jenkins pipeline credentials
3. Deploy Kubernetes manifests
4. Configure DNS and SSL certificates
5. Monitor application health and performance

## CI/CD Pipeline

The Jenkins pipeline includes the following stages:

1. **Code Quality Analysis**: SonarQube scanning for code quality metrics
2. **Security Scanning**: Trivy file and image vulnerability assessment
3. **Container Build**: Docker image creation with best practices
4. **Registry Push**: Automated push to Amazon ECR
5. **Deployment Update**: Kubernetes manifest updates with new image tags
6. **Automated Testing**: Integration and unit test execution

## Security Features

- **Dependency Scanning**: Automated vulnerability assessment of npm packages
- **Container Security**: Image scanning for known vulnerabilities
- **Secrets Management**: Kubernetes secrets for sensitive configuration
- **Network Security**: VPC and security group configuration
- **Code Quality**: Automated code analysis and quality gates

## Monitoring and Observability

- **Health Checks**: Application-level health monitoring
- **Readiness Probes**: Database connectivity verification
- **Logging**: Centralized logging with CloudWatch
- **Metrics**: Application and infrastructure metrics collection
- **Alerting**: Automated alerting for critical issues

## Performance Optimization

- **Container Optimization**: Multi-stage Docker builds
- **Database Optimization**: MongoDB configuration for production workloads
- **Load Balancing**: Application Load Balancer with path-based routing
- **Caching**: Application-level caching strategies
- **Auto-scaling**: Kubernetes horizontal pod autoscaling

## Contributing

1. Fork the repository
2. Create a feature branch
3. Implement changes with appropriate testing
4. Ensure code quality standards are met
5. Submit a pull request with detailed description

## License

This project is licensed under the ISC License.

## Contact

For questions or contributions, please contact the project maintainer.

---

*This project demonstrates modern DevOps practices, cloud-native architecture, and production-ready application deployment using industry-standard tools and technologies.*
