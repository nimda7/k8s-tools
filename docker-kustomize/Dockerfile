FROM alpine:3.8

ARG BUILD_DATE
ARG KUBECTL_VERSION=1.16.0
ARG KUSTOMIZE_VERSION=3.2.1

LABEL maintainer="nimda7@gmail.com"
LABEL KUBECTL_VERSION=${KUBECTL_VERSION}
LABEL KUSTOMIZE_VERSION=${KUSTOMIZE_VERSION}
LABEL build-date=$BUILD_DATE

ENV KUBECTL_VERSION=${KUBECTL_VERSION} \
    KUSTOMIZE_VERSION=${KUSTOMIZE_VERSION}

WORKDIR /app

RUN apk add --no-cache curl && \
    curl -L https://storage.googleapis.com/kubernetes-release/release/v${KUBECTL_VERSION}/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl && \
    chmod +x /usr/local/bin/kubectl && \
    curl -L https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize/v${KUSTOMIZE_VERSION}/kustomize_kustomize.v${KUSTOMIZE_VERSION}_linux_amd64 -o /usr/local/bin/kustomize && \
    chmod +x /usr/local/bin/kustomize && \
    rm -rf /var/cache/apk/*

#CMD ["kustomize"]

