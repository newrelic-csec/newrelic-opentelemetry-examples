# Getting Started Guide - Java

This is the solution (completely instrumented with OpenTelemetry) for the Java demo application used in the Getting Started Guide - Java doc. 

Requires:

* Java 17+
* [A New Relic account](https://one.newrelic.com/)

To run this demo app via the CLI:

1. Switch to the `java` directory
2. Set these two environment variables to send data to your New Relic account:
```
export OTEL_EXPORTER_OTLP_HEADERS=<your_license_key>
export OTEL_EXPORTER_OTLP_ENDPOINT=https://otlp.nr-data.net
export OTEL_EXPORTER_OTLP_PROTOCOL=http/protobuf
export OTEL_ATTRIBUTE_VALUE_LENGTH_LIMIT=4095
```
* Make sure to use your [ingest license key](https://docs.newrelic.com/docs/apis/intro-apis/new-relic-api-keys/#license-key)
* If your account is based in the EU, set the endpoint to: https://otlp.eu01.nr-data.net

3. Set this environment variable to name the demo app:
```
export OTEL_SERVICE_NAME=getting-started-java
export OTEL_RESOURCE_ATTRIBUTES=service.instance.id=123
```

4. Run the following command

```shell
../gradlew bootRun
```

4. To generate traffic, in a new terminal tab run the following command
```shell
./load-generator.sh
```

5. To shut down the program, run the following in both shells or terminal tabs: `ctrl + c`. 