FROM openjdk:11.0-jdk-slim AS builder

# binutils needed for command strip
RUN apt update && apt install -y binutils
RUN mkdir -p /home/jlink/src/com/logicbig/example/
COPY module-info.java /home/jlink/src/
COPY Test.java /home/jlink/src/com/logicbig/example/

WORKDIR /home/jlink/
RUN javac -d out src/module-info.java
RUN javac -d out --module-path out src/com/logicbig/example/Test.java

RUN jlink -G --launcher test-app=test.example/com.logicbig.example.Test --module-path /usr/local/openjdk-11/jmods:out --add-modules test.example --output jre --no-man-pages --no-header-files

RUN find /home/jlink/jre -name "*.so" -exec strip --strip-unneeded {} \;

FROM debian:stretch-slim
COPY --from=builder /home/jlink/jre /home/jlink/jre/
CMD ["/home/jlink/jre/bin/test-app"]
