FROM --platform=$TARGETOS/$TARGETARCH eclipse-temurin:17-jdk-jammy

RUN apt-get update -y \
    && apt-get install -y lsof curl ca-certificates openssl git tar sqlite3 fontconfig libfreetype6 tzdata iproute2 libstdc++6 rsync \
    && useradd -d /home/container -m container

USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

COPY --chmod=0755 ./../entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
