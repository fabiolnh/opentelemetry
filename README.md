# Open Telemetry (Currently Studying)

- Project built by CNCF (same foundation that invented Kubernetes)

1) Context:
    - Observability (Logs, Metrics, Tracing)
    - (Cloud Native Telemetry): Independently of Programing language, Independently of the provider (DataDog, New Relic, Splunk, etc)
    - Centralize Information
    - Need of customized information
      * Generation of business metrics, etc.
      * internal block and routines tracing of the application

- Lock In: You have to avoid "Lock In" (when you are dependent on only one vendor when you are implementing something). Each tool in the market has its own way to work. You have to minimize the problem when you are working with a tool and you need to change it. That's why the project Open Telemetry exists. This way you do not depend on New Relic, Elastic, DataDog, Splunk, etc.
- In the past, there were 2 projects: Open Tracing and OpenCensus. They tried to consolidate a pattern to work with "Lock In". Open Telemetry got these ideas and generates a project that is much more consolidated and official

- What is Open Telemetry?
    - Observability Framework
    - Tools: APIs and SDKs
    - Instrumentation, Generation, data export
- Main Components:
    - Specifications
        * Data
        * SDKs (it brings the SDKs to work with all languages)
        * APIs (to use with collectors)
    - Collector
        * Agent or Service (get the data to send to the vendor). (Can be an agent running in the application, a sidecar, or a separated service)
        * Pipeline (can receive data, transform it, following some moments, until the data is ready to send to the vendor). Steps: (how to receive, how to process, how to send data)
        * Vendor-Agnostic: You can change the vendor any time that you want
    - Libs
        * Vendor-Agnostic
        * Tracing and Logs
        * Auto Tracing (in some languages, you can inject something at the execution time. The agent helps to generate the information without changing the code. This way you do not need to inject manually the tracing in the code)
    - Logs

- OBS: some languages and some things in Open Telemetry are not 100% done, because there are a lot of vendors, SDKs, Libs to implement. Visit the website to check it. Ex: https://opentelemetry.io/docs/instrumentation/java/ - Traces (Stable) Metrics (Stable) Logs (Stable)

- Options with Collector:
    1) No Collector: just using libs to send directly to the vendor
    2) Collector Agent (sidecar): an app that stays "aside of the application (in the same pod)" that receives the information and then exports to the vendor
    3) Collector Server: A service that stays apart from the application. The application send the information to the Server and the Server sends to the Vendor

- Instrumentation: The way that treats the information in your app and sends it to the collector or to the vendor. Options:
    1) Automatically (a lib that everytime is getting all the information of your app and sending it to the vendor) (ex: with java, you can run a command to run the application with the jar from the OpenTelemetry)  (it is not available in all languages, and probably some languages will never have it)
    2) Manually (check the code and choose what you want to be sent, coding it)
