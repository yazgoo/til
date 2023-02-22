
## running pipelines locally

https://github.com/jenkinsci/jenkinsfile-runner

```Dockerfile
ARG baseImage=jenkins/jenkins:2.346.3-lts-jdk11

# Load the JFR docker image
FROM jenkins/jenkinsfile-runner:latest as jfr

# Lets configure our Jenkins image
FROM ${baseImage}

# This installs the "Pipeline" plugins
RUN jenkins-plugin-cli --plugins \
      ace-editor \
      ansicolor \
      apache-httpcomponents-client-4-api \
      authentication-tokens \
      authorize-project \
      azure-ad \
      azure-credentials \
      azure-sdk \
      azure-vm-agents \
      blueocean \
      blueocean-autofavorite \
      blueocean-bitbucket-pipeline \
      blueocean-commons \
      blueocean-config \
      blueocean-core-js \
      blueocean-dashboard \
      blueocean-display-url \
      blueocean-events \
      blueocean-github-pipeline \
      blueocean-git-pipeline \
      blueocean-i18n \
      blueocean-jwt \
      blueocean-personalization \
      blueocean-pipeline-api-impl \
      blueocean-pipeline-editor \
      blueocean-pipeline-scm-api \
      blueocean-rest \
      blueocean-rest-impl \
      blueocean-web \
      bootstrap4-api \
      branch-api \
      caffeine-api \
      checks-api \
      cloudbees-bitbucket-branch-source \
      cloudbees-folder \
      cloud-stats \
      configuration-as-code \
      credentials \
      credentials-binding \
      dark-theme \
      disable-github-multibranch-status \
      display-url-api \
      durable-task \
      echarts-api \
      email-ext \
      embeddable-build-status \
      extended-read-permission \
      favorite \
      font-awesome-api \
      git \
      git-client \
      github \
      github-api \
      github-branch-source \
      github-checks \
      github-label-filter \
      github-scm-trait-notification-context \
      git-server \
      handy-uri-templates-2-api \
      htmlpublisher \
      jackson2-api \
      jenkins-design-language \
      jjwt-api \
      job-dsl \
      jquery3-api \
      jsch \
      junit \
      kubernetes \
      kubernetes-client-api \
      kubernetes-credentials \
      lockable-resources \
      mailer \
      matrix-auth \
      matrix-project \
      mercurial \
      metrics \
      Office-365-Connector \
      okhttp-api \
      pipeline-build-step \
      pipeline-github \
      pipeline-graph-analysis \
      pipeline-input-step \
      pipeline-milestone-step \
      pipeline-model-api \
      pipeline-model-definition \
      pipeline-model-extensions \
      pipeline-stage-step \
      pipeline-stage-tags-metadata \
      pipeline-utility-steps \
      plain-credentials \
      plugin-util-api \
      popper-api \
      pubsub-light \
      role-strategy \
      scm-api \
      script-security \
      snakeyaml-api \
      sse-gateway \
      ssh-credentials \
      structs \
      theme-manager \
      timestamper \
      token-macro \
      trilead-api \
      variant \
      workflow-api \
      workflow-basic-steps \
      workflow-cps \
      workflow-cps-global-lib \
      workflow-durable-task-step \
      workflow-job \
      workflow-multibranch \
      workflow-scm-step \
      workflow-step-api \
      workflow-support

# Now lets turn our existing docker container into a JFR.

# The jenkins/jenkins containers run as the user "jenkins" which will prevent us from exploding files later.
USER root

# copy the files needed to run the JFR binary
COPY --from=jfr /app /app

# We need to explode the jenkins.war for JFR
RUN cd /usr/share/jenkins && jar -xvf jenkins.war

# I change the home
# ENV JENKINS_HOME="/usr/share/jenkins/ref/"

# "--withInitHooks", "/usr/share/jenkins/ref/init.groovy.d/"

ENTRYPOINT ["/app/bin/jenkinsfile-runner", "-w", "/usr/share/jenkins/", "-p", "/usr/share/jenkins/ref/plugins", "-f"]

CMD ["/workspace/Jenkinsfile"]
```
