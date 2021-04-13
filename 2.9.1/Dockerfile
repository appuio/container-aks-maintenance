ARG AZURE_CLI_VERSION=2.9.1

FROM mcr.microsoft.com/azure-cli:$AZURE_CLI_VERSION

RUN apk add jq

RUN az extension add --name aks-preview

ADD src/updateNodes.sh /usr/local/bin/updateNodes.sh

RUN chmod +x /usr/local/bin/updateNodes.sh
