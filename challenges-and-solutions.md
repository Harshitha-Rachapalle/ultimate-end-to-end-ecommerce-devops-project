# 1.When we run below command and if build fails 

**`./gradlew installDist`**

> Task :compileJava FAILED

[Incubating] Problems report is available at: file:///home/ubuntu/project-opentelemetry-demo/src/ad/build/reports/problems/problems-report.html

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':compileJava'.
> Error while evaluating property 'javaCompiler' of task ':compileJava'.
   > Failed to calculate the value of task ':compileJava' property 'javaCompiler'.
      > Toolchain installation '/usr/lib/jvm/java-21-openjdk-amd64' does not provide the required capabilities: [JAVA_COMPILER]

* Try:
> Run with --stacktrace option to get the stack trace.
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.
> Get more help at https://help.gradle.org.

Deprecated Gradle features were used in this build, making it incompatible with Gradle 9.0.

You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.

For more on this, please refer to https://docs.gradle.org/8.12.1/userguide/command_line_interface.html#sec:command_line_warnings in the Gradle documentation.

BUILD FAILED in 2s
5 actionable tasks: 1 executed, 4 up-to-date

## solution

**1️⃣ Check Java Installation**

**Run:**
```which java
which javac
```

Expected output (or similar):

/usr/bin/java
/usr/bin/javac

Then check the Java version:

```java -version
javac -version
```

If both show Java 21, then Java is installed correctly.

**2️⃣ Set JAVA_HOME Properly**
If JAVA_HOME is not set correctly, Gradle will fail. Run:

```
echo $JAVA_HOME
```
If it’s empty or incorrect, set it manually:

```
export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
```

Make it permanent:

```
echo "export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64" >> ~/.bashrc
echo "export PATH=\$JAVA_HOME/bin:\$PATH" >> ~/.bashrc
source ~/.bashrc
```

**3️⃣ Verify Gradle is Using the Correct Java**

Run:

```
./gradlew --version
```

It should show Java 21.

**4.Run a Clean Build**

Now, try:

```
./gradlew --stop
./gradlew clean
./gradlew --info installDist
```
This ensures Gradle picks up the correct Java installation.

