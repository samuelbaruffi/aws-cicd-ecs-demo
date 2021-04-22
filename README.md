# AWS CI/CD Pipeline For ECS Service Using Fargate

# AWS Services used
* CodeCommit
* CodeBuild
* CodePipeline
* ECR
* ECS
* Fargate
* ALB
* Cloud9 

# CI/CD
* Using CodePipeline and CodeBuild for building Docker image to AWS ECR, and then deploy to ECS Fargate cluster

# Steps to trigger CI/CD on your AWS account
* Deploy Cloudformation to your AWS Account
* Open Cloud9 IDE, and run this commands:
  * Git Clone this repo `githttps://github.com/samuelbaruffi/aws-cicd-ecs-demo.git`
  * Git Clone the CodeCommit Repot `git clone <CODE_COMMIT_REPO_HTTPS_ENDPOINT>`
  * CD inside the GitHub Repo Folder `cd aws-cicd-ecs-demo`
  * Copy files from GitHub folder to CodeCommit `cp * -a  ../PGCC-Demo-Devops/`
  * CD inside the CodeCommit Repo Folder `cd ../PGCC-Demo-Devops/`
  * Add all files to git control `git add .`
  * Commit all files `git commit -am "first commit`
  * Push all files to CodeCommit `git push`
* This will trigger CodePipeline to start
* You should in 5 mins see the changes be applied to your account:
  * Container image built and stored on ECR
  * ECS Fargate service be updated with new ECR image
  * Able to see new ALB endpoint with content
