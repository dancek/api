## cljs.core/specify!



 <table border="1">
<tr>
<td>macro</td>
<td><a href="https://github.com/cljsinfo/cljs-api-docs/tree/0.0-2156"><img valign="middle" alt="[+] 0.0-2156" title="Added in 0.0-2156" src="https://img.shields.io/badge/+-0.0--2156-lightgrey.svg"></a> </td>
</tr>
</table>


 <samp>
(__specify!__ expr & impls)<br>
</samp>

---





Source docstring:

```
Identical to reify but mutates its first argument.
```


Source code @ [github](https://github.com/clojure/clojurescript/blob/r3291/src/main/clojure/cljs/core.clj#L736-L742):

```clj
(defmacro specify!
  [expr & impls]
  (let [x (with-meta (gensym "x") {:extend :instance})]
    `(let [~x ~expr]
       (extend-type ~x ~@impls)
       ~x)))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r3291
└── src
    └── main
        └── clojure
            └── cljs
                └── <ins>[core.clj:736-742](https://github.com/clojure/clojurescript/blob/r3291/src/main/clojure/cljs/core.clj#L736-L742)</ins>
</pre>

-->

---



###### External doc links:

[`cljs.core/specify!` @ crossclj](http://crossclj.info/fun/cljs.core/specify%21.html)<br>

---

 <table>
<tr><td>
<img valign="middle" align="right" width="48px" src="http://i.imgur.com/Hi20huC.png">
</td><td>
Created for the upcoming ClojureScript website.<br>
[edit here] | [learn how]
</td></tr></table>

[edit here]:https://github.com/cljsinfo/cljs-api-docs/blob/master/cljsdoc/cljs.core/specifyBANG.cljsdoc
[learn how]:https://github.com/cljsinfo/cljs-api-docs/wiki/cljsdoc-files

<!--

This information was too distracting to show to readers, but I'll leave it
commented here since it is helpful to:

- pretty-print the data used to generate this document
- and show how to retrieve that data



The API data for this symbol:

```clj
{:ns "cljs.core",
 :name "specify!",
 :signature ["[expr & impls]"],
 :history [["+" "0.0-2156"]],
 :type "macro",
 :full-name-encode "cljs.core/specifyBANG",
 :source {:code "(defmacro specify!\n  [expr & impls]\n  (let [x (with-meta (gensym \"x\") {:extend :instance})]\n    `(let [~x ~expr]\n       (extend-type ~x ~@impls)\n       ~x)))",
          :title "Source code",
          :repo "clojurescript",
          :tag "r3291",
          :filename "src/main/clojure/cljs/core.clj",
          :lines [736 742]},
 :full-name "cljs.core/specify!",
 :docstring "Identical to reify but mutates its first argument."}

```

Retrieve the API data for this symbol:

```clj
;; from Clojure REPL
(require '[clojure.edn :as edn])
(-> (slurp "https://raw.githubusercontent.com/cljsinfo/cljs-api-docs/catalog/cljs-api.edn")
    (edn/read-string)
    (get-in [:symbols "cljs.core/specify!"]))
```

-->