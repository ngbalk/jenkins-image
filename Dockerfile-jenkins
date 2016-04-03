FROM jenkins
#Prepare environment (Install maven)
USER root
RUN apt-get update
RUN apt-get install maven -y

#Copy local plugins.txt file for plugin installation 
COPY files/plugins.txt /usr/share/jenkins/plugins.txt

#Add plugin configuration .xml files to startup ref 
ADD files/jenkins-configurations /usr/share/jenkins/ref

#Copy seed build folder to startup ref
ADD files/jenkins-seed-build/seed/config.xml /usr/share/jenkins/ref/jobs/seed/config.xml

#Download sonatype plugin
ADD http://download.sonatype.com/clm/ci/sonatype-clm-ci-2.14.2-01.hpi?elqid=d68c23a6-5c1a-4919-bfce-09e93169cb4a /usr/share/jenkins/ref/plugins/sonatype-clm-ci-2.14.2-01.hpi

#Install plugins
#RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt
RUN mkdir /usr/share/jenkins/plugins
ADD https://updates.jenkins-ci.org/download/plugins/git-client/1.19.4/git-client.hpi /usr/share/jenkins/ref/plugins/git-client.hpi
ADD https://updates.jenkins-ci.org/download/plugins/git/2.4.2/git.hpi /usr/share/jenkins/ref/plugins/git.hpi
ADD https://updates.jenkins-ci.org/download/plugins/credentials/1.24/credentials.hpi /usr/share/jenkins/ref/plugins/credentials.hpi
ADD https://updates.jenkins-ci.org/download/plugins/scm-api/1.0/scm-api.hpi /usr/share/jenkins/ref/plugins/scm-api.hpi
ADD https://updates.jenkins-ci.org/download/plugins/mailer/1.16/mailer.hpi /usr/share/jenkins/ref/plugins/mailer.hpi
ADD https://updates.jenkins-ci.org/download/plugins/matrix-project/1.6/matrix-project.hpi /usr/share/jenkins/ref/plugins/matrix-project.hpi
ADD https://updates.jenkins-ci.org/download/plugins/job-dsl/1.42/job-dsl.hpi /usr/share/jenkins/ref/plugins/job-dsl.hpi
