<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [kibana-plugin-core-public](./kibana-plugin-core-public.md) &gt; [ScopedHistory](./kibana-plugin-core-public.scopedhistory.md)

## ScopedHistory class

A wrapper around a `History` instance that is scoped to a particular base path of the history stack. Behaves similarly to the `basename` option except that this wrapper hides any history stack entries from outside the scope of this base path.

This wrapper also allows Core and Plugins to share a single underlying global `History` instance without exposing the history of other applications.

The [createSubHistory](./kibana-plugin-core-public.scopedhistory.createsubhistory.md) method is particularly useful for applications that contain any number of "sub-apps" which should not have access to the main application's history or basePath.

<b>Signature:</b>

```typescript
export declare class ScopedHistory<HistoryLocationState = unknown> implements History<HistoryLocationState> 
```

## Constructors

|  Constructor | Modifiers | Description |
|  --- | --- | --- |
|  [(constructor)(parentHistory, basePath)](./kibana-plugin-core-public.scopedhistory._constructor_.md) |  | Constructs a new instance of the <code>ScopedHistory</code> class |

## Properties

|  Property | Modifiers | Type | Description |
|  --- | --- | --- | --- |
|  [action](./kibana-plugin-core-public.scopedhistory.action.md) |  | <code>Action</code> | The last action dispatched on the history stack. |
|  [block](./kibana-plugin-core-public.scopedhistory.block.md) |  | <code>(prompt?: string &#124; boolean &#124; History.TransitionPromptHook&lt;HistoryLocationState&gt; &#124; undefined) =&gt; UnregisterCallback</code> | Not supported. Use [AppMountParameters.onAppLeave](./kibana-plugin-core-public.appmountparameters.onappleave.md)<!-- -->. |
|  [createHref](./kibana-plugin-core-public.scopedhistory.createhref.md) |  | <code>(location: LocationDescriptorObject&lt;HistoryLocationState&gt;, { prependBasePath }?: {</code><br/><code>        prependBasePath?: boolean &#124; undefined;</code><br/><code>    }) =&gt; string</code> | Creates an href (string) to the location. If <code>prependBasePath</code> is true (default), it will prepend the location's path with the scoped history basePath. |
|  [createSubHistory](./kibana-plugin-core-public.scopedhistory.createsubhistory.md) |  | <code>&lt;SubHistoryLocationState = unknown&gt;(basePath: string) =&gt; ScopedHistory&lt;SubHistoryLocationState&gt;</code> | Creates a <code>ScopedHistory</code> for a subpath of this <code>ScopedHistory</code>. Useful for applications that may have sub-apps that do not need access to the containing application's history. |
|  [go](./kibana-plugin-core-public.scopedhistory.go.md) |  | <code>(n: number) =&gt; void</code> | Send the user forward or backwards in the history stack. |
|  [goBack](./kibana-plugin-core-public.scopedhistory.goback.md) |  | <code>() =&gt; void</code> | Send the user one location back in the history stack. Equivalent to calling [ScopedHistory.go(-1)](./kibana-plugin-core-public.scopedhistory.go.md)<!-- -->. If no more entries are available backwards, this is a no-op. |
|  [goForward](./kibana-plugin-core-public.scopedhistory.goforward.md) |  | <code>() =&gt; void</code> | Send the user one location forward in the history stack. Equivalent to calling [ScopedHistory.go(1)](./kibana-plugin-core-public.scopedhistory.go.md)<!-- -->. If no more entries are available forwards, this is a no-op. |
|  [length](./kibana-plugin-core-public.scopedhistory.length.md) |  | <code>number</code> | The number of entries in the history stack, including all entries forwards and backwards from the current location. |
|  [listen](./kibana-plugin-core-public.scopedhistory.listen.md) |  | <code>(listener: (location: Location&lt;HistoryLocationState&gt;, action: Action) =&gt; void) =&gt; UnregisterCallback</code> | Adds a listener for location updates. |
|  [location](./kibana-plugin-core-public.scopedhistory.location.md) |  | <code>Location&lt;HistoryLocationState&gt;</code> | The current location of the history stack. |
|  [push](./kibana-plugin-core-public.scopedhistory.push.md) |  | <code>(pathOrLocation: string &#124; LocationDescriptorObject&lt;HistoryLocationState&gt;, state?: HistoryLocationState &#124; undefined) =&gt; void</code> | Pushes a new location onto the history stack. If there are forward entries in the stack, they will be removed. |
|  [replace](./kibana-plugin-core-public.scopedhistory.replace.md) |  | <code>(pathOrLocation: string &#124; LocationDescriptorObject&lt;HistoryLocationState&gt;, state?: HistoryLocationState &#124; undefined) =&gt; void</code> | Replaces the current location in the history stack. Does not remove forward or backward entries. |

