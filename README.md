# Setting up open-source microservice based applications

## Robot Shop
Link - https://github.com/instana/robot-shop

## Media Microservices
Link - https://github.com/delimitrou/DeathStarBench/tree/master/mediaMicroservices

## Train Ticket
Link - https://github.com/FudanSELab/train-ticket

# Dataset - collected from static and dynamic analysis

## Steps to collect features from tool

### Static Analysis tools
#### CodeQL
- Clone any of the above repositories
- Go to actions
- Add CodeQL
- Go to security and click on code scanning
- Use CVSS to convert labels(Critical, High, Medium, Low) into numerical scores
#### Dependabot
- Clone any of the above repositories
- Go to actions
- Add Dependabot
- Go to security and click on code scanning
- Use CVSS to convert labels(Critical, High, Medium, Low) into numerical scores
#### SonarQube
- Follow setup process from this link - https://docs.sonarsource.com/sonarqube/latest/setup-and-upgrade/install-the-server/installing-sonarqube-from-docker/
- Configure it with any of the above microservice application using docker
- Go to the dashboard and capture features like - LOC, Bugs, Vulnerabilities, etc.

### Dynamic analysis tools
#### Jaeger Tracing
- Configure jaeger tracing when building the applications
- Follow the setup process srom this link - https://docs.openshift.com/container-platform/4.11/distr_tracing/distr_tracing_jaeger/distr-tracing-jaeger-configuring.html
- This will generate a log file(trace.json), run the extract_data.ipynb file to extract *call counts*, *average duration* and *delay*

# Feature prediction

## Node feature prediction
- Run notebook files in <application-name>/feature-prediction/node folder
## Edge feature prediction
- Run notebook files in <application-name>/feature-prediction/edge folder

# Node Scoring

## Calculating vulnerability scores
- Run notebook files in <application-name>/node-scoring/training folder
## Performance analysis
### Topology-based analysis
- Run notebook files in <application-name>/node-scoring/structural-integrity folder
### Node similarity analysis
- Run notebook files in <application-name>/node-scoring/closeness-similarity folder
