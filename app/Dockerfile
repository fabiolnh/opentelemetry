FROM amazoncorretto:17-alpine-jdk
WORKDIR /home/app
ARG JAR_FILE=build/libs/demo-0.0.1-SNAPSHOT.jar
COPY ${JAR_FILE} app.jar
COPY opentelemetry-javaagent.jar opentelemetry-javaagent.jar
ENTRYPOINT ["java", \
            "-javaagent:/home/app/opentelemetry-javaagent.jar", \
            "-Dotel.resource.attributes=service.name=demo", \
            "-Dotel.traces.exporter=jaeger", \
            "-Dotel.exporter.jaeger.endpoint=http://jaeger:14250", \
            "-Dotel.metrics.exporter=none", \
            "-Dotel.instrumentation.aws-sdk.experimental-span-attributes=true", \
            "-Dotel.instrumentation.aws-sdk.experimental-use-propagator-for-messaging=true", \
            "-Dotel.traces.sampler=always_on", \
            "-Dotel.javaagent.debug=true", \
            "-jar", "/home/app/app.jar"]
EXPOSE 8080
