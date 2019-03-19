# quarkus-opentracing
Simple Quarkus project which uses quarkus-smallrye-openapi via application.properties to report traces to a Jeager instance running on localhost. 
Make sure you have Jager running, easiest way is to just run jeager-all-in-one see https://www.jaegertracing.io/docs/1.8/getting-started/  with default ports.

Clone the project and type
```mvn compile quarkus:dev```

then access http://localhost:8080/greeting/acme

Open up Jeager UI at http://127.0.0.1:16686 and you can see the trace from the above request
