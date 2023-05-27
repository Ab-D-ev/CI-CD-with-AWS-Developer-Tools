# CI/CD with AWS Developer Tools

This repository contains a CI/CD project that allows you to automate the process of building, testing, and deploying your application using AWS Developer Tools.

## Getting Started

To get started with this project, follow these steps:

1. Clone the repository onto your local machine.
2. Install the necessary dependencies.
3. Configure your AWS credentials.
4. Update the configuration files to suit your needs.
5. Create 2 IAM Roles one for Ec2 and other for CodeDeploy Service.

## Dependencies

This project requires the following dependencies:

- AWS Ec2
- S3 Bucket (For Artifacts)
- CodeCommit
- CodeBuild
- CodeDeploy
- CodePipeline
- Nginx

## Configuration

To configure this project, you will need to update the following files:

- `buildspec.yml` : This file contains the build commands for the App
- `appspec.yml`: This file contains the specifications used after deployment
- `install.sh` : This script installs CodeDeploy agent for AWS in the server.
- `install_nginx.sh` : This script installs NGINX in the server
- `start_nginx.sh` : This script starts the NGINX

## How to use :

To use this project, follow these steps:

1. Push changes to your CodeCommit repository.
2. CodeCommit will check for changes and trigger a build
3. Configure the CodeBuild using the `buildspec.yml` and click ‘Start Build’
4. Configure S3 as Artifact Storage and set path as needed.
5. Configure an EC2 Instance , give IAM Permissions as per needed and Install CodeDeploy-agent from `install.sh` file
6. Configure CodeDeploy by using `appspec.yml` and deploy on the configured EC2 Instance.
7. Restart Codedeploy-agent in the instance
8. Check by simply navigating to the Public IP of the instance and fix issues if any.
9. After it is Deployed , create a pipeline in CodePipeline and make changes in the code , see if the pipeline triggers on its own.
10. Fix issues if any

## Contributing

If you would like to contribute to this project, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more information.


##Screenshots

Pipeline

![AWS-CI-CD](https://github.com/Ab-D-ev/CI-CD-with-AWS-Developer-Tools/assets/88940690/d49e0565-8771-44e4-8d14-8110e901a607)

Output 
![image](https://github.com/Ab-D-ev/CI-CD-with-AWS-Developer-Tools/assets/88940690/00447446-1f8e-4856-be31-4a85d1cc1ecc)

