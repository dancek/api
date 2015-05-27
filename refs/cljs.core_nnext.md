## <img width="48px" valign="middle" src="http://i.imgur.com/Hi20huC.png"> cljs.core/nnext

 <table border="1">
<tr>
<td>function</td>
<td><a href="https://github.com/cljsinfo/api-refs/tree/0.0-927"><img valign="middle" alt="[+] 0.0-927" src="https://img.shields.io/badge/+-0.0--927-lightgrey.svg"></a> </td>
<td>
[<img height="24px" valign="middle" src="http://i.imgur.com/1GjPKvB.png"> <samp>clojure.core/nnext</samp>](http://clojure.github.io/clojure/branch-master/clojure.core-api.html#clojure.core/nnext)
</td>
</tr>
</table>

 <samp>
(__nnext__ coll)<br>
</samp>

```
Same as (next (next x))
```

---

 <pre>
clojurescript @ r1803
└── src
    └── cljs
        └── cljs
            └── <ins>[core.cljs:751-754](https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L751-L754)</ins>
</pre>

```clj
(defn nnext
  [coll]
  (next (next coll)))
```


---

```clj
{:ns "cljs.core",
 :name "nnext",
 :signature ["[coll]"],
 :history [["+" "0.0-927"]],
 :type "function",
 :full-name-encode "cljs.core_nnext",
 :source {:code "(defn nnext\n  [coll]\n  (next (next coll)))",
          :filename "clojurescript/src/cljs/cljs/core.cljs",
          :lines [751 754],
          :link "https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L751-L754"},
 :full-name "cljs.core/nnext",
 :clj-symbol "clojure.core/nnext",
 :docstring "Same as (next (next x))"}

```