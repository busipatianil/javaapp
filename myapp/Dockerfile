# Use a hardened Tomcat image for production
FROM tomcat:9.0-jdk11-corretto-al2
# Security Best Practice: Remove default webapps
RUN rm -rf /usr/local/tomcat/webapps/*
# Copy your pre-built .war file into the container.
# Make sure "my-application.war" is in the same directory as the Dockerfile.
COPY myapp.war /usr/local/tomcat/webapps/ROOT.war
# Security Best Practice: Run as a non-root user
RUN groupadd -r tomcat && useradd -r -g tomcat -d /usr/local/tomcat -s /bin/false tomcat
RUN chown -R tomcat:tomcat /usr/local/tomcat/
USER tomcat
#Expose Port
EXPOSE 8080
