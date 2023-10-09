FROM mcr.microsoft.com/mssql/rhel/server:2019-latest

COPY . /
USER root
RUN chmod +x /db-init.sh
CMD /bin/bash ./entrypoint.sh
