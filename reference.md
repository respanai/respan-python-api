# Reference
## Spans
<details><summary><code>client.spans.<a href="src/respan/spans/client.py">create_span</a>(...) -> CreateSpanResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a span representing a single LLM interaction. Spans are the core data unit in Respan — every LLM call, agent step, or tool invocation is stored as a span.

Span size limit: 20MB per payload.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.spans.create_span(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**prompt_messages:** `typing.Optional[typing.List[str]]` — Deprecated. Use `input` instead.
    
</dd>
</dl>

<dl>
<dd>

**completion_message:** `typing.Optional[typing.Dict[str, typing.Any]]` — Deprecated. Use `output` instead.
    
</dd>
</dl>

<dl>
<dd>

**input:** `typing.Optional[CreateSpanRequestInput]` — The input to the model. Format depends on `log_type`.
    
</dd>
</dl>

<dl>
<dd>

**output:** `typing.Optional[CreateSpanRequestOutput]` — The output from the model. Format depends on `log_type`.
    
</dd>
</dl>

<dl>
<dd>

**log_type:** `typing.Optional[CreateSpanRequestLogType]` — Type of span. Determines how `input` and `output` are parsed.
    
</dd>
</dl>

<dl>
<dd>

**model:** `typing.Optional[str]` — Model used for the request.
    
</dd>
</dl>

<dl>
<dd>

**usage:** `typing.Optional[typing.Dict[str, typing.Any]]` — Token usage for the request.
    
</dd>
</dl>

<dl>
<dd>

**cost:** `typing.Optional[float]` — Cost in USD. Auto-calculated from model pricing if omitted.
    
</dd>
</dl>

<dl>
<dd>

**latency:** `typing.Optional[float]` — Total request latency in seconds.
    
</dd>
</dl>

<dl>
<dd>

**time_to_first_token:** `typing.Optional[float]` — Time to first token in seconds.
    
</dd>
</dl>

<dl>
<dd>

**tokens_per_second:** `typing.Optional[float]` — Generation speed in tokens per second.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Arbitrary key-value pairs for your reference.
    
</dd>
</dl>

<dl>
<dd>

**customer_identifier:** `typing.Optional[str]` — Identifier for the end user who made this request.
    
</dd>
</dl>

<dl>
<dd>

**customer_params:** `typing.Optional[typing.Dict[str, typing.Any]]` — Extended customer information.
    
</dd>
</dl>

<dl>
<dd>

**thread_identifier:** `typing.Optional[str]` — Conversation thread ID for multi-turn conversations.
    
</dd>
</dl>

<dl>
<dd>

**custom_identifier:** `typing.Optional[str]` — Indexed custom identifier for fast querying.
    
</dd>
</dl>

<dl>
<dd>

**group_identifier:** `typing.Optional[str]` — Groups related spans together.
    
</dd>
</dl>

<dl>
<dd>

**trace_unique_id:** `typing.Optional[str]` — Trace ID to link spans into a trace tree.
    
</dd>
</dl>

<dl>
<dd>

**span_workflow_name:** `typing.Optional[str]` — Name of the parent workflow.
    
</dd>
</dl>

<dl>
<dd>

**span_name:** `typing.Optional[str]` — Name of this span within the workflow.
    
</dd>
</dl>

<dl>
<dd>

**span_parent_id:** `typing.Optional[str]` — Parent span ID. Builds the trace hierarchy.
    
</dd>
</dl>

<dl>
<dd>

**tools:** `typing.Optional[typing.List[str]]` — Tools available to the model (OpenAI function calling format).
    
</dd>
</dl>

<dl>
<dd>

**tool_choice:** `typing.Optional[CreateSpanRequestToolChoice]` — Controls tool selection. `"none"`, `"auto"`, or a specific tool object.
    
</dd>
</dl>

<dl>
<dd>

**response_format:** `typing.Optional[typing.Dict[str, typing.Any]]` — Response format configuration (e.g. JSON mode or structured output).
    
</dd>
</dl>

<dl>
<dd>

**temperature:** `typing.Optional[float]` — Sampling temperature (0-2). Higher = more random.
    
</dd>
</dl>

<dl>
<dd>

**top_p:** `typing.Optional[float]` — Nucleus sampling parameter.
    
</dd>
</dl>

<dl>
<dd>

**frequency_penalty:** `typing.Optional[float]` — Penalizes repeated tokens (-2 to 2).
    
</dd>
</dl>

<dl>
<dd>

**presence_penalty:** `typing.Optional[float]` — Penalizes tokens already present (-2 to 2).
    
</dd>
</dl>

<dl>
<dd>

**max_tokens:** `typing.Optional[int]` — Maximum tokens to generate.
    
</dd>
</dl>

<dl>
<dd>

**stop:** `typing.Optional[typing.List[str]]` — Stop sequences where generation halts.
    
</dd>
</dl>

<dl>
<dd>

**status_code:** `typing.Optional[int]` — HTTP status code of the request.
    
</dd>
</dl>

<dl>
<dd>

**error_message:** `typing.Optional[str]` — Error message if the request failed.
    
</dd>
</dl>

<dl>
<dd>

**warnings:** `typing.Optional[CreateSpanRequestWarnings]` — Warnings from the request.
    
</dd>
</dl>

<dl>
<dd>

**status:** `typing.Optional[CreateSpanRequestStatus]` — Request status.
    
</dd>
</dl>

<dl>
<dd>

**stream:** `typing.Optional[bool]` — Whether the response was streamed.
    
</dd>
</dl>

<dl>
<dd>

**prompt_id:** `typing.Optional[str]` — ID of the Respan prompt template used.
    
</dd>
</dl>

<dl>
<dd>

**prompt_name:** `typing.Optional[str]` — Name of the prompt template.
    
</dd>
</dl>

<dl>
<dd>

**is_custom_prompt:** `typing.Optional[bool]` — Set `true` when using a custom `prompt_id`.
    
</dd>
</dl>

<dl>
<dd>

**timestamp:** `typing.Optional[str]` — ISO 8601 timestamp when the request completed.
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `typing.Optional[str]` — ISO 8601 timestamp when the request started.
    
</dd>
</dl>

<dl>
<dd>

**full_request:** `typing.Optional[typing.Dict[str, typing.Any]]` — Full raw request object for reference.
    
</dd>
</dl>

<dl>
<dd>

**full_response:** `typing.Optional[typing.Dict[str, typing.Any]]` — Full raw response object from the provider.
    
</dd>
</dl>

<dl>
<dd>

**prompt_unit_price:** `typing.Optional[float]` — Custom price per 1M prompt tokens (for self-hosted/fine-tuned models).
    
</dd>
</dl>

<dl>
<dd>

**completion_unit_price:** `typing.Optional[float]` — Custom price per 1M completion tokens (for self-hosted/fine-tuned models).
    
</dd>
</dl>

<dl>
<dd>

**respan_api_controls:** `typing.Optional[typing.Dict[str, typing.Any]]` — Controls for the Respan logging API behavior.
    
</dd>
</dl>

<dl>
<dd>

**positive_feedback:** `typing.Optional[bool]` — User feedback. `true` = positive, `false` = negative.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.spans.<a href="src/respan/spans/client.py">list_spans</a>(...) -> ListSpansResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve spans matching the specified filters with pagination. Supports filtering by any span field, URL-based quick filters, and sorting by evaluator scores. See [Filters API Reference](/docs/api-reference/reference/filters-api-reference) for full filter syntax.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment
import datetime

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.spans.list_spans(
    sort_by="-cost",
    start_time=datetime.datetime.fromisoformat("2025-01-01T00:00:00+00:00"),
    end_time=datetime.datetime.fromisoformat("2025-01-31T23:59:59+00:00"),
    environment="production",
    include_fields="customer_identifier,model,cost,latency",
    authorization="Bearer sk_live_xxxxx",
    operator="AND",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**operator:** `ListSpansRequestOperator` — Logical operator to combine filters.
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Results per page (max 1000).
    
</dd>
</dl>

<dl>
<dd>

**sort_by:** `typing.Optional[str]` — Field to sort by. Prefix `-` for descending.
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `typing.Optional[datetime.datetime]` — Start of time range (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**end_time:** `typing.Optional[datetime.datetime]` — End of time range (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[str]` — Filter by environment.
    
</dd>
</dl>

<dl>
<dd>

**is_test:** `typing.Optional[ListSpansRequestIsTest]` — Filter by test/production spans.
    
</dd>
</dl>

<dl>
<dd>

**all_envs:** `typing.Optional[ListSpansRequestAllEnvs]` — Include spans from all environments.
    
</dd>
</dl>

<dl>
<dd>

**fetch_filters:** `typing.Optional[ListSpansRequestFetchFilters]` — Return available filter options in the response. May slow response.
    
</dd>
</dl>

<dl>
<dd>

**include_fields:** `typing.Optional[str]` — Comma-separated list of fields to include in each span. Reduces response size.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.spans.<a href="src/respan/spans/client.py">retrieve_span</a>(...) -> RetrieveSpanResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a span by its unique ID. Returns the full span including input, output, metrics, metadata, trace context, evaluation scores, and credit/budget info (`limit_info`).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.spans.retrieve_span(
    unique_id="unique_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**unique_id:** `str` — The unique ID of the log to get.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.spans.<a href="src/respan/spans/client.py">patch_log_span</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update mutable fields of a span. Supports pinning for infinite retention, user feedback, text annotations, and metadata (merged with existing metadata).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.spans.patch_log_span(
    unique_id="unique_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**unique_id:** `str` — The unique identifier of the span
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**is_pinned:** `typing.Optional[bool]` — Pin the span for infinite retention.
    
</dd>
</dl>

<dl>
<dd>

**positive_feedback:** `typing.Optional[bool]` — User feedback. `true` = positive, `false` = negative, `null` = clear.
    
</dd>
</dl>

<dl>
<dd>

**note:** `typing.Optional[str]` — Free-text annotation on the span.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Metadata to merge into existing span metadata.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.spans.<a href="src/respan/spans/client.py">get_spans_summary</a>(...) -> GetSpansSummaryResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get aggregated statistics for spans matching the given filters. Uses the same filters and query parameters as [List spans](/docs/api-reference/observe/logs/list-spans).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment
import datetime

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.spans.get_spans_summary(
    start_time=datetime.datetime.fromisoformat("2025-01-01T00:00:00+00:00"),
    end_time=datetime.datetime.fromisoformat("2025-01-31T23:59:59+00:00"),
    environment="production",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `typing.Optional[datetime.datetime]` — Start of time range (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**end_time:** `typing.Optional[datetime.datetime]` — End of time range (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[str]` — Filter by environment.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.spans.<a href="src/respan/spans/client.py">ingest_spans_from_traces</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Ingest an array of spans as a trace. Each span uses the same fields as [Create span](/docs/api-reference/observe/logs/create-span), plus `span_unique_id` to identify each span within the trace.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment
from respan.spans import IngestSpansFromTracesRequestBodyItem

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.spans.ingest_spans_from_traces(
    authorization="Bearer sk_live_xxxxx",
    request=[
        IngestSpansFromTracesRequestBodyItem(
            trace_unique_id="trace_abc123",
            span_unique_id="span_xyz789",
        )
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.List[IngestSpansFromTracesRequestBodyItem]` — Array of span objects to ingest as a trace.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Traces
<details><summary><code>client.traces.<a href="src/respan/traces/client.py">ingest_traces_via_otlp</a>(...) -> IngestTracesViaOtlpResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Send traces using the standard [OTLP/HTTP](https://opentelemetry.io/docs/specs/otlp/) protocol. Any OpenTelemetry-compatible SDK can export directly to this endpoint. Accepts both `application/json` and `application/x-protobuf` content types.

For the easiest setup, use the [Respan tracing SDK](/docs/sdks/python-sdk/overview) or the [OpenTelemetry integration](/docs/integrations/opentelemetry) which auto-configures the exporter.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment
from respan.traces import IngestTracesViaOtlpRequestResourceSpansItem

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.traces.ingest_traces_via_otlp(
    authorization="Bearer sk_live_xxxxx",
    resource_spans=[
        IngestTracesViaOtlpRequestResourceSpansItem()
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**resource_spans:** `typing.List[IngestTracesViaOtlpRequestResourceSpansItem]` — Array of resource spans. Each element represents spans from a single resource (service).
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.traces.<a href="src/respan/traces/client.py">list</a>(...) -> TracesListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a paginated list of traces matching your filters. See [Filters API Reference](/docs/api-reference/reference/filters-api-reference) for filter syntax.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment
import datetime

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.traces.list(
    sort_by="-total_cost",
    start_time=datetime.datetime.fromisoformat("2025-01-01T00:00:00+00:00"),
    end_time=datetime.datetime.fromisoformat("2025-01-31T23:59:59+00:00"),
    environment="production",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Results per page (max 1000).
    
</dd>
</dl>

<dl>
<dd>

**sort_by:** `typing.Optional[str]` — Field to sort by. Prefix `-` for descending.
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `typing.Optional[datetime.datetime]` — Start of time range (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**end_time:** `typing.Optional[datetime.datetime]` — End of time range (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[str]` — Filter by environment.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**operator:** `typing.Optional[TracesListRequestOperator]` — Logical operator to combine filters.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.traces.<a href="src/respan/traces/client.py">retrieve_trace</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a trace by its ID, including the complete span tree with full input/output for all spans.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.traces.retrieve_trace(
    trace_unique_id="trace_unique_id",
    environment="production",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**trace_unique_id:** `str` — Trace Unique Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[str]` — Filter by environment.
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `typing.Optional[datetime.datetime]` — Start of time range (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**end_time:** `typing.Optional[datetime.datetime]` — End of time range (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.traces.<a href="src/respan/traces/client.py">delete_trace</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a trace and all its spans by `trace_unique_id`. Removes data from both raw span storage and the aggregated trace table.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.traces.delete_trace(
    trace_unique_id="trace_unique_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**trace_unique_id:** `str` — Unique identifier of the trace to delete.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `typing.Optional[str]` — ISO 8601 start of time range for efficient lookup. Defaults to end_time minus 1 hour.
    
</dd>
</dl>

<dl>
<dd>

**end_time:** `typing.Optional[str]` — ISO 8601 end of time range for efficient lookup. Defaults to current time.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.traces.<a href="src/respan/traces/client.py">retrieve_traces_summary</a>(...) -> RetrieveTracesSummaryResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get aggregated statistics for traces matching your filters. Uses the same filters and query parameters as [List traces](/docs/api-reference/observe/traces/list-traces).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment
import datetime

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.traces.retrieve_traces_summary(
    start_time=datetime.datetime.fromisoformat("2025-01-01T00:00:00+00:00"),
    end_time=datetime.datetime.fromisoformat("2025-01-31T23:59:59+00:00"),
    environment="production",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `typing.Optional[datetime.datetime]` — Start of time range (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**end_time:** `typing.Optional[datetime.datetime]` — End of time range (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[str]` — Filter by environment.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.traces.<a href="src/respan/traces/client.py">bulk_delete_traces</a>(...) -> BulkDeleteTracesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete multiple traces matching the given filters. Uses the same filter format as [List traces](/docs/api-reference/observe/traces/list-traces). Returns the count of deleted traces.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient, Filters, FilterValue
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.traces.bulk_delete_traces(
    authorization="Bearer sk_live_xxxxx",
    filters=Filters(
        customer_identifier=FilterValue(
            operator="",
            value=[
                "user_123"
            ],
        ),
        model=FilterValue(
            operator="",
            value=[
                "gpt-4o"
            ],
        ),
        cost=FilterValue(
            operator="gte",
            value=[
                0.01
            ],
        ),
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `Filters` 
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `typing.Optional[str]` — ISO 8601 start of time range. Defaults to end_time minus 1 hour.
    
</dd>
</dl>

<dl>
<dd>

**end_time:** `typing.Optional[str]` — ISO 8601 end of time range. Defaults to current time.
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[str]` — Filter by environment (e.g., production, staging).
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.traces.<a href="src/respan/traces/client.py">ingest_traces_from_logs</a>(...) -> IngestTracesFromLogsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Ingest a batch of spans to construct traces. Spans with the same `trace_unique_id` are grouped into a single trace. Parent-child relationships are inferred via `span_parent_id`. For new integrations, prefer [Create a trace (OTLP)](/docs/api-reference/observe/traces/create-a-trace-otlp).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment
from respan.traces import IngestTracesFromLogsRequestBodyItem

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.traces.ingest_traces_from_logs(
    authorization="Bearer sk_live_xxxxx",
    request=[
        IngestTracesFromLogsRequestBodyItem(
            trace_unique_id="trace_abc123",
            span_unique_id="span_001",
        )
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.List[IngestTracesFromLogsRequestBodyItem]` — Array of span objects. Each span uses the same fields as [Create a span](/docs/api-reference/observe/spans/create-a-span).
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Health
<details><summary><code>client.health.<a href="src/respan/health/client.py">check</a>(...) -> HealthCheckResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Check API availability.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.health.check(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Threads
<details><summary><code>client.threads.<a href="src/respan/threads/client.py">list</a>(...) -> ThreadsListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve threads matching the specified filters with pagination.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.threads.list(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — The page number to retrieve.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — The number of items per page. Maximum is 1000.
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[str]` — This is controlled by the API key. A prod API key creates prod threads, test key creates test threads.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[ThreadsListRequestFilters]` — Filter criteria. See [Filters API Reference](/docs/api-reference/reference/filters-api-reference).
    
</dd>
</dl>

<dl>
<dd>

**operator:** `typing.Optional[ThreadsListRequestOperator]` — Logical operator to combine filters.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Users
<details><summary><code>client.users.<a href="src/respan/users/client.py">search</a>(...) -> UsersSearchResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve customers matching the specified filters with pagination. See [Filters API Reference](/docs/api-reference/reference/filters-api-reference) for filter syntax.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.users.search(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[float]` — Page number.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[float]` — The number of customers to return per page. Maximum is 1000.
    
</dd>
</dl>

<dl>
<dd>

**sort_by:** `typing.Optional[str]` — Sort field. Prefix with - for descending.
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[str]` — Filter by environment. Options: prod, test.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[UsersSearchRequestFilters]` — Filter criteria.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.users.<a href="src/respan/users/client.py">retrieve_user</a>(...) -> RetrieveUserResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a customer by their identifier. Returns usage stats, budgets, and metadata.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.users.retrieve_user(
    customer_identifier="customer_identifier",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**customer_identifier:** `str` — Your unique identifier for this customer.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[str]` — Specify environment if you are not using the default. Options: prod, test.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.users.<a href="src/respan/users/client.py">delete_user</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a customer by their identifier. This action is irreversible.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.users.delete_user(
    customer_identifier="customer_identifier",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**customer_identifier:** `str` — Your unique identifier for this customer.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.users.<a href="src/respan/users/client.py">update_user</a>(...) -> UpdateUserResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a customer profile. Supports name, email, metadata, and budget settings.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.users.update_user(
    customer_identifier="customer_identifier",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**customer_identifier:** `str` — Your unique identifier for this customer.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**email:** `typing.Optional[str]` — Customer email address.
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Customer display name.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Custom key-value metadata.
    
</dd>
</dl>

<dl>
<dd>

**period_budget:** `typing.Optional[float]` — Spending budget per period in USD.
    
</dd>
</dl>

<dl>
<dd>

**budget_duration:** `typing.Optional[UpdateUserRequestBudgetDuration]` — Budget reset period.
    
</dd>
</dl>

<dl>
<dd>

**total_budget:** `typing.Optional[float]` — Total lifetime spending budget in USD.
    
</dd>
</dl>

<dl>
<dd>

**markup_percentage:** `typing.Optional[float]` — Markup percentage applied to costs for this customer.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Gateway
<details><summary><code>client.gateway.<a href="src/respan/gateway/client.py">create_chat_completion</a>(...) -> CreateChatCompletionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Send a chat completion request through the Respan gateway. Supports 250+ models across OpenAI, Anthropic, Google, Azure, and more with automatic logging, fallbacks, and caching.

Accepts all [OpenAI chat completion parameters](https://platform.openai.com/docs/api-reference/chat). Respan-specific parameters can be passed three ways:
1. **Top-level body fields** - add directly to the request body
2. **Nested under `respan_params`** - explicit namespacing to avoid conflicts
3. **Header `X-Respan-Params`** - base64-encoded JSON header

Merge order: header > `respan_params` > top-level fields.

When using the OpenAI SDK, pass Respan parameters via `extra_body`.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.gateway.create_chat_completion(
    authorization="Bearer sk_live_xxxxx",
    messages=[
        "messages"
    ],
    model="gpt-4o",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**messages:** `typing.List[str]` — Array of messages in the conversation. Each message has `role` (`system`, `user`, `assistant`, `tool`) and `content`.
    
</dd>
</dl>

<dl>
<dd>

**model:** `str` — Model to use. See [Models](https://platform.respan.ai/platform/models) for available options.
    
</dd>
</dl>

<dl>
<dd>

**respan_beta:** `typing.Optional[str]` — Comma-separated beta feature flags. Available: token-breakdown-2026-03-26, env-scoped-integrations-2026-03-28
    
</dd>
</dl>

<dl>
<dd>

**stream:** `typing.Optional[bool]` — Stream back partial progress token by token as server-sent events.
    
</dd>
</dl>

<dl>
<dd>

**tools:** `typing.Optional[typing.List[typing.Dict[str, typing.Any]]]` — Tools the model may call. Currently only functions are supported.
    
</dd>
</dl>

<dl>
<dd>

**tool_choice:** `typing.Optional[typing.Dict[str, typing.Any]]` — Controls tool selection. `"none"` = no tools, `"auto"` = model decides, or specify a tool object.
    
</dd>
</dl>

<dl>
<dd>

**frequency_penalty:** `typing.Optional[float]` — Penalizes tokens based on frequency in text so far (-2 to 2).
    
</dd>
</dl>

<dl>
<dd>

**max_tokens:** `typing.Optional[float]` — Maximum tokens to generate.
    
</dd>
</dl>

<dl>
<dd>

**temperature:** `typing.Optional[float]` — Sampling temperature (0-2). Higher = more random.
    
</dd>
</dl>

<dl>
<dd>

**n:** `typing.Optional[float]` — Number of completions to generate. Note: costs multiply with `n`.
    
</dd>
</dl>

<dl>
<dd>

**logprobs:** `typing.Optional[bool]` — Return log probabilities of output tokens.
    
</dd>
</dl>

<dl>
<dd>

**echo:** `typing.Optional[bool]` — Echo back the prompt in addition to the completion
    
</dd>
</dl>

<dl>
<dd>

**stop:** `typing.Optional[typing.List[str]]` — Stop sequences where generation halts.
    
</dd>
</dl>

<dl>
<dd>

**presence_penalty:** `typing.Optional[float]` — Penalizes tokens already present in text (-2 to 2).
    
</dd>
</dl>

<dl>
<dd>

**logit_bias:** `typing.Optional[typing.Dict[str, typing.Any]]` — Used to modify the probability of tokens appearing in the response
    
</dd>
</dl>

<dl>
<dd>

**response_format:** `typing.Optional[typing.Dict[str, typing.Any]]` — Output format. Set `{"type": "json_schema", "json_schema": {...}}` for structured output, or `{"type": "json_object"}` for JSON mode.
    
</dd>
</dl>

<dl>
<dd>

**parallel_tool_calls:** `typing.Optional[bool]` — Enable parallel function calling during tool use.
    
</dd>
</dl>

<dl>
<dd>

**load_balance_group:** `typing.Optional[typing.Dict[str, typing.Any]]` — Load balance config. Specify `models` array with `model`, `weight`, and optional `credentials` per model. See [Advanced configuration](/docs/documentation/features/gateway/advanced).
    
</dd>
</dl>

<dl>
<dd>

**fallback_models:** `typing.Optional[typing.List[str]]` — Backup models (ranked by priority) if the primary model fails.
    
</dd>
</dl>

<dl>
<dd>

**customer_credentials:** `typing.Optional[typing.Dict[str, typing.Any]]` — Per-customer LLM provider credentials. Keys are provider names, values are API keys.
    
</dd>
</dl>

<dl>
<dd>

**credential_override:** `typing.Optional[typing.Dict[str, typing.Any]]` — One-off credential overrides per provider. Overrides uploaded provider keys for this request only.
    
</dd>
</dl>

<dl>
<dd>

**cache_enabled:** `typing.Optional[bool]` — Enable response caching. See [Caching](/docs/documentation/features/gateway/advanced).
    
</dd>
</dl>

<dl>
<dd>

**cache_ttl:** `typing.Optional[float]` — Cache time-to-live in seconds.
    
</dd>
</dl>

<dl>
<dd>

**cache_options:** `typing.Optional[bool]` — Cache options. Set `cache_by_customer: true` to cache per customer.
    
</dd>
</dl>

<dl>
<dd>

**prompt:** `typing.Optional[typing.Dict[str, typing.Any]]` — Prompt template config. Properties: `prompt_id` (required), `variables` (template variables), `version` (number, or `"latest"` for draft), `echo` (return rendered prompt), `override` (use override_params), `override_params` (OpenAI params to override), `schema_version` (`1` = legacy, `2` = prompt config wins). See [Prompt management](/docs/documentation/features/prompt-management/advanced).
    
</dd>
</dl>

<dl>
<dd>

**retry_params:** `typing.Optional[typing.Dict[str, typing.Any]]` — Retry config. Properties: `retry_enabled` (boolean, required), `num_retries` (number), `retry_after` (seconds to wait).
    
</dd>
</dl>

<dl>
<dd>

**disable_log:** `typing.Optional[bool]` — When `true`, omits input/output from the log. Metrics (tokens, cost, latency) are still recorded.
    
</dd>
</dl>

<dl>
<dd>

**model_name_map:** `typing.Optional[typing.Dict[str, typing.Any]]` — Azure deployment name mapping. Maps your custom Azure deployment names to standard model names.
    
</dd>
</dl>

<dl>
<dd>

**models:** `typing.Optional[typing.List[str]]` — Load balancing model list. Each item: `model` (name), `weight` (routing weight), optional `credentials`.
    
</dd>
</dl>

<dl>
<dd>

**exclude_providers:** `typing.Optional[typing.List[str]]` — Providers to exclude from routing. All models under excluded providers are skipped.
    
</dd>
</dl>

<dl>
<dd>

**exclude_models:** `typing.Optional[typing.List[str]]` — Specific models to exclude from routing.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Custom key-value metadata attached to the span.
    
</dd>
</dl>

<dl>
<dd>

**custom_identifier:** `typing.Optional[str]` — Indexed custom tag for fast querying.
    
</dd>
</dl>

<dl>
<dd>

**customer_identifier:** `typing.Optional[str]` — End user identifier for analytics and budgets.
    
</dd>
</dl>

<dl>
<dd>

**customer_params:** `typing.Optional[typing.Dict[str, typing.Any]]` — Extended customer info. Properties: `customer_identifier` (required), `group_identifier`, `name`, `email`, `period_budget`, `budget_duration` (`daily`/`weekly`/`monthly`/`yearly`), `total_budget`, `markup_percentage`.
    
</dd>
</dl>

<dl>
<dd>

**request_breakdown:** `typing.Optional[bool]` — Return response metrics summary in the response body. For streaming, metrics appear in the final chunk.
    
</dd>
</dl>

<dl>
<dd>

**positive_feedback:** `typing.Optional[bool]` — User feedback. `true` = liked, `false` = disliked.
    
</dd>
</dl>

<dl>
<dd>

**customer_api_keys:** `typing.Optional[typing.Dict[str, typing.Any]]` — You can pass in a dictionary of your customer's API keys for specific models. If the router selects a model that is in the dictionary, it will attempt to use the customer's API key for calling the model before using your integration API key or Respan's default API key.
    
</dd>
</dl>

<dl>
<dd>

**loadbalance_models:** `typing.Optional[typing.List[str]]` — Balance the load of your requests between different models. See the details of load balancing here.
    
</dd>
</dl>

<dl>
<dd>

**thread_identifier:** `typing.Optional[str]` — Conversation thread ID. Spans with the same `thread_identifier` are grouped together.
    
</dd>
</dl>

<dl>
<dd>

**properties:** `typing.Optional[typing.Dict[str, typing.Any]]` — Typed metadata preserving native types (numbers, booleans, nested objects). Unlike `metadata` which coerces to strings.
    
</dd>
</dl>

<dl>
<dd>

**retries:** `typing.Optional[int]` — Number of retries on failure.
    
</dd>
</dl>

<dl>
<dd>

**weight:** `typing.Optional[float]` — Load balancing weight.
    
</dd>
</dl>

<dl>
<dd>

**prompt_id:** `typing.Optional[str]` — Respan prompt template ID.
    
</dd>
</dl>

<dl>
<dd>

**prompt_variables:** `typing.Optional[typing.Dict[str, typing.Any]]` — Variables to inject into the prompt template.
    
</dd>
</dl>

<dl>
<dd>

**span_name:** `typing.Optional[str]` — Custom span name for tracing.
    
</dd>
</dl>

<dl>
<dd>

**respan_params:** `typing.Optional[typing.Dict[str, typing.Any]]` — Namespaced container for all Respan parameters. Alternative to passing them at top level.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.gateway.<a href="src/respan/gateway/client.py">create_response</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Send a response request through the Respan gateway using the OpenAI Responses API format. Supports streaming, tool use, and prompt management.

Respan parameters can be passed the same way as [Create chat completion](/docs/api-reference/develop/gateway/create-chat-completion): top-level fields, nested under `respan_params`, or via `X-Respan-Params` header.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.gateway.create_response(
    authorization="Bearer sk_live_xxxxx",
    model="gpt-4o",
    input="input",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**model:** `str` — Model to use.
    
</dd>
</dl>

<dl>
<dd>

**input:** `CreateResponseRequestInput` — Input text or array of conversation messages.
    
</dd>
</dl>

<dl>
<dd>

**respan_beta:** `typing.Optional[str]` — Comma-separated beta feature flags. Available: token-breakdown-2026-03-26, env-scoped-integrations-2026-03-28
    
</dd>
</dl>

<dl>
<dd>

**instructions:** `typing.Optional[str]` — System instructions for the model.
    
</dd>
</dl>

<dl>
<dd>

**stream:** `typing.Optional[bool]` — Stream the response as server-sent events.
    
</dd>
</dl>

<dl>
<dd>

**temperature:** `typing.Optional[float]` — Sampling temperature (0-2).
    
</dd>
</dl>

<dl>
<dd>

**max_output_tokens:** `typing.Optional[int]` — Maximum tokens to generate.
    
</dd>
</dl>

<dl>
<dd>

**top_p:** `typing.Optional[float]` — Nucleus sampling parameter.
    
</dd>
</dl>

<dl>
<dd>

**tools:** `typing.Optional[typing.List[typing.Dict[str, typing.Any]]]` — Tools the model may call.
    
</dd>
</dl>

<dl>
<dd>

**previous_response_id:** `typing.Optional[str]` — ID of a previous response for multi-turn conversations.
    
</dd>
</dl>

<dl>
<dd>

**fallback_models:** `typing.Optional[typing.List[str]]` — Backup models if the primary model fails.
    
</dd>
</dl>

<dl>
<dd>

**customer_credentials:** `typing.Optional[typing.Dict[str, typing.Any]]` — Per-customer LLM provider credentials.
    
</dd>
</dl>

<dl>
<dd>

**credential_override:** `typing.Optional[typing.Dict[str, typing.Any]]` — One-off credential overrides per provider.
    
</dd>
</dl>

<dl>
<dd>

**cache_enabled:** `typing.Optional[bool]` — Enable response caching.
    
</dd>
</dl>

<dl>
<dd>

**cache_ttl:** `typing.Optional[int]` — Cache TTL in seconds.
    
</dd>
</dl>

<dl>
<dd>

**prompt:** `typing.Optional[typing.Dict[str, typing.Any]]` — Prompt template config. Properties: `prompt_id` (required), `variables`, `version`, `echo`. See [Prompt management](/docs/documentation/features/prompt-management/advanced).
    
</dd>
</dl>

<dl>
<dd>

**retry_params:** `typing.Optional[typing.Dict[str, typing.Any]]` — Retry config. Properties: `retry_enabled` (boolean), `num_retries`, `retry_after` (seconds).
    
</dd>
</dl>

<dl>
<dd>

**disable_log:** `typing.Optional[bool]` — When `true`, omits input/output from the log. Metrics still recorded.
    
</dd>
</dl>

<dl>
<dd>

**models:** `typing.Optional[typing.List[typing.Dict[str, typing.Any]]]` — Load balancing model list.
    
</dd>
</dl>

<dl>
<dd>

**exclude_providers:** `typing.Optional[typing.List[str]]` — Providers to exclude from routing.
    
</dd>
</dl>

<dl>
<dd>

**exclude_models:** `typing.Optional[typing.List[str]]` — Models to exclude from routing.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Custom key-value metadata attached to the span.
    
</dd>
</dl>

<dl>
<dd>

**custom_identifier:** `typing.Optional[str]` — Indexed custom tag for fast querying.
    
</dd>
</dl>

<dl>
<dd>

**customer_identifier:** `typing.Optional[str]` — End user identifier for analytics and budgets.
    
</dd>
</dl>

<dl>
<dd>

**customer_params:** `typing.Optional[typing.Dict[str, typing.Any]]` — Extended customer info.
    
</dd>
</dl>

<dl>
<dd>

**thread_identifier:** `typing.Optional[str]` — Conversation thread ID.
    
</dd>
</dl>

<dl>
<dd>

**positive_feedback:** `typing.Optional[bool]` — User feedback. `true` = liked, `false` = disliked.
    
</dd>
</dl>

<dl>
<dd>

**properties:** `typing.Optional[typing.Dict[str, typing.Any]]` — Typed metadata preserving native types.
    
</dd>
</dl>

<dl>
<dd>

**respan_params:** `typing.Optional[typing.Dict[str, typing.Any]]` — Namespaced container for all Respan parameters.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## OpenAI Batch
<details><summary><code>client.open_ai_batch.<a href="src/respan/open_ai_batch/client.py">list_files</a>(...) -> ListFilesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all uploaded files.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.open_ai_batch.list_files(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.open_ai_batch.<a href="src/respan/open_ai_batch/client.py">upload_file</a>(...) -> UploadFileResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Upload a JSONL file for batch processing.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.open_ai_batch.upload_file(
    authorization="Bearer sk_live_xxxxx",
    file="example_file",
    purpose="batch",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**file:** `core.File` — The JSONL file to upload.
    
</dd>
</dl>

<dl>
<dd>

**purpose:** `UploadFileRequestPurpose` — Intended purpose of the file.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.open_ai_batch.<a href="src/respan/open_ai_batch/client.py">retrieve_file</a>(...) -> RetrieveFileResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve metadata for a specific file.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.open_ai_batch.retrieve_file(
    file_id="file_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**file_id:** `str` — The unique identifier of the file to retrieve. Format: file-xxxxx
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.open_ai_batch.<a href="src/respan/open_ai_batch/client.py">delete_file</a>(...) -> DeleteFileResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete an uploaded file.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.open_ai_batch.delete_file(
    file_id="file_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**file_id:** `str` — The unique identifier of the file to delete. Format: file-xxxxx
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.open_ai_batch.<a href="src/respan/open_ai_batch/client.py">retrieve_file_content</a>(...) -> typing.Iterator[bytes]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Download the content of a file. For batch output files, returns JSONL with results for each request.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.open_ai_batch.retrieve_file_content(
    file_id="file_id",
    authorization="authorization",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**file_id:** `str` — The unique identifier of the file whose content you want to download. Format: file-xxxxx
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.open_ai_batch.<a href="src/respan/open_ai_batch/client.py">list_batches</a>(...) -> ListBatchesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List batch processing jobs with pagination.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.open_ai_batch.list_batches(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Maximum number of batches to return.
    
</dd>
</dl>

<dl>
<dd>

**after:** `typing.Optional[str]` — Cursor for pagination. Use the last_id from a previous response to get the next page.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.open_ai_batch.<a href="src/respan/open_ai_batch/client.py">create_batch</a>(...) -> CreateBatchResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new batch processing job from an uploaded JSONL file.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.open_ai_batch.create_batch(
    authorization="Bearer sk_live_xxxxx",
    input_file_id="file-abc123",
    endpoint="/v1/chat/completions",
    completion_window="24h",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**input_file_id:** `str` — ID of the uploaded JSONL file. Get from Upload file endpoint.
    
</dd>
</dl>

<dl>
<dd>

**endpoint:** `CreateBatchRequestEndpoint` — API endpoint for batch requests.
    
</dd>
</dl>

<dl>
<dd>

**completion_window:** `CreateBatchRequestCompletionWindow` — Processing time frame.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Custom key-value pairs for tracking.
    
</dd>
</dl>

<dl>
<dd>

**customer_identifier:** `typing.Optional[str]` — End user identifier.
    
</dd>
</dl>

<dl>
<dd>

**custom_identifier:** `typing.Optional[str]` — Custom identifier for fast querying.
    
</dd>
</dl>

<dl>
<dd>

**thread_identifier:** `typing.Optional[str]` — Conversation thread ID.
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[str]` — Environment tag.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.open_ai_batch.<a href="src/respan/open_ai_batch/client.py">retrieve_batch</a>(...) -> RetrieveBatchResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve details of a batch processing job.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.open_ai_batch.retrieve_batch(
    batch_id="batch_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**batch_id:** `str` — The unique identifier of the batch to retrieve. Format: batch_xxxxx
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.open_ai_batch.<a href="src/respan/open_ai_batch/client.py">cancel_batch</a>(...) -> CancelBatchResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Cancel an in-progress batch. Already completed requests in the batch are not affected.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.open_ai_batch.cancel_batch(
    batch_id="batch_id",
    authorization="Bearer sk_live_xxxxx",
    request={
        "key": "value"
    },
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**batch_id:** `str` — The unique identifier of the batch to cancel. Format: batch_xxxxx
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Dict[str, typing.Any]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Multimodal
<details><summary><code>client.multimodal.<a href="src/respan/multimodal/client.py">embeddings</a>(...) -> EmbeddingsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create embeddings through the Respan gateway with automatic logging.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.multimodal.embeddings(
    authorization="Bearer sk_live_xxxxx",
    model="text-embedding-3-small",
    input="Hello world",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**model:** `EmbeddingsRequestModel` — Embedding model ID.
    
</dd>
</dl>

<dl>
<dd>

**input:** `typing.Any` 
    
</dd>
</dl>

<dl>
<dd>

**encoding_format:** `typing.Optional[EmbeddingsRequestEncodingFormat]` — Output format.
    
</dd>
</dl>

<dl>
<dd>

**dimensions:** `typing.Optional[int]` — Output embedding dimensions. Only supported by `text-embedding-3-*` models.
    
</dd>
</dl>

<dl>
<dd>

**customer_credentials:** `typing.Optional[typing.Dict[str, typing.Any]]` — Per-customer LLM provider credentials.
    
</dd>
</dl>

<dl>
<dd>

**disable_log:** `typing.Optional[bool]` — When `true`, omits input/output from the log. Metrics still recorded.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Custom key-value metadata.
    
</dd>
</dl>

<dl>
<dd>

**customer_identifier:** `typing.Optional[str]` — End user identifier.
    
</dd>
</dl>

<dl>
<dd>

**customer_email:** `typing.Optional[str]` — Customer email address.
    
</dd>
</dl>

<dl>
<dd>

**thread_identifier:** `typing.Optional[str]` — Conversation thread ID.
    
</dd>
</dl>

<dl>
<dd>

**request_breakdown:** `typing.Optional[bool]` — Return response metrics summary in the response body.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.multimodal.<a href="src/respan/multimodal/client.py">speech_to_text</a>(...) -> SpeechToTextResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Transcribe audio to text through the Respan gateway with automatic logging.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.multimodal.speech_to_text(
    authorization="Bearer sk_live_xxxxx",
    file="example_file",
    model="whisper-1",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**file:** `core.File` — Audio file. Supported: flac, mp3, mp4, mpeg, mpga, m4a, ogg, wav, webm.
    
</dd>
</dl>

<dl>
<dd>

**model:** `SpeechToTextRequestModel` — Model ID.
    
</dd>
</dl>

<dl>
<dd>

**language:** `typing.Optional[str]` — Input audio language (ISO-639-1).
    
</dd>
</dl>

<dl>
<dd>

**prompt:** `typing.Optional[str]` — Optional text to guide the model's style.
    
</dd>
</dl>

<dl>
<dd>

**response_format:** `typing.Optional[SpeechToTextRequestResponseFormat]` — Output format.
    
</dd>
</dl>

<dl>
<dd>

**temperature:** `typing.Optional[float]` — Sampling temperature (0-1).
    
</dd>
</dl>

<dl>
<dd>

**timestamp_granularities:** `typing.Optional[typing.List[str]]` — Timestamp granularities. Requires `verbose_json` response format.
    
</dd>
</dl>

<dl>
<dd>

**customer_credentials:** `typing.Optional[typing.Dict[str, typing.Any]]` — Per-customer LLM provider credentials.
    
</dd>
</dl>

<dl>
<dd>

**disable_log:** `typing.Optional[bool]` — When `true`, omits input/output from the log. Metrics still recorded.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Custom key-value metadata.
    
</dd>
</dl>

<dl>
<dd>

**customer_identifier:** `typing.Optional[str]` — End user identifier.
    
</dd>
</dl>

<dl>
<dd>

**customer_email:** `typing.Optional[str]` — Customer email address.
    
</dd>
</dl>

<dl>
<dd>

**thread_identifier:** `typing.Optional[str]` — Conversation thread ID.
    
</dd>
</dl>

<dl>
<dd>

**request_breakdown:** `typing.Optional[bool]` — Return response metrics summary in the response body.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.multimodal.<a href="src/respan/multimodal/client.py">text_to_speech</a>(...) -> typing.Iterator[bytes]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Convert text to speech through the Respan gateway with automatic logging.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.multimodal.text_to_speech(
    authorization="authorization",
    model="tts-1",
    input="input",
    voice="alloy",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**model:** `TextToSpeechRequestModel` — TTS model.
    
</dd>
</dl>

<dl>
<dd>

**input:** `str` — Text to generate audio for. Max 4096 characters.
    
</dd>
</dl>

<dl>
<dd>

**voice:** `TextToSpeechRequestVoice` — Voice to use.
    
</dd>
</dl>

<dl>
<dd>

**response_format:** `typing.Optional[TextToSpeechRequestResponseFormat]` — Audio output format.
    
</dd>
</dl>

<dl>
<dd>

**speed:** `typing.Optional[float]` — Audio speed (0.25 to 4.0).
    
</dd>
</dl>

<dl>
<dd>

**customer_credentials:** `typing.Optional[typing.Dict[str, typing.Any]]` — Per-customer LLM provider credentials.
    
</dd>
</dl>

<dl>
<dd>

**disable_log:** `typing.Optional[bool]` — When `true`, omits input/output from the log. Metrics still recorded.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Custom key-value metadata.
    
</dd>
</dl>

<dl>
<dd>

**customer_identifier:** `typing.Optional[str]` — End user identifier.
    
</dd>
</dl>

<dl>
<dd>

**customer_email:** `typing.Optional[str]` — Customer email address.
    
</dd>
</dl>

<dl>
<dd>

**thread_identifier:** `typing.Optional[str]` — Conversation thread ID.
    
</dd>
</dl>

<dl>
<dd>

**request_breakdown:** `typing.Optional[bool]` — Return response metrics summary in the response body.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.multimodal.<a href="src/respan/multimodal/client.py">assemblyai_integration</a>(...) -> AssemblyaiIntegrationResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve an AssemblyAI transcript by ID. Proxied through Respan for logging.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.multimodal.assemblyai_integration(
    transcript_id="transcript_id",
    authorization="Bearer sk_live_xxxxx",
    assemblyai_api_key="X-Assemblyai-Api-Key",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**transcript_id:** `str` — The AssemblyAI transcript ID to retrieve.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**assemblyai_api_key:** `str` — Your AssemblyAI API key for authentication with AssemblyAI services.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Prompts
<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">list_prompts</a>(...) -> ListPromptsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List prompts with pagination and sorting.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.list_prompts(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Number of items per page (max: 100)
    
</dd>
</dl>

<dl>
<dd>

**sort_by:** `typing.Optional[ListPromptsRequestSortBy]` — Sort field (e.g., -current_version__updated_at, -id)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">create_prompt</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new prompt template.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.create_prompt(
    authorization="Bearer sk_live_xxxxx",
    name="customer_support",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Prompt name.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Prompt description.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">retrieve_prompt</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a single prompt by ID, including its current deployed version.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.retrieve_prompt(
    prompt_id="prompt_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**prompt_id:** `str` — The unique prompt identifier
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">delete_prompt</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a prompt and all its versions.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.delete_prompt(
    prompt_id="prompt_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**prompt_id:** `str` — Prompt Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">update_prompt</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a prompt's name or description.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.update_prompt(
    prompt_id="prompt_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**prompt_id:** `str` — Prompt Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Prompt name.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Prompt description.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">retrieve_versions</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all versions of a prompt.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.retrieve_versions(
    prompt_id="prompt_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**prompt_id:** `str` — Prompt Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">create_version</a>(...) -> CreateVersionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new version of a prompt. Use `{{variable_name}}` syntax in messages to define template variables.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.create_version(
    prompt_id="prompt_id",
    authorization="Bearer sk_live_xxxxx",
    messages=[
        "messages"
    ],
    model="gpt-4o",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**prompt_id:** `str` — Prompt Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**messages:** `typing.List[str]` — Messages for this version. Use `{{variable_name}}` for template variables.
    
</dd>
</dl>

<dl>
<dd>

**model:** `str` — Model for this version.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Version description.
    
</dd>
</dl>

<dl>
<dd>

**stream:** `typing.Optional[bool]` — Whether to stream responses.
    
</dd>
</dl>

<dl>
<dd>

**temperature:** `typing.Optional[float]` — Sampling temperature (0-2).
    
</dd>
</dl>

<dl>
<dd>

**max_tokens:** `typing.Optional[int]` — Maximum tokens to generate.
    
</dd>
</dl>

<dl>
<dd>

**top_p:** `typing.Optional[float]` — Nucleus sampling parameter.
    
</dd>
</dl>

<dl>
<dd>

**frequency_penalty:** `typing.Optional[float]` — Frequency penalty (-2 to 2).
    
</dd>
</dl>

<dl>
<dd>

**presence_penalty:** `typing.Optional[float]` — Presence penalty (-2 to 2).
    
</dd>
</dl>

<dl>
<dd>

**variables:** `typing.Optional[typing.Dict[str, typing.Any]]` — Template variables and their default values.
    
</dd>
</dl>

<dl>
<dd>

**fallback_models:** `typing.Optional[typing.List[str]]` — Fallback models if the primary model fails.
    
</dd>
</dl>

<dl>
<dd>

**tools:** `typing.Optional[typing.List[str]]` — Tools available to the model (function calling).
    
</dd>
</dl>

<dl>
<dd>

**deploy:** `typing.Optional[bool]` — Deploy this version as the live version.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">retrieve_prompt_version</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a specific version of a prompt.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.retrieve_prompt_version(
    prompt_id="prompt_id",
    version="version",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**prompt_id:** `str` — The unique prompt identifier
    
</dd>
</dl>

<dl>
<dd>

**version:** `str` — The version number
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">delete_version</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a specific prompt version. Cannot delete the currently deployed version.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.delete_version(
    prompt_id="prompt_id",
    version="version",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**prompt_id:** `str` — Prompt Id
    
</dd>
</dl>

<dl>
<dd>

**version:** `str` — Version
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">update_prompt_version</a>(...) -> UpdatePromptVersionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a prompt version's messages, model, parameters, or deploy it as the live version.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.update_prompt_version(
    prompt_id="prompt_id",
    version="version",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**prompt_id:** `str` — Prompt Id
    
</dd>
</dl>

<dl>
<dd>

**version:** `str` — Version
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**messages:** `typing.Optional[typing.List[typing.Any]]` — Messages for this version. Use `{{variable_name}}` for template variables.
    
</dd>
</dl>

<dl>
<dd>

**model:** `typing.Optional[str]` — Model for this version.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Version description.
    
</dd>
</dl>

<dl>
<dd>

**stream:** `typing.Optional[bool]` — Whether to stream responses.
    
</dd>
</dl>

<dl>
<dd>

**temperature:** `typing.Optional[float]` — Sampling temperature (0-2).
    
</dd>
</dl>

<dl>
<dd>

**max_tokens:** `typing.Optional[int]` — Maximum tokens to generate.
    
</dd>
</dl>

<dl>
<dd>

**top_p:** `typing.Optional[float]` — Nucleus sampling parameter.
    
</dd>
</dl>

<dl>
<dd>

**frequency_penalty:** `typing.Optional[float]` — Frequency penalty (-2 to 2).
    
</dd>
</dl>

<dl>
<dd>

**presence_penalty:** `typing.Optional[float]` — Presence penalty (-2 to 2).
    
</dd>
</dl>

<dl>
<dd>

**variables:** `typing.Optional[typing.Dict[str, typing.Any]]` — Template variables and default values.
    
</dd>
</dl>

<dl>
<dd>

**fallback_models:** `typing.Optional[typing.List[str]]` — Fallback models.
    
</dd>
</dl>

<dl>
<dd>

**tools:** `typing.Optional[typing.List[typing.Any]]` — Tools for function calling.
    
</dd>
</dl>

<dl>
<dd>

**deploy:** `typing.Optional[bool]` — Deploy this version as the live version.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">commit_draft_version</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Commit the current prompt version with a description message.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.commit_draft_version(
    prompt_id="prompt_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**prompt_id:** `str` — The unique prompt identifier
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Commit message describing the changes.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">deploy_committed_version</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deploy a specific version as the live version. All API calls referencing this prompt will use the deployed version.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.deploy_committed_version(
    prompt_id="prompt_id",
    authorization="Bearer sk_live_xxxxx",
    version=3,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**prompt_id:** `str` — The unique prompt identifier
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**version:** `int` — Version number to deploy as live.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">get_prompts_summary</a>(...) -> GetPromptsSummaryResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get aggregated summary statistics for all prompts.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.get_prompts_summary(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.prompts.<a href="src/respan/prompts/client.py">get_prompts_summary_with_filters</a>(...) -> GetPromptsSummaryWithFiltersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get aggregated summary statistics for prompts matching the given filters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.prompts.get_prompts_summary_with_filters(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Testsets
<details><summary><code>client.testsets.<a href="src/respan/testsets/client.py">create_testset</a>(...) -> CreateTestsetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new testset for evaluation.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.testsets.create_testset(
    authorization="Bearer sk_live_xxxxx",
    name="QA Test Set",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Testset name.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Testset description.
    
</dd>
</dl>

<dl>
<dd>

**column_definitions:** `typing.Optional[typing.List[CreateTestsetRequestColumnDefinitionsItem]]` — Column definitions for the testset.
    
</dd>
</dl>

<dl>
<dd>

**starred:** `typing.Optional[bool]` — Star the testset.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.testsets.<a href="src/respan/testsets/client.py">list_testsets</a>(...) -> ListTestsetsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List testsets with optional filtering.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.testsets.list_testsets(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[typing.Dict[str, typing.Any]]` — Filter criteria.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.testsets.<a href="src/respan/testsets/client.py">retrieve_testset</a>(...) -> RetrieveTestsetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a testset by ID, including column definitions.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.testsets.retrieve_testset(
    testset_id="testset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**testset_id:** `str` — The ID of the testset to retrieve.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.testsets.<a href="src/respan/testsets/client.py">delete_testset</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a testset and all its rows.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.testsets.delete_testset(
    testset_id="testset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**testset_id:** `str` — The ID of the testset to delete.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.testsets.<a href="src/respan/testsets/client.py">update_testset</a>(...) -> UpdateTestsetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a testset's name, description, or starred status.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.testsets.update_testset(
    testset_id="testset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**testset_id:** `str` — The ID of the testset to update.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Testset name.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Testset description.
    
</dd>
</dl>

<dl>
<dd>

**starred:** `typing.Optional[bool]` — Star the testset.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.testsets.<a href="src/respan/testsets/client.py">list_testset_rows</a>(...) -> ListTestsetRowsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all rows in a testset.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.testsets.list_testset_rows(
    testset_id="testset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**testset_id:** `str` — The ID of the testset to list rows from.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.testsets.<a href="src/respan/testsets/client.py">create_testset_rows</a>(...) -> CreateTestsetRowsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add rows to a testset.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment
from respan.testsets import CreateTestsetRowsRequestBodyItem

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.testsets.create_testset_rows(
    testset_id="testset_id",
    authorization="Bearer sk_live_xxxxx",
    request=[
        CreateTestsetRowsRequestBodyItem()
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**testset_id:** `str` — The ID of the testset to add rows to.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.List[CreateTestsetRowsRequestBodyItem]` — Array of row objects.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.testsets.<a href="src/respan/testsets/client.py">delete_testset_row</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a specific row from a testset.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.testsets.delete_testset_row(
    testset_id="testset_id",
    row_index=1,
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**testset_id:** `str` — The ID of the testset.
    
</dd>
</dl>

<dl>
<dd>

**row_index:** `int` — The index of the row to delete.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.testsets.<a href="src/respan/testsets/client.py">update_testset_row</a>(...) -> UpdateTestsetRowResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a specific row in a testset.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.testsets.update_testset_row(
    testset_id="testset_id",
    row_index=1,
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**testset_id:** `str` — The ID of the testset.
    
</dd>
</dl>

<dl>
<dd>

**row_index:** `int` — The index of the row to update.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**row_data:** `typing.Optional[typing.Dict[str, typing.Any]]` — Updated row data keyed by column name.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Experiments
<details><summary><code>client.experiments.<a href="src/respan/experiments/client.py">create_experiment</a>(...) -> CreateExperimentResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new experiment with workflows. Supports custom (submit results via API), completion (auto-run LLM calls), and prompt (test prompt versions) workflow types.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.experiments.create_experiment(
    authorization="Bearer sk_live_xxxxx",
    name="model-comparison",
    dataset_id="ds_abc123",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Experiment name.
    
</dd>
</dl>

<dl>
<dd>

**dataset_id:** `str` — Dataset ID to run against.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Experiment description.
    
</dd>
</dl>

<dl>
<dd>

**workflows:** `typing.Optional[typing.List[CreateExperimentRequestWorkflowsItem]]` — Array of workflow configs. Each has `type`, `config`, and optional settings.
    
</dd>
</dl>

<dl>
<dd>

**evaluator_slugs:** `typing.Optional[typing.List[str]]` — Evaluator slugs to auto-run on results.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.experiments.<a href="src/respan/experiments/client.py">search_experiment</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Search experiments with filters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.experiments.search_experiment(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.experiments.<a href="src/respan/experiments/client.py">retrieve_experiment</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve an experiment by ID, including its workflows and configuration.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.experiments.retrieve_experiment(
    experiment_id="experiment_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**experiment_id:** `str` — The ID of the experiment to retrieve.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.experiments.<a href="src/respan/experiments/client.py">delete_experiment</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete an experiment and all its results.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.experiments.delete_experiment(
    experiment_id="experiment_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**experiment_id:** `str` — The ID of the experiment to delete.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.experiments.<a href="src/respan/experiments/client.py">search_experiment_spans</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Search experiment spans with filters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.experiments.search_experiment_spans(
    experiment_id="experiment_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**experiment_id:** `str` — The ID of the experiment to search spans for.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.experiments.<a href="src/respan/experiments/client.py">retrieve_experiment_span</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a single span (result) from an experiment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.experiments.retrieve_experiment_span(
    experiment_id="experiment_id",
    log_id="log_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**experiment_id:** `str` — The ID of the experiment.
    
</dd>
</dl>

<dl>
<dd>

**log_id:** `str` — The ID of the log to retrieve.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.experiments.<a href="src/respan/experiments/client.py">update_experiment_span</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a span in an experiment. Supports updating output, metadata, and scores.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.experiments.update_experiment_span(
    experiment_id="experiment_id",
    log_id="log_id",
    authorization="Bearer sk_live_xxxxx",
    request={
        "key": "value"
    },
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**experiment_id:** `str` — The ID of the experiment.
    
</dd>
</dl>

<dl>
<dd>

**log_id:** `str` — The ID of the log to update.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Dict[str, typing.Any]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.experiments.<a href="src/respan/experiments/client.py">get_experiment_spans_summary</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get aggregated statistics for spans in an experiment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.experiments.get_experiment_spans_summary(
    experiment_id="experiment_id",
    start_time="start_time",
    end_time="end_time",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**experiment_id:** `str` — The ID of the experiment to get summary statistics for.
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `str` — Filter start time (ISO format).
    
</dd>
</dl>

<dl>
<dd>

**end_time:** `str` — Filter end time (ISO format).
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.experiments.<a href="src/respan/experiments/client.py">export_experiment_spans</a>(...) -> ExportExperimentSpansResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all experiment spans. Supports pagination and sorting.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.experiments.export_experiment_spans(
    experiment_id="experiment_id",
    export="export",
    page=1,
    page_size=1,
    sort_by="sort_by",
    start_time="start_time",
    end_time="end_time",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**experiment_id:** `str` — The ID of the experiment to export spans from.
    
</dd>
</dl>

<dl>
<dd>

**export:** `str` — Set to 1 or true to trigger export.
    
</dd>
</dl>

<dl>
<dd>

**page:** `int` — Page number (default: 1).
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `int` — Number of results per page (default: 100).
    
</dd>
</dl>

<dl>
<dd>

**sort_by:** `str` — Sort field (e.g., "-cost", "-start_time", "name").
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `str` — Filter start time (ISO format).
    
</dd>
</dl>

<dl>
<dd>

**end_time:** `str` — Filter end time (ISO format).
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Evaluators
<details><summary><code>client.evaluators.<a href="src/respan/evaluators/client.py">create_evaluator</a>(...) -> CreateEvaluatorResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new evaluator for scoring LLM outputs. Specify `type` and `score_value_type`. Optionally use `eval_class` for pre-built templates.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.evaluators.create_evaluator(
    authorization="Bearer sk_live_xxxxx",
    name="Response Quality",
    type="llm",
    score_value_type="numerical",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Evaluator display name.
    
</dd>
</dl>

<dl>
<dd>

**type:** `CreateEvaluatorRequestType` — Evaluator type.
    
</dd>
</dl>

<dl>
<dd>

**score_value_type:** `CreateEvaluatorRequestScoreValueType` — Score format.
    
</dd>
</dl>

<dl>
<dd>

**evaluator_slug:** `typing.Optional[str]` — Unique identifier. Auto-generated if not provided.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Evaluator description.
    
</dd>
</dl>

<dl>
<dd>

**eval_class:** `typing.Optional[CreateEvaluatorRequestEvalClass]` — Pre-built template.
    
</dd>
</dl>

<dl>
<dd>

**categorical_choices:** `typing.Optional[typing.List[CreateEvaluatorRequestCategoricalChoicesItem]]` — Required for `single_select` or `multi_select` score types.
    
</dd>
</dl>

<dl>
<dd>

**score_config:** `typing.Optional[CreateEvaluatorRequestScoreConfig]` — Score type configuration. For numerical/percentage: `min_score`, `max_score`. For single/multi select: `choices` array.
    
</dd>
</dl>

<dl>
<dd>

**passing_conditions:** `typing.Optional[typing.Dict[str, typing.Any]]` — Conditions for passing. Uses filter format (e.g. `{"primary_score": {"operator": "gte", "value": 3}}`).
    
</dd>
</dl>

<dl>
<dd>

**llm_config:** `typing.Optional[CreateEvaluatorRequestLlmConfig]` — LLM automation config. Required fields: `model`, `evaluator_definition`.
    
</dd>
</dl>

<dl>
<dd>

**code_config:** `typing.Optional[CreateEvaluatorRequestCodeConfig]` — Code automation config.
    
</dd>
</dl>

<dl>
<dd>

**configurations:** `typing.Optional[CreateEvaluatorRequestConfigurations]` — Legacy configuration format. Use `llm_config`/`code_config` instead for new evaluators.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.evaluators.<a href="src/respan/evaluators/client.py">retrieve_evaluator</a>(...) -> RetrieveEvaluatorResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve an evaluator by ID, including its full configuration.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.evaluators.retrieve_evaluator(
    evaluator_id="evaluator_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**evaluator_id:** `str` — Evaluator Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.evaluators.<a href="src/respan/evaluators/client.py">delete_evaluator</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete an evaluator.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.evaluators.delete_evaluator(
    evaluator_id="evaluator_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**evaluator_id:** `str` — Evaluator Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.evaluators.<a href="src/respan/evaluators/client.py">update_evaluator</a>(...) -> UpdateEvaluatorResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update an evaluator's configuration, scoring, or automation settings.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.evaluators.update_evaluator(
    evaluator_id="evaluator_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**evaluator_id:** `str` — Evaluator Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Evaluator name.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**score_value_type:** `typing.Optional[UpdateEvaluatorRequestScoreValueType]` 
    
</dd>
</dl>

<dl>
<dd>

**categorical_choices:** `typing.Optional[typing.List[typing.Dict[str, typing.Any]]]` 
    
</dd>
</dl>

<dl>
<dd>

**score_config:** `typing.Optional[typing.Dict[str, typing.Any]]` — Score configuration.
    
</dd>
</dl>

<dl>
<dd>

**passing_conditions:** `typing.Optional[typing.Dict[str, typing.Any]]` — Passing conditions.
    
</dd>
</dl>

<dl>
<dd>

**llm_config:** `typing.Optional[typing.Dict[str, typing.Any]]` — LLM automation config.
    
</dd>
</dl>

<dl>
<dd>

**code_config:** `typing.Optional[typing.Dict[str, typing.Any]]` — Code automation config.
    
</dd>
</dl>

<dl>
<dd>

**configurations:** `typing.Optional[typing.Dict[str, typing.Any]]` — Legacy config format.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.evaluators.<a href="src/respan/evaluators/client.py">run_evaluator</a>(...) -> RunEvaluatorResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Run an evaluator against spans or a dataset to generate scores.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.evaluators.run_evaluator(
    evaluator_id="evaluator_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**evaluator_id:** `str` — Evaluator Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**log_ids:** `typing.Optional[typing.List[str]]` — Span IDs to evaluate.
    
</dd>
</dl>

<dl>
<dd>

**dataset_id:** `typing.Optional[str]` — Dataset ID to evaluate all spans in.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.evaluators.<a href="src/respan/evaluators/client.py">list_evaluators</a>(...) -> typing.List[ListEvaluatorsResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List evaluators with optional filters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.evaluators.list_evaluators(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Datasets
<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">retrieve_dataset</a>(...) -> RetrieveDatasetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a dataset by ID.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.retrieve_dataset(
    dataset_id="dataset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — Dataset Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">delete_dataset</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a dataset and all its spans.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.delete_dataset(
    dataset_id="dataset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — Dataset Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">update_dataset</a>(...) -> UpdateDatasetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a dataset's name or description.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.update_dataset(
    dataset_id="dataset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — Dataset Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Dataset name.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Dataset description.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">create_dataset</a>(...) -> CreateDatasetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new dataset, either empty or populated from existing spans using filters and sampling.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.create_dataset(
    authorization="Bearer sk_live_xxxxx",
    name="qa-test-set",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Dataset name.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Dataset description.
    
</dd>
</dl>

<dl>
<dd>

**sampling:** `typing.Optional[int]` — Sampling rate (0-1). Fraction of matching spans to include.
    
</dd>
</dl>

<dl>
<dd>

**start_time:** `typing.Optional[str]` — Start of time range for selecting spans (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**end_time:** `typing.Optional[str]` — End of time range for selecting spans (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**is_empty:** `typing.Optional[bool]` — Create an empty dataset (no initial spans).
    
</dd>
</dl>

<dl>
<dd>

**initial_log_filters:** `typing.Optional[typing.Dict[str, typing.Any]]` — Filters for selecting initial spans. Same format as [Filters API](/docs/api-reference/reference/filters-api-reference).
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">list_datasets</a>(...) -> ListDatasetsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List datasets with pagination and filters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.list_datasets(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Results per page.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">listspanswithfilters</a>(...) -> DatasetsListSpansWithFiltersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List spans in a dataset with filters and pagination. See [Filters API Reference](/docs/api-reference/reference/filters-api-reference).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.listspanswithfilters(
    dataset_id="dataset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — Dataset Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">create_dataset_span</a>(...) -> CreateDatasetSpanResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new span in a dataset.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.create_dataset_span(
    dataset_id="dataset_id",
    authorization="Bearer sk_live_xxxxx",
    input="What is 2+2?",
    output="4",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — Dataset Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**input:** `str` — Span input data.
    
</dd>
</dl>

<dl>
<dd>

**output:** `str` — Span output data.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Custom key-value metadata.
    
</dd>
</dl>

<dl>
<dd>

**metrics:** `typing.Optional[typing.Dict[str, typing.Any]]` — Performance metrics.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">retrievespan</a>(...) -> DatasetsRetrieveSpanResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a single span from a dataset.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.retrievespan(
    dataset_id="dataset_id",
    log_id="log_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — Dataset Id
    
</dd>
</dl>

<dl>
<dd>

**log_id:** `str` — Log Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">delete_span</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a single span from a dataset.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.delete_span(
    dataset_id="dataset_id",
    log_id="log_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — Dataset Id
    
</dd>
</dl>

<dl>
<dd>

**log_id:** `str` — Log Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">update_span_partial</a>(...) -> UpdateSpanPartialResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update fields on a span in a dataset. Only provided fields are updated.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.update_span_partial(
    dataset_id="dataset_id",
    log_id="log_id",
    authorization="Bearer sk_live_xxxxx",
    request={
        "key": "value"
    },
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — Dataset Id
    
</dd>
</dl>

<dl>
<dd>

**log_id:** `str` — Log Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Dict[str, typing.Any]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">delete_spans</a>(...) -> DeleteSpansResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete spans from a dataset by filters, or delete all spans.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.delete_spans(
    dataset_id="dataset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — Dataset Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**is_deleting_all_logs:** `typing.Optional[bool]` — Delete all spans in the dataset. Required if no `filters` provided.
    
</dd>
</dl>

<dl>
<dd>

**filters:** `typing.Optional[Filters]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">add_spans_to_dataset</a>(...) -> AddSpansToDatasetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add existing spans to a dataset by their IDs.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.add_spans_to_dataset(
    dataset_id="dataset_id",
    authorization="Bearer sk_live_xxxxx",
    log_ids=[
        "log_abc",
        "log_def"
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — Dataset Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**log_ids:** `typing.List[str]` — Array of span IDs to add.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">run_eval_on_dataset</a>(...) -> RunEvalOnDatasetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Run evaluators on all spans in a dataset.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.run_eval_on_dataset(
    dataset_id="dataset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — The ID of the dataset to run evaluations on.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**evaluator_ids:** `typing.Optional[typing.List[str]]` — Evaluator IDs to run.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.datasets.<a href="src/respan/datasets/client.py">list_eval_runs</a>(...) -> ListEvalRunsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List evaluation runs for a dataset.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.datasets.list_eval_runs(
    dataset_id="dataset_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataset_id:** `str` — The ID of the dataset to list evaluation reports for.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Scores
<details><summary><code>client.scores.<a href="src/respan/scores/client.py">list_scores</a>(...) -> ListScoresResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all evaluation scores with pagination.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.scores.list_scores(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.scores.<a href="src/respan/scores/client.py">create_score</a>(...) -> CreateScoreResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new evaluation score.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.scores.create_score(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**evaluator_id:** `typing.Optional[str]` — UUID of evaluator created in Respan. Either this or `evaluator_slug` must be provided.
    
</dd>
</dl>

<dl>
<dd>

**evaluator_slug:** `typing.Optional[str]` — Custom string identifier for your evaluator. Either this or `evaluator_id` must be provided.
    
</dd>
</dl>

<dl>
<dd>

**numerical_value:** `typing.Optional[float]` — Numerical score value. Use when evaluator's `score_value_type` is `numerical`.
    
</dd>
</dl>

<dl>
<dd>

**string_value:** `typing.Optional[str]` — String/text score value. Use when `score_value_type` is `text` or `comment`.
    
</dd>
</dl>

<dl>
<dd>

**boolean_value:** `typing.Optional[bool]` — Boolean score value. Use when `score_value_type` is `boolean`.
    
</dd>
</dl>

<dl>
<dd>

**categorical_value:** `typing.Optional[typing.List[str]]` — Categorical score value. Use when `score_value_type` is `single_select`, `multi_select`, or `categorical`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.scores.<a href="src/respan/scores/client.py">retrieve_score</a>(...) -> RetrieveScoreResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a specific score by ID.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.scores.retrieve_score(
    id="id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.scores.<a href="src/respan/scores/client.py">delete_score</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete an evaluation score.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.scores.delete_score(
    id="id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.scores.<a href="src/respan/scores/client.py">update_score</a>(...) -> UpdateScoreResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update an existing score. Only provided fields are updated.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.scores.update_score(
    id="id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**numerical_value:** `typing.Optional[float]` — Numerical score value. Use when evaluator's `score_value_type` is `numerical`.
    
</dd>
</dl>

<dl>
<dd>

**string_value:** `typing.Optional[str]` — String/text score value. Use when `score_value_type` is `text` or `comment`.
    
</dd>
</dl>

<dl>
<dd>

**boolean_value:** `typing.Optional[bool]` — Boolean score value. Use when `score_value_type` is `boolean`.
    
</dd>
</dl>

<dl>
<dd>

**categorical_value:** `typing.Optional[typing.List[str]]` — Categorical score value. Use when `score_value_type` is `single_select`, `multi_select`, or `categorical`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.scores.<a href="src/respan/scores/client.py">list_span_scores</a>(...) -> ListSpanScoresResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all scores for a specific span. Scores are automatically enriched with evaluator names when retrieving span details.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.scores.list_span_scores(
    log_id="log_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**log_id:** `str` — Log Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.scores.<a href="src/respan/scores/client.py">log_scores_create_span_score</a>(...) -> LogScoresCreateSpanScoreResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a score for a specific span. Only one score per evaluator per span is allowed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.scores.log_scores_create_span_score(
    log_id="log_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**log_id:** `str` — Log Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**evaluator_id:** `typing.Optional[str]` — UUID of evaluator created in Respan. Either this or `evaluator_slug` must be provided.
    
</dd>
</dl>

<dl>
<dd>

**evaluator_slug:** `typing.Optional[str]` — Custom string identifier for your evaluator. Either this or `evaluator_id` must be provided.
    
</dd>
</dl>

<dl>
<dd>

**numerical_value:** `typing.Optional[float]` — Numerical score value. Use when evaluator's `score_value_type` is `numerical`.
    
</dd>
</dl>

<dl>
<dd>

**string_value:** `typing.Optional[str]` — String/text score value. Use when `score_value_type` is `text` or `comment`.
    
</dd>
</dl>

<dl>
<dd>

**boolean_value:** `typing.Optional[bool]` — Boolean score value. Use when `score_value_type` is `boolean`.
    
</dd>
</dl>

<dl>
<dd>

**categorical_value:** `typing.Optional[typing.List[str]]` — Categorical score value. Use when `score_value_type` is `single_select`, `multi_select`, or `categorical`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.scores.<a href="src/respan/scores/client.py">retrieve_span_score</a>(...) -> RetrieveSpanScoreResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a specific score for a span.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.scores.retrieve_span_score(
    log_id="log_id",
    score_id="score_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**log_id:** `str` — Log Id
    
</dd>
</dl>

<dl>
<dd>

**score_id:** `str` — Score Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.scores.<a href="src/respan/scores/client.py">delete_span_score</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a score from a span.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.scores.delete_span_score(
    log_id="log_id",
    score_id="score_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**log_id:** `str` — Log Id
    
</dd>
</dl>

<dl>
<dd>

**score_id:** `str` — Score Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.scores.<a href="src/respan/scores/client.py">update_span_score</a>(...) -> UpdateSpanScoreResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a score for a specific span. Only provided fields are updated.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.scores.update_span_score(
    log_id="log_id",
    score_id="score_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**log_id:** `str` — Log Id
    
</dd>
</dl>

<dl>
<dd>

**score_id:** `str` — Score Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**numerical_value:** `typing.Optional[float]` — Numerical score value. Use when evaluator's `score_value_type` is `numerical`.
    
</dd>
</dl>

<dl>
<dd>

**string_value:** `typing.Optional[str]` — String/text score value. Use when `score_value_type` is `text` or `comment`.
    
</dd>
</dl>

<dl>
<dd>

**boolean_value:** `typing.Optional[bool]` — Boolean score value. Use when `score_value_type` is `boolean`.
    
</dd>
</dl>

<dl>
<dd>

**categorical_value:** `typing.Optional[typing.List[str]]` — Categorical score value. Use when `score_value_type` is `single_select`, `multi_select`, or `categorical`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Models
<details><summary><code>client.models.<a href="src/respan/models/client.py">list_models</a>(...) -> typing.List[ListModelsResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all available models including pricing, context window, and provider info.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.list_models(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.models.<a href="src/respan/models/client.py">list_custom_models</a>(...) -> typing.List[ListCustomModelsResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all models accessible to your organization, including global models and custom models.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.list_custom_models(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**sort_by:** `typing.Optional[str]` — Field to sort by.
    
</dd>
</dl>

<dl>
<dd>

**all:** `typing.Optional[bool]` — If true, returns all models without pagination.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.models.<a href="src/respan/models/client.py">create_custom_model</a>(...) -> CreateCustomModelResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new custom model or update an existing one (upsert by `model_name`). Custom models allow organization-specific configurations with custom pricing, capabilities, and provider associations.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.create_custom_model(
    authorization="Bearer sk_live_xxxxx",
    model_name="my-custom-gpt-4",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**model_name:** `str` — Unique model name. Used to reference the model in API calls.
    
</dd>
</dl>

<dl>
<dd>

**base_model_name:** `typing.Optional[str]` — Base model to inherit properties from.
    
</dd>
</dl>

<dl>
<dd>

**display_name:** `typing.Optional[str]` — Human-readable display name.
    
</dd>
</dl>

<dl>
<dd>

**custom_provider_id:** `typing.Optional[str]` — ID of the custom provider to associate.
    
</dd>
</dl>

<dl>
<dd>

**provider_id:** `typing.Optional[str]` — Alternative to `custom_provider_id`.
    
</dd>
</dl>

<dl>
<dd>

**input_cost:** `typing.Optional[float]` — Cost per 1M input tokens (USD).
    
</dd>
</dl>

<dl>
<dd>

**output_cost:** `typing.Optional[float]` — Cost per 1M output tokens (USD).
    
</dd>
</dl>

<dl>
<dd>

**cache_hit_input_cost:** `typing.Optional[float]` — Cost per 1M cached input tokens (USD).
    
</dd>
</dl>

<dl>
<dd>

**cache_creation_input_cost:** `typing.Optional[float]` — Cost per 1M cache creation tokens (USD).
    
</dd>
</dl>

<dl>
<dd>

**max_context_window:** `typing.Optional[int]` — Maximum context window size.
    
</dd>
</dl>

<dl>
<dd>

**streaming_support:** `typing.Optional[int]` — Streaming support. `0` = no, `1` = yes.
    
</dd>
</dl>

<dl>
<dd>

**function_call:** `typing.Optional[int]` — Function calling support. `0` = no, `1` = yes.
    
</dd>
</dl>

<dl>
<dd>

**image_support:** `typing.Optional[int]` — Image/vision support. `0` = no, `1` = yes.
    
</dd>
</dl>

<dl>
<dd>

**supported_params_override:** `typing.Optional[typing.Dict[str, typing.Any]]` — Override UI parameter support for Playground.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.models.<a href="src/respan/models/client.py">retrieve_custom_model</a>(...) -> RetrieveCustomModelResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a model by name. Global models are accessible by anyone. Custom models are only accessible by the owning organization.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.retrieve_custom_model(
    model_name="model_name",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**model_name:** `str` — The model's unique name. Can include slashes (e.g., openai/gpt-4).
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.models.<a href="src/respan/models/client.py">delete_custom_model</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a custom model. Only custom models (`source: "db"`) can be deleted. This action is permanent.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.delete_custom_model(
    model_name="model_name",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**model_name:** `str` — The model's unique name to delete.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.models.<a href="src/respan/models/client.py">update_custom_model</a>(...) -> UpdateCustomModelResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a custom model. Only provided fields are updated. The `model_name` field is read-only. Only the owning organization can update their custom models.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.update_custom_model(
    model_name="model_name",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**model_name:** `str` — The model's unique name to update.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**display_name:** `typing.Optional[str]` — Display name.
    
</dd>
</dl>

<dl>
<dd>

**base_model_name:** `typing.Optional[str]` — Base model.
    
</dd>
</dl>

<dl>
<dd>

**custom_provider_id:** `typing.Optional[str]` — Custom provider ID.
    
</dd>
</dl>

<dl>
<dd>

**input_cost:** `typing.Optional[float]` — Cost per 1M input tokens (USD).
    
</dd>
</dl>

<dl>
<dd>

**output_cost:** `typing.Optional[float]` — Cost per 1M output tokens (USD).
    
</dd>
</dl>

<dl>
<dd>

**cache_hit_input_cost:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**cache_creation_input_cost:** `typing.Optional[float]` 
    
</dd>
</dl>

<dl>
<dd>

**max_context_window:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**streaming_support:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**function_call:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**image_support:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**supported_params_override:** `typing.Optional[typing.Dict[str, typing.Any]]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.models.<a href="src/respan/models/client.py">list_custom_providers</a>(...) -> typing.List[ListCustomProvidersResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all custom providers. The `api_key` and `extra_kwargs` fields are write-only and never returned for security.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.list_custom_providers(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.models.<a href="src/respan/models/client.py">create_custom_provider</a>(...) -> CreateCustomProviderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new custom provider or update an existing one (upsert by `provider_id`). The `api_key` and `extra_kwargs` fields are write-only and never returned for security.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.create_custom_provider(
    authorization="Bearer sk_live_xxxxx",
    provider_id="my-azure-provider",
    provider_name="My Azure Provider",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**provider_id:** `str` — Unique provider identifier.
    
</dd>
</dl>

<dl>
<dd>

**provider_name:** `str` — Human-readable provider name.
    
</dd>
</dl>

<dl>
<dd>

**api_key:** `typing.Optional[str]` — API key for the provider (write-only, never returned).
    
</dd>
</dl>

<dl>
<dd>

**extra_kwargs:** `typing.Optional[typing.Dict[str, typing.Any]]` — Additional provider config (write-only). Common fields: `base_url`, `timeout`, `temperature`, `max_tokens`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.models.<a href="src/respan/models/client.py">retrieve_custom_provider</a>(...) -> RetrieveCustomProviderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a custom provider by ID. Sensitive fields (`api_key`, `extra_kwargs`) are never returned. The `api_key` and `extra_kwargs` fields are write-only and never returned.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.retrieve_custom_provider(
    provider_id=1,
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**provider_id:** `int` — The provider's primary key ID (numeric database ID).
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.models.<a href="src/respan/models/client.py">delete_custom_provider</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a custom provider. Managed providers cannot be deleted. Deleting a provider may affect models that reference it. This action is permanent.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.delete_custom_provider(
    provider_id=1,
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**provider_id:** `int` — The provider's primary key ID to delete.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.models.<a href="src/respan/models/client.py">update_custom_provider</a>(...) -> UpdateCustomProviderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a custom provider. Only provided fields are updated. The `provider_id` is read-only. Managed providers cannot have critical fields modified.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.models.update_custom_provider(
    provider_id=1,
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**provider_id:** `int` — The provider's primary key ID to update.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**provider_name:** `typing.Optional[str]` — Provider name.
    
</dd>
</dl>

<dl>
<dd>

**api_key:** `typing.Optional[str]` — API key (write-only).
    
</dd>
</dl>

<dl>
<dd>

**extra_kwargs:** `typing.Optional[typing.Dict[str, typing.Any]]` — Additional config (write-only).
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Temporary API Keys
<details><summary><code>client.temporary_api_keys.<a href="src/respan/temporary_api_keys/client.py">list_api_keys</a>(...) -> typing.List[ListApiKeysResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all API keys for your organization.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.temporary_api_keys.list_api_keys(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.temporary_api_keys.<a href="src/respan/temporary_api_keys/client.py">create_api_key</a>(...) -> CreateApiKeyResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new API key.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.temporary_api_keys.create_api_key(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Key name.
    
</dd>
</dl>

<dl>
<dd>

**expiry_date:** `typing.Optional[datetime.datetime]` — Expiry date (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**max_usage:** `typing.Optional[int]` — Max usage count. -1 = unlimited.
    
</dd>
</dl>

<dl>
<dd>

**rate_limit:** `typing.Optional[int]` — Calls per minute. Overridden by plan limit.
    
</dd>
</dl>

<dl>
<dd>

**spending_limit:** `typing.Optional[float]` — Spending limit in USD for gateway usage.
    
</dd>
</dl>

<dl>
<dd>

**is_test:** `typing.Optional[bool]` — Test key (`true`) or production key (`false`).
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.temporary_api_keys.<a href="src/respan/temporary_api_keys/client.py">retrieve_api_key</a>(...) -> RetrieveApiKeyResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve an API key by ID.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.temporary_api_keys.retrieve_api_key(
    id="id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The ID of the temporary API key to retrieve.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.temporary_api_keys.<a href="src/respan/temporary_api_keys/client.py">delete_api_key</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete an API key. This action is irreversible.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.temporary_api_keys.delete_api_key(
    id="id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The ID of the temporary API key to delete.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.temporary_api_keys.<a href="src/respan/temporary_api_keys/client.py">update_api_key</a>(...) -> UpdateApiKeyResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update an API key's name, expiry, or test status.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.temporary_api_keys.update_api_key(
    id="id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The ID of the temporary API key to update.
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Key name.
    
</dd>
</dl>

<dl>
<dd>

**expiry_date:** `typing.Optional[datetime.datetime]` — Expiry date (ISO 8601).
    
</dd>
</dl>

<dl>
<dd>

**is_test:** `typing.Optional[bool]` — Test or production key.
    
</dd>
</dl>

<dl>
<dd>

**prefix:** `typing.Optional[str]` — Key prefix.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Credit Transactions
<details><summary><code>client.credit_transactions.<a href="src/respan/credit_transactions/client.py">credit_transactions_list</a>(...) -> CreditTransactionsListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List credit transactions with pagination.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.credit_transactions.credit_transactions_list(
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number for pagination.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Number of items per page. Maximum is 1000.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.credit_transactions.<a href="src/respan/credit_transactions/client.py">credit_transactions_retrieve</a>(...) -> CreditTransactionsRetrieveResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve details of a specific credit transaction.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.credit_transactions.credit_transactions_retrieve(
    id="id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — The unique identifier of the transaction to retrieve (e.g., ct_1a2b3c4d5e6f7g8h)
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Automations
<details><summary><code>client.automations.<a href="src/respan/automations/client.py">list_conditions</a>(...) -> ListConditionsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List automation conditions with pagination and filtering.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.automations.list_conditions(
    condition_type="single_log",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Results per page.
    
</dd>
</dl>

<dl>
<dd>

**search:** `typing.Optional[str]` — Search conditions by name or slug.
    
</dd>
</dl>

<dl>
<dd>

**condition_type:** `typing.Optional[str]` — Filter by condition type.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.automations.<a href="src/respan/automations/client.py">create_condition</a>(...) -> CreateConditionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create an automation condition that defines which spans should trigger evaluations.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment
from respan.automations import CreateConditionRequestConditionPolicy, CreateConditionRequestConditionPolicyRulesItem

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.automations.create_condition(
    authorization="Bearer sk_live_xxxxx",
    name="Successful Requests",
    condition_slug="success_logs",
    condition_type="single_log",
    condition_policy=CreateConditionRequestConditionPolicy(
        rules=[
            CreateConditionRequestConditionPolicyRulesItem(
                field="status_code",
                operator="equals",
                value=200,
            )
        ],
        connector="AND",
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Display name.
    
</dd>
</dl>

<dl>
<dd>

**condition_slug:** `str` — Unique identifier.
    
</dd>
</dl>

<dl>
<dd>

**condition_type:** `CreateConditionRequestConditionType` — Condition type.
    
</dd>
</dl>

<dl>
<dd>

**condition_policy:** `CreateConditionRequestConditionPolicy` — Policy defining evaluation rules.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Condition description.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.automations.<a href="src/respan/automations/client.py">create_automation</a>(...) -> CreateAutomationResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create an online evaluation automation that automatically runs evaluators on spans matching specified conditions.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment
from respan.automations import CreateAutomationRequestConfiguration

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.automations.create_automation(
    authorization="Bearer sk_live_xxxxx",
    automation_slug="prod_quality_monitor",
    name="Production Quality Monitor",
    automation_type="online_eval",
    condition="cond-12345",
    evaluator_ids=[
        "eval-quality-uuid",
        "eval-safety-uuid"
    ],
    configuration=CreateAutomationRequestConfiguration(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**automation_slug:** `str` — Unique identifier.
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Human-readable name.
    
</dd>
</dl>

<dl>
<dd>

**automation_type:** `CreateAutomationRequestAutomationType` — Automation type.
    
</dd>
</dl>

<dl>
<dd>

**condition:** `str` — Condition ID (from Create Condition endpoint).
    
</dd>
</dl>

<dl>
<dd>

**evaluator_ids:** `typing.List[str]` — Evaluator UUIDs to run (from List Evaluators).
    
</dd>
</dl>

<dl>
<dd>

**configuration:** `CreateAutomationRequestConfiguration` — Automation configuration.
    
</dd>
</dl>

<dl>
<dd>

**is_enabled:** `typing.Optional[bool]` — Whether automation is active.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.automations.<a href="src/respan/automations/client.py">update_automation</a>(...) -> UpdateAutomationResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update an automation. Use to enable/disable, change sampling rate, or update evaluator list. Only provided fields are updated.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from respan import RespanClient
from respan.environment import RespanClientEnvironment

client = RespanClient(
    environment=RespanClientEnvironment.DEFAULT,
)

client.automations.update_automation(
    automation_id="automation_id",
    authorization="Bearer sk_live_xxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**automation_id:** `str` — Automation Id
    
</dd>
</dl>

<dl>
<dd>

**authorization:** `str` — Bearer token. Use `Bearer YOUR_API_KEY`.
    
</dd>
</dl>

<dl>
<dd>

**is_enabled:** `typing.Optional[bool]` — Enable or disable the automation.
    
</dd>
</dl>

<dl>
<dd>

**configuration:** `typing.Optional[UpdateAutomationRequestConfiguration]` 
    
</dd>
</dl>

<dl>
<dd>

**evaluator_ids:** `typing.Optional[typing.List[str]]` — Updated evaluator UUIDs.
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Automation name.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

