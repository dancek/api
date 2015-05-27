## <img width="48px" valign="middle" src="http://i.imgur.com/Hi20huC.png"> cljs.core/regexp?

 <table border="1">
<tr>
<td>function</td>
<td><a href="https://github.com/cljsinfo/api-refs/tree/0.0-1424"><img valign="middle" alt="[+] 0.0-1424" src="https://img.shields.io/badge/+-0.0--1424-lightgrey.svg"></a> </td>
</tr>
</table>

 <samp>
(__regexp?__ o)<br>
</samp>

```
(no docstring)
```

---

 <pre>
clojurescript @ r1803
└── src
    └── cljs
        └── cljs
            └── <ins>[core.cljs:6172-6173](https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L6172-L6173)</ins>
</pre>

```clj
(defn regexp? [o]
  (instance? js/RegExp o))
```


---

```clj
{:full-name "cljs.core/regexp?",
 :ns "cljs.core",
 :name "regexp?",
 :type "function",
 :signature ["[o]"],
 :source {:code "(defn regexp? [o]\n  (instance? js/RegExp o))",
          :filename "clojurescript/src/cljs/cljs/core.cljs",
          :lines [6172 6173],
          :link "https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L6172-L6173"},
 :full-name-encode "cljs.core_regexp_QMARK_",
 :history [["+" "0.0-1424"]]}

```