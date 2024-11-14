FROM icr.io/appcafe/open-liberty:kernel-slim-java11-openj9-ubi

ARG VERSION=1.0
ARG REVISION=SNAPSHOT

LABEL \
  org.opencontainers.image.authors="Sushma KR" \
  org.opencontainers.image.vendor="sushmakravi" \
  org.opencontainers.image.url="local" \
  org.opencontainers.image.source="https://https://github.com/sushmakravi/Scalable-Services" \
  org.opencontainers.image.version="$VERSION" \
  org.opencontainers.image.revision="$REVISION" \
  vendor="Open Liberty" \
  name="system" \
  version="$VERSION-$REVISION" \
  summary="The system microservice from the Deploying microservices to Azure Kubernetes Service guide" \
  description="This image contains the system microservice running with the Open Liberty runtime."

COPY --chown=1001:0 src/main/scalable/config /config/
RUN features.sh
COPY --chown=1001:0 target/cloud-azure-system.war /config/apps

RUN configure.sh
