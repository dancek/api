## Name
cljs.core/fnext

## Signature
[coll]

## Description

Same as `(first (next coll))`

## Related
cljs.core/ffirst
cljs.core/second

## Examples

```clj
(fnext [1 2 3])
;;=> 2

(fnext [1 2])
;;=> 2

(fnext [1])
;;=> nil

(fnext [])
;;=> nil
```