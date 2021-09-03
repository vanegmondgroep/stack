# Arguments
ARG STACK_RUNTIME_TAG
ARG STACK_RUNTIME_IMAGE

# Build image
FROM ${STACK_RUNTIME_IMAGE}:${STACK_RUNTIME_TAG}

ARG STACK_UID

ENV RUNTIME_USER_ID=${STACK_UID}

USER root

RUN apk --no-cache add shadow

RUN usermod -u ${RUNTIME_USER_ID} ${RUNTIME_USER_NAME} \
    && /opt/runtime/bin/runtime reset-permissions

USER ${RUNTIME_USER_NAME}
