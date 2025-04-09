# personal-website
This project deploys a simple Single Page Application (SPA) built with HTML using AWS App Runner and Elastic Container Registry (ECR) for containerization and storage. GitHub Actions automates the continuous integration and continuous delivery (CI/CD) process.

## Technologies Used

HTML: The foundational markup language for structuring the SPA's content, providing the base for dynamic updates driven by JavaScript.

AWS App Runner: A fully managed service that simplifies deploying and scaling containerized web applications and APIs without managing infrastructure. It handles load balancing, encryption, and auto-scaling.  

AWS Elastic Container Registry (ECR): A fully managed Docker container registry for securely storing, managing, and deploying Docker images used by AWS App Runner.

GitHub Actions: A CI/CD platform to automate building, testing, and deploying code directly from the GitHub repository, triggered by pushes to the main branch. 

## GitHub Actions Workflow Explained

This workflow, located in .github/workflows/deploy.yml, automates the deployment process to AWS App Runner.
**actions/checkout@v3**: Checks out the repository code to the runner.  
--- --- ---
**aws-actions/configure-aws-credentials@v2**: Configures AWS credentials using secrets stored in GitHub (AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, AWS_REGION).  
--- --- ---
**aws-actions/amazon-ecr-login@v1**: Logs in to the Amazon ECR registry.  
--- --- ---
**Create ECR repository if it doesn't exist**: Creates the my-website ECR repository if it doesn't already exist.  
--- --- ---
**Build and push Docker image**: Builds a Docker image from the Dockerfile in the repository and pushes it to the my-website ECR repository, tagging it with the commit SHA.  
--- --- ---
**Check if App Runner service exists**: Checks if an App Runner service named my-website already exists.  
--- --- ---
**Create IAM role for App Runner (if needed)**: Creates an IAM role named AppRunnerECRAccessRole with the necessary permissions for App Runner to access ECR if it doesn't exist.  
--- --- ---
**Create new App Runner service**: Creates a new App Runner service named my-website using the Docker image from ECR if it doesn't exist.  
--- --- ---
**Update existing App Runner service**: Updates the existing App Runner service my-website with the latest Docker image if it already exists.   