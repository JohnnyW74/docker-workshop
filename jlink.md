# smaller Java-Images with jlink

compiling
> javac -d out src/module-info.java
> javac -d out --module-path out src/com/logicbig/example/Test.java

running
> java --module-path out --module test.example/com.logicbig.example.Test

getting dependencies
> jdeps --module-path out -s --module test.example

building with dependencies
> jlink --module-path /usr/lib/jvm/java-11-openjdk-amd64/jmods/:out --add-modules test.example --output build

additional parameters for jlink:
> -G --no-man-pages --no-header-files

also strip the result:
> find build -name "*.so" -exec strip --strip-unneeded {} \;