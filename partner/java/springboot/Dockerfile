# Build:
#   mvn clean package
#   docker build --rm -t foundation-partner-service:1.0.0 .
#   docker tag foundation-partner-service:1.0.0 docker.io/robin9999/foundation-partner-service:1.0.0

# Docker push (on F28):
#   Make sure the following is the *first* entry in the docker daemon (by updating /etc/sysconfig/docker):  --add-registry docker.io
#   docker login docker.io -u robin9999
#   docker push docker.io/robin9999/foundation-partner-service:1.0.0

# Execution: OpenShift
#   oc run foundation-partner-service --image=docker.io/robin9999/foundation-partner-service:1.0.0

FROM fabric8/java-jboss-openjdk8-jdk:1.3.1
ENV JAVA_APP_DIR=/deployments
ENV JAEGER_SERVICE_NAME=gateway\
  JAEGER_ENDPOINT=http://jaeger-collector.istio-system.svc:14268/api/traces\
  JAEGER_PROPAGATION=b3\
  JAEGER_SAMPLER_TYPE=const\
  JAEGER_SAMPLER_PARAM=1
EXPOSE 8080 8778 9779
COPY target/foundation-partner-service.jar /deployments/
