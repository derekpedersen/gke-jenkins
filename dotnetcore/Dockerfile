FROM build-jenkins-base

USER root

# dotnetcore
RUN wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg && \
    mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/ && \ 
    wget -q https://packages.microsoft.com/config/debian/9/prod.list && \
    mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
RUN apt-get update && \
    apt-get install -y dotnet-sdk-2.1

ENTRYPOINT ["jenkins-slave"] 