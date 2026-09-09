// SIT223/753 - 7.1C Part 1 Task 1
// Mock 7-stage CI/CD pipeline. No real build/test/deploy is performed here -
// each stage only prints the task it represents and the tool that would be used,
// as instructed by the task brief.
pipeline {
    agent any

    triggers {
        // Polls GitHub for new commits every 5 minutes instead of a webhook.
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'TASK: Compile and package the application source code into a deployable artefact.'
                echo 'TOOL: Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'TASK: Run unit tests to verify individual components, then integration tests to verify components work together correctly.'
                echo 'TOOL: JUnit (unit tests) and Postman/Newman (integration tests)'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'TASK: Statically analyse the codebase for code smells, bugs, and maintainability issues against industry standards.'
                echo 'TOOL: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'TASK: Scan source code, dependencies and container images for known vulnerabilities (CVEs).'
                echo 'TOOL: Trivy'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'TASK: Deploy the built artefact to a staging environment for pre-production verification.'
                echo 'TOOL: AWS EC2 (via Ansible playbook)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'TASK: Run integration tests against the staging deployment to confirm the application behaves correctly in a production-like environment.'
                echo 'TOOL: Postman/Newman'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'TASK: Promote and deploy the verified artefact to the production environment.'
                echo 'TOOL: AWS EC2 (via Ansible playbook)'
            }
        }
    }
}
