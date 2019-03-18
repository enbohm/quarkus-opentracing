# quarkus-opentracing
Simple Quarkus project which tries to use quarkus-smallrye-openapi via application.properties to report traces to a Jeager instance running on localhost. 
Make sure you have Jager running, easiest way is to just run jeager-all-in-one see https://www.jaegertracing.io/docs/1.8/getting-started/  with default ports.

Clone the project and type
```mvn compile quarkus:dev```

then access http://localhost:8080/greeting/acme

Open up Jeager UI at http://127.0.0.1:16686 and NO spans/traces are visible even that is has been configured in application.properties.

Now run the application with the following params

```mvn compile quarkus:dev -Djvm.args="-DJAEGER_SAMPLER_TYPE=const -DJAEGER_SAMPLER_PARAM=1 -DJAEGER_ENDPOINT=http://localhost:14268/api/traces"```

Now traces are visible in Jaeger UI with the service-name from application.properties BUT the other properties doesn't seem to be working/read from the file.


