# Build locally 

In this project . ad service based on java language. This java microservice is build by **gradle**

on windows, we can use gradlew.bat 

(go through ad service readme file and follow instructions to run it locally)

..>in my case, in gitbash go to project-opentelemetry-demo project inside it go to ad microservice i.e cd project-opentelemetry-demo/src/ad/

Then,

**1.Install java version latest**

```
sudo apt install openjdk-21-jre-headless
```

**2.give permission to gradle wrapper**

```
chmod +x ./gradlew
```

**3. To build Ad Service, run:**

```
./gradlew installDist
```

once, build is completed , then check **build** directory is present by using 'ls -ltr'

**4.check executable file**

```
ls -ltr ./build/install/opentelemetry-demo-ad/bin/Ad
```

### output

-rwxr-xr-x 1 ubuntu ubuntu 11517 Mar 30 11:42 ./build/install/opentelemetry-demo-ad/bin/Ad

**5.To run the Ad Service:**

```
export AD_PORT=8088
export FEATURE_FLAG_GRPC_SERVICE_ADDR=featureflagservice:50053
./build/install/opentelemetry-demo-ad/bin/Ad
```

### output

SLF4J(W): No SLF4J providers were found.
SLF4J(W): Defaulting to no-operation (NOP) logger implementation
SLF4J(W): See https://www.slf4j.org/codes.html#noProviders for further details.
2025-03-30 12:22:48 - oteldemo.AdService - Ad service started, listening on 8088 trace_id= span_id= trace_flags=



