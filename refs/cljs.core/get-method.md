## cljs.core/get-method



 <table border="1">
<tr>
<td>function</td>
<td><a href="https://github.com/cljsinfo/cljs-api-docs/tree/0.0-927"><img valign="middle" alt="[+] 0.0-927" title="Added in 0.0-927" src="https://img.shields.io/badge/+-0.0--927-lightgrey.svg"></a> </td>
<td>
[<img height="24px" valign="middle" src="http://i.imgur.com/1GjPKvB.png"> <samp>clojure.core/get-method</samp>](http://clojure.github.io/clojure/branch-master/clojure.core-api.html#clojure.core/get-method)
</td>
</tr>
</table>


 <samp>
(__get-method__ multifn dispatch-val)<br>
</samp>

---





Source docstring:

```
Given a multimethod and a dispatch value, returns the dispatch fn
that would apply to that value, or nil if none apply and no default
```


Source code @ [github](https://github.com/clojure/clojurescript/blob/r971/src/cljs/cljs/core.cljs#L3546-L3549):

```clj
(defn get-method
  [multifn dispatch-val] (-get-method multifn dispatch-val))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r971
└── src
    └── cljs
        └── cljs
            └── <ins>[core.cljs:3546-3549](https://github.com/clojure/clojurescript/blob/r971/src/cljs/cljs/core.cljs#L3546-L3549)</ins>
</pre>

-->

---



###### External doc links:

[`clojure.core/get-method` @ clojuredocs](http://clojuredocs.org/clojure.core/get-method)<br>
[`clojure.core/get-method` @ grimoire](http://conj.io/store/v1/org.clojure/clojure/1.7.0-beta3/clj/clojure.core/get-method/)<br>
[`clojure.core/get-method` @ crossclj](http://crossclj.info/fun/clojure.core/get-method.html)<br>
[`cljs.core/get-method` @ crossclj](http://crossclj.info/fun/cljs.core.cljs/get-method.html)<br>

---

 <table>
<tr><td>
<img valign="middle" align="right" width="48px" src="http://i.imgur.com/Hi20huC.png">
</td><td>
Created for the upcoming ClojureScript website.<br>
[edit here] | [learn how]
</td></tr></table>

[edit here]:https://github.com/cljsinfo/cljs-api-docs/blob/master/cljsdoc/cljs.core/get-method.cljsdoc
[learn how]:https://github.com/cljsinfo/cljs-api-docs/wiki/cljsdoc-files

<!--

This information was too distracting to show to readers, but I'll leave it
commented here since it is helpful to:

- pretty-print the data used to generate this document
- and show how to retrieve that data



The API data for this symbol:

```clj
{:ns "cljs.core",
 :name "get-method",
 :signature ["[multifn dispatch-val]"],
 :history [["+" "0.0-927"]],
 :type "function",
 :full-name-encode "cljs.core/get-method",
 :source {:code "(defn get-method\n  [multifn dispatch-val] (-get-method multifn dispatch-val))",
          :title "Source code",
          :repo "clojurescript",
          :tag "r971",
          :filename "src/cljs/cljs/core.cljs",
          :lines [3546 3549]},
 :full-name "cljs.core/get-method",
 :clj-symbol "clojure.core/get-method",
 :docstring "Given a multimethod and a dispatch value, returns the dispatch fn\nthat would apply to that value, or nil if none apply and no default"}

```

Retrieve the API data for this symbol:

```clj
;; from Clojure REPL
(require '[clojure.edn :as edn])
(-> (slurp "https://raw.githubusercontent.com/cljsinfo/cljs-api-docs/catalog/cljs-api.edn")
    (edn/read-string)
    (get-in [:symbols "cljs.core/get-method"]))
```

-->