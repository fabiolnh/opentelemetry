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
