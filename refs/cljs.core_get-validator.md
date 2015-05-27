## <img width="48px" valign="middle" src="http://i.imgur.com/Hi20huC.png"> cljs.core/get-validator

 <table border="1">
<tr>
<td>function</td>
<td><a href="https://github.com/cljsinfo/api-refs/tree/0.0-927"><img valign="middle" alt="[+] 0.0-927" src="https://img.shields.io/badge/+-0.0--927-lightgrey.svg"></a> </td>
<td>
[<img height="24px" valign="middle" src="http://i.imgur.com/1GjPKvB.png"> <samp>clojure.core/get-validator</samp>](http://clojure.github.io/clojure/branch-master/clojure.core-api.html#clojure.core/get-validator)
</td>
</tr>
</table>

 <samp>
(__get-validator__ iref)<br>
</samp>

```
Gets the validator-fn for a var/ref/agent/atom.
```

---

 <pre>
clojurescript @ r1803
└── src
    └── cljs
        └── cljs
            └── <ins>[core.cljs:6619-6622](https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L6619-L6622)</ins>
</pre>

```clj
(defn get-validator
  [iref]
  (.-validator iref))
```


---

```clj
{:ns "cljs.core",
 :name "get-validator",
 :signature ["[iref]"],
 :history [["+" "0.0-927"]],
 :type "function",
 :full-name-encode "cljs.core_get-validator",
 :source {:code "(defn get-validator\n  [iref]\n  (.-validator iref))",
          :filename "clojurescript/src/cljs/cljs/core.cljs",
          :lines [6619 6622],
          :link "https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L6619-L6622"},
 :full-name "cljs.core/get-validator",
 :clj-symbol "clojure.core/get-validator",
 :docstring "Gets the validator-fn for a var/ref/agent/atom."}

```