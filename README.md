This repo is a copy of all code from https://github.com/open-telemetry/opentelemetry-rust/blob/e773f922632a1858004f04a83b95a227ee8f3dfa/opentelemetry-otlp/examples/basic-otlp/README.md#L0-L1
to demo issue with building it

```
otlp-demo-issue git:(main) ✗ cargo run
    Updating crates.io index
   Compiling proc-macro2 v1.0.63
   Compiling unicode-ident v1.0.9
   Compiling quote v1.0.29
   Compiling autocfg v1.1.0
   Compiling libc v0.2.147
   Compiling cfg-if v1.0.0
   Compiling pin-project-lite v0.2.9
   Compiling futures-core v0.3.28
   Compiling parking_lot_core v0.9.8
   Compiling bytes v1.4.0
   Compiling memchr v2.5.0
   Compiling futures-task v0.3.28
   Compiling futures-channel v0.3.28
   Compiling futures-sink v0.3.28
   Compiling smallvec v1.10.0
   Compiling scopeguard v1.1.0
   Compiling once_cell v1.18.0
   Compiling futures-util v0.3.28
   Compiling pin-utils v0.1.0
   Compiling futures-io v0.3.28
   Compiling hashbrown v0.12.3
   Compiling fnv v1.0.7
   Compiling tracing-core v0.1.31
   Compiling rustversion v1.0.12
   Compiling lock_api v0.4.10
   Compiling slab v0.4.8
   Compiling tokio v1.29.1
   Compiling indexmap v1.9.3
   Compiling ppv-lite86 v0.2.17
   Compiling itoa v1.0.6
   Compiling async-trait v0.1.68
   Compiling http v0.2.9
   Compiling thiserror v1.0.40
   Compiling crossbeam-utils v0.8.16
   Compiling httparse v1.8.0
   Compiling mio v0.8.8
   Compiling signal-hook-registry v1.4.1
   Compiling num_cpus v1.16.0
   Compiling socket2 v0.4.9
   Compiling getrandom v0.2.10
   Compiling tower-service v0.3.2
   Compiling syn v2.0.22
   Compiling parking_lot v0.12.1
   Compiling rand_core v0.6.4
   Compiling try-lock v0.2.4
   Compiling syn v1.0.109
   Compiling rand_chacha v0.3.1
   Compiling anyhow v1.0.71
   Compiling percent-encoding v2.3.0
   Compiling axum-core v0.3.4
   Compiling want v0.3.1
   Compiling either v1.8.1
   Compiling httpdate v1.0.2
   Compiling urlencoding v2.1.2
   Compiling tower-layer v0.3.2
   Compiling rand v0.8.5
   Compiling serde v1.0.164
   Compiling http-body v0.4.5
   Compiling itertools v0.10.5
   Compiling axum v0.6.18
   Compiling crossbeam-channel v0.5.8
   Compiling dashmap v5.4.0
   Compiling mime v0.3.17
   Compiling bitflags v1.3.2
   Compiling matchit v0.7.0
   Compiling sync_wrapper v0.1.2
   Compiling base64 v0.13.1
   Compiling prost-derive v0.11.9
   Compiling prost v0.11.9
   Compiling futures-macro v0.3.28
   Compiling tokio-macros v2.1.0
   Compiling tracing-attributes v0.1.26
   Compiling thiserror-impl v1.0.40
   Compiling pin-project-internal v1.1.1
   Compiling async-stream-impl v0.3.5
   Compiling async-stream v0.3.5
   Compiling pin-project v1.1.1
   Compiling tracing v0.1.37
   Compiling tracing-futures v0.2.5
   Compiling opentelemetry_api v0.19.0
   Compiling futures-executor v0.3.28
   Compiling futures v0.3.28
   Compiling tokio-util v0.7.8
   Compiling tokio-stream v0.1.14
   Compiling tokio-io-timeout v1.2.0
   Compiling opentelemetry_sdk v0.19.0
   Compiling h2 v0.3.20
   Compiling tower v0.4.13
   Compiling opentelemetry v0.19.0
   Compiling opentelemetry-semantic-conventions v0.11.0
   Compiling hyper v0.14.27
   Compiling hyper-timeout v0.4.1
   Compiling tonic v0.8.3
   Compiling opentelemetry-proto v0.2.0
   Compiling opentelemetry-otlp v0.12.0
   Compiling basic-otlp v0.1.0 (/Users/ivanitskiy/go/src/github.com/ivanitskiy/otlp-demo-issue)
error[E0432]: unresolved import `opentelemetry_sdk::metrics::MeterProvider`
  --> src/main.rs:11:25
   |
11 | use opentelemetry_sdk::{metrics::MeterProvider, runtime, trace as sdktrace, Resource};
   |                         ^^^^^^^^^^^^^^^^^^^^^^ no `MeterProvider` in `metrics`
   |
   = help: consider importing one of these items instead:
           crate::metrics::MeterProvider
           opentelemetry_api::metrics::MeterProvider

error[E0277]: the trait bound `Tokio: AggregatorSelector` is not satisfied
  --> src/main.rs:37:18
   |
37 |         .metrics(runtime::Tokio)
   |          ------- ^^^^^^^^^^^^^^ the trait `AggregatorSelector` is not implemented for `Tokio`
   |          |
   |          required by a bound introduced by this call
   |
note: required by a bound in `opentelemetry_otlp::metric::<impl OtlpPipeline>::metrics`
  --> /Users/ivanitskiy/.cargo/registry/src/github.com-1ecc6299db9ec823/opentelemetry-otlp-0.12.0/src/metric.rs:60:13
   |
60 |         AS: AggregatorSelector,
   |             ^^^^^^^^^^^^^^^^^^ required by this bound in `opentelemetry_otlp::metric::<impl OtlpPipeline>::metrics`

error[E0061]: this method takes 3 arguments but 1 argument was supplied
  --> src/main.rs:37:10
   |
37 |         .metrics(runtime::Tokio)
   |          ^^^^^^^---------------- two arguments are missing
   |
note: associated function defined here
  --> /Users/ivanitskiy/.cargo/registry/src/github.com-1ecc6299db9ec823/opentelemetry-otlp-0.12.0/src/metric.rs:53:12
   |
53 |     pub fn metrics<AS, TS, RT>(
   |            ^^^^^^^
help: provide the arguments
   |
37 |         .metrics(runtime::Tokio, /* temporality_selector */, /* rt */)
   |                 ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

error[E0599]: the method `with_exporter` exists for struct `OtlpMetricPipeline<Tokio, _, _>`, but its trait bounds were not satisfied
  --> src/main.rs:38:10
   |
38 |         .with_exporter(
   |          ^^^^^^^^^^^^^ method cannot be called on `OtlpMetricPipeline<Tokio, _, _>` due to unsatisfied trait bounds
   |
  ::: /Users/ivanitskiy/.cargo/registry/src/github.com-1ecc6299db9ec823/opentelemetry_sdk-0.19.0/src/runtime.rs:49:1
   |
49 | pub struct Tokio;
   | ---------------- doesn't satisfy `Tokio: AggregatorSelector`
   |
   = note: the following trait bounds were not satisfied:
           `Tokio: AggregatorSelector`

error[E0599]: no method named `as_any` found for struct `ObservableGauge` in the current scope
  --> src/main.rs:74:37
   |
74 |     meter.register_callback(&[gauge.as_any()], move |observer| {
   |                                     ^^^^^^ method not found in `ObservableGauge<f64>`

error[E0061]: this method takes 1 argument but 2 arguments were supplied
   --> src/main.rs:74:11
    |
74  |       meter.register_callback(&[gauge.as_any()], move |observer| {
    |  ___________^^^^^^^^^^^^^^^^^____________________-
75  | |         observer.observe_f64(&gauge, 1.0, COMMON_ATTRIBUTES.as_ref())
76  | |     })?;
    | |_____- argument unexpected
    |
note: associated function defined here
   --> /Users/ivanitskiy/.cargo/registry/src/github.com-1ecc6299db9ec823/opentelemetry_api-0.19.0/src/metrics/meter.rs:150:12
    |
150 |     pub fn register_callback<F>(&self, callback: F) -> Result<(), MetricsError>
    |            ^^^^^^^^^^^^^^^^^
help: remove the extra argument
    |
74  |     meter.register_callback(&[gauge.as_any()])?;
    |                            ~~~~~~~~~~~~~~~~~~~

error[E0061]: this method takes 3 arguments but 2 arguments were supplied
  --> src/main.rs:79:15
   |
79 |     histogram.record(5.5, COMMON_ATTRIBUTES.as_ref());
   |               ^^^^^^ --- an argument of type `&opentelemetry_api::Context` is missing
   |
note: associated function defined here
  --> /Users/ivanitskiy/.cargo/registry/src/github.com-1ecc6299db9ec823/opentelemetry_api-0.19.0/src/metrics/instruments/histogram.rs:35:12
   |
35 |     pub fn record(&self, cx: &Context, value: T, attributes: &[KeyValue]) {
   |            ^^^^^^
help: provide the argument
   |
79 |     histogram.record(/* &opentelemetry_api::Context */, 5.5, COMMON_ATTRIBUTES.as_ref());
   |                     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

error[E0061]: this method takes 3 arguments but 2 arguments were supplied
  --> src/main.rs:95:23
   |
95 |             histogram.record(1.3, &[]);
   |                       ^^^^^^ --- an argument of type `&opentelemetry_api::Context` is missing
   |
note: associated function defined here
  --> /Users/ivanitskiy/.cargo/registry/src/github.com-1ecc6299db9ec823/opentelemetry_api-0.19.0/src/metrics/instruments/histogram.rs:35:12
   |
35 |     pub fn record(&self, cx: &Context, value: T, attributes: &[KeyValue]) {
   |            ^^^^^^
help: provide the argument
   |
95 |             histogram.record(/* &opentelemetry_api::Context */, 1.3, &[]);
   |                             ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Some errors have detailed explanations: E0061, E0277, E0432, E0599.
For more information about an error, try `rustc --explain E0061`.
error: could not compile `basic-otlp` due to 8 previous errors
```


# Basic OTLP exporter Example

This example shows basic span and metric usage, and exports to the [OpenTelemetry Collector](https://github.com/open-telemetry/opentelemetry-collector) via OTLP.

## Usage

### `docker-compose`

By default runs against the `otel/opentelemetry-collector-dev:latest` image, and uses the `tonic`'s
`grpc` example as the transport.

```shell
docker-compose up
or
docker-compose up -d
```

In another terminal run the application `cargo run`

Use the browser to see the trace:
- Jaeger at http://0.0.0.0:16686

Tear it down:

```shell
docker-compose down
```

### Manual

If you don't want to use `docker-compose`, you can manually run the `otel/opentelemetry-collector` container
and inspect the logs to see traces being transferred.

```shell
# Run `opentelemetry-collector`
$ docker run  -p4317:4317 otel/opentelemetry-collector:latest

# Report spans/metrics
$ cargo run
```

# View result

You should be able to see something similar below with different time and ID in the same console that docker runs.

## Span

```
Resource labels:
     -> service.name: STRING(trace-demo)
InstrumentationLibrarySpans #0
InstrumentationLibrary
Span #0
    Trace ID       : 737d9c966e8250475f400776228c0044
    Parent ID      : ade62a071825f2db
    ID             : 7aa9ea5f24e0444c
    Name           : Sub operation...
    Kind           : SPAN_KIND_INTERNAL
    Start time     : 2022-02-24 04:59:57.218995 +0000 UTC
    End time       : 2022-02-24 04:59:57.219022 +0000 UTC
    Status code    : STATUS_CODE_UNSET
    Status message :
Attributes:
     -> lemons: STRING(five)
Events:
SpanEvent #0
     -> Name: Sub span event
     -> Timestamp: 2022-02-24 04:59:57.219012 +0000 UTC
     -> DroppedAttributesCount: 0
ResourceSpans #1
Resource labels:
     -> service.name: STRING(trace-demo)
InstrumentationLibrarySpans #0
InstrumentationLibrary
Span #0
    Trace ID       : 737d9c966e8250475f400776228c0044
    Parent ID      :
    ID             : ade62a071825f2db
    Name           : operation
    Kind           : SPAN_KIND_INTERNAL
    Start time     : 2022-02-24 04:59:57.218877 +0000 UTC
    End time       : 2022-02-24 04:59:57.219043 +0000 UTC
    Status code    : STATUS_CODE_UNSET
    Status message :
Attributes:
     -> ex.com/another: STRING(yes)
Events:
SpanEvent #0
     -> Name: Nice operation!
     -> Timestamp: 2022-02-24 04:59:57.218896 +0000 UTC
     -> DroppedAttributesCount: 0
     -> Attributes:
         -> bogons: INT(100)
```

## Metric

```
2021-11-19T04:08:36.453Z	INFO	loggingexporter/logging_exporter.go:56	MetricsExporter	{"#metrics": 1}
2021-11-19T04:08:36.454Z	DEBUG	loggingexporter/logging_exporter.go:66	ResourceMetrics #0
Resource labels:
     -> service.name: STRING(unknown_service)
InstrumentationLibraryMetrics #0
InstrumentationLibrary ex.com/basic
Metric #0
Descriptor:
     -> Name: ex.com.one
     -> Description: A ValueObserver set to 1.0
     -> Unit:
     -> DataType: Gauge
NumberDataPoints #0
Data point attributes:
     -> A: STRING(1)
     -> B: STRING(2)
     -> C: STRING(3)
     -> lemons: INT(10)
StartTimestamp: 2021-11-19 04:07:46.29555 +0000 UTC
Timestamp: 2021-11-19 04:08:36.297279 +0000 UTC
Value: 1.000000
```


