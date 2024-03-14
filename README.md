# ozaru

> [!NOTE]
> This is a WIP. If you're seeing this message, you're here too early

Ozaru is a library to help ape test javascript applications.

Ape testing is similar to monkey/gorilla tetting, often including elements of both, but is specifically designed to test how a javascript application and its surrounding infrastructure reacts to adverse conditions like high memory/cpu usage, stalled event loops, unexpected crashes,

This can be useful for testing autoscaling, monitoring tools, or error recovery.

Ozaru provides tooling for common scenarios that can be triggered on-demand, on a schedule, or completely randomly. 

### Crashing

- Uncaught Exceptions
- Uncaught Promise Rejections
- Sudden SIGKILL
- OOM Error (Max Old State)
- Crash Loop

### CPU

- Large JSON Deserialization
  - Often comes from runaway database queries or huge http requests
- Starved Event Loop

### Network

- Sudden network loss
- Increased nework latency

## How?

Ozaru starts your application in a separate thread and communicates with an internal library using messaging

The Ozaru library included in the application by by altering the NODE_OPTIONS environment variable to include the `--require` flag.
