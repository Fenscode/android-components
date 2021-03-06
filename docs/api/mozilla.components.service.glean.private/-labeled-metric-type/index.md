[android-components](../../index.md) / [mozilla.components.service.glean.private](../index.md) / [LabeledMetricType](./index.md)

# LabeledMetricType

`data class LabeledMetricType<T> : `[`CommonMetricData`](../-common-metric-data/index.md) [(source)](https://github.com/mozilla-mobile/android-components/blob/master/components/service/glean/src/main/java/mozilla/components/service/glean/private/LabeledMetricType.kt#L25)

This implements the developer facing API for labeled metrics.

Instances of this class type are automatically generated by the parsers at build time,
allowing developers to record values that were previously registered in the metrics.yaml file.

Unlike most metric types, LabeledMetricType does not have its own corresponding storage engine,
but records metrics for the underlying metric type T in the storage engine for that type.  The
only difference is that labeled metrics are stored with the special key `$category.$name/$label`.
The |StorageEngineManager.collect| method knows how to pull these special values back out of the
individual storage engines and rearrange them correctly in the ping.

### Constructors

| Name | Summary |
|---|---|
| [&lt;init&gt;](-init-.md) | `LabeledMetricType(disabled: `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html)`, category: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`, lifetime: `[`Lifetime`](../-lifetime/index.md)`, name: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`, sendInPings: `[`List`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-list/index.html)`<`[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`>, subMetric: `[`T`](index.md#T)`, labels: `[`Set`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-set/index.html)`<`[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`>? = null)`<br>This implements the developer facing API for labeled metrics. |

### Properties

| Name | Summary |
|---|---|
| [category](category.md) | `val category: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html) |
| [defaultStorageDestinations](default-storage-destinations.md) | `val defaultStorageDestinations: `[`List`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-list/index.html)`<`[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`>`<br>Defines the names of the storages the metric defaults to when "default" is used as the destination storage. Note that every metric type will need to override this. |
| [disabled](disabled.md) | `val disabled: `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [labels](labels.md) | `val labels: `[`Set`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-set/index.html)`<`[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`>?` |
| [lifetime](lifetime.md) | `val lifetime: `[`Lifetime`](../-lifetime/index.md) |
| [name](name.md) | `val name: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html) |
| [sendInPings](send-in-pings.md) | `val sendInPings: `[`List`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-list/index.html)`<`[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`>` |
| [subMetric](sub-metric.md) | `val subMetric: `[`T`](index.md#T) |

### Inherited Properties

| Name | Summary |
|---|---|
| [identifier](../-common-metric-data/identifier.md) | `open val identifier: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html) |

### Functions

| Name | Summary |
|---|---|
| [get](get.md) | `operator fun get(label: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`): `[`T`](index.md#T)<br>Get the specific metric for a given label. |

### Inherited Functions

| Name | Summary |
|---|---|
| [getStorageNames](../-common-metric-data/get-storage-names.md) | `open fun getStorageNames(): `[`List`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-list/index.html)`<`[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`>`<br>Get the list of storage names the metric will record to. This automatically expands [DEFAULT_STORAGE_NAME](#) to the list of default storages for the metric. |
| [shouldRecord](../-common-metric-data/should-record.md) | `open fun shouldRecord(logger: `[`Logger`](../../mozilla.components.support.base.log.logger/-logger/index.md)`): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
