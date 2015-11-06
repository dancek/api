## cljs.core/type->str



 <table border="1">
<tr>
<td>function</td>
<td><a href="https://github.com/cljsinfo/cljs-api-docs/tree/0.0-1859"><img valign="middle" alt="[+] 0.0-1859" title="Added in 0.0-1859" src="https://img.shields.io/badge/+-0.0--1859-lightgrey.svg"></a> </td>
</tr>
</table>


 <samp>
(__type->str__ ty)<br>
</samp>

---







Source code @ [github](https://github.com/clojure/clojurescript/blob/r1933/src/cljs/cljs/core.cljs#L118-L121):

```clj
(defn type->str [ty]
  (if-let [s (.-cljs$lang$ctorStr ty)]
    s
    (str ty)))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r1933
└── src
    └── cljs
        └── cljs
            └── <ins>[core.cljs:118-121](https://github.com/clojure/clojurescript/blob/r1933/src/cljs/cljs/core.cljs#L118-L121)</ins>
</pre>

-->

---



###### External doc links:

[`cljs.core/type->str` @ crossclj](http://crossclj.info/fun/cljs.core.cljs/type-%3Estr.html)<br>

---

 <table>
<tr><td>
<img valign="middle" align="right" width="48px" src="http://i.imgur.com/Hi20huC.png">
</td><td>
Created for the upcoming ClojureScript website.<br>
[edit here] | [learn how]
</td></tr></table>

[edit here]:https://github.com/cljsinfo/cljs-api-docs/blob/master/cljsdoc/cljs.core/type-GTstr.cljsdoc
[learn how]:https://github.com/cljsinfo/cljs-api-docs/wiki/cljsdoc-files

<!--

This information was too distracting to show to readers, but I'll leave it
commented here since it is helpful to:

- pretty-print the data used to generate this document
- and show how to retrieve that data



The API data for this symbol:

```clj
{:ns "cljs.core",
 :name "type->str",
 :type "function",
 :signature ["[ty]"],
 :source {:code "(defn type->str [ty]\n  (if-let [s (.-cljs$lang$ctorStr ty)]\n    s\n    (str ty)))",
          :title "Source code",
          :repo "clojurescript",
          :tag "r1933",
          :filename "src/cljs/cljs/core.cljs",
          :lines [118 121]},
 :full-name "cljs.core/type->str",
 :full-name-encode "cljs.core/type-GTstr",
 :history [["+" "0.0-1859"]]}

```

Retrieve the API data for this symbol:

```clj
;; from Clojure REPL
(require '[clojure.edn :as edn])
(-> (slurp "https://raw.githubusercontent.com/cljsinfo/cljs-api-docs/catalog/cljs-api.edn")
    (edn/read-string)
    (get-in [:symbols "cljs.core/type->str"]))
```

-->