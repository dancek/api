## def

_known as "define"_


 <table border="1">
<tr>
<td>special form</td>
<td><a href="https://github.com/cljsinfo/cljs-api-docs/tree/0.0-927"><img valign="middle" alt="[+] 0.0-927" title="Added in 0.0-927" src="https://img.shields.io/badge/+-0.0--927-lightgrey.svg"></a> </td>
<td>
[<img height="24px" valign="middle" src="http://i.imgur.com/1GjPKvB.png"> <samp>clojure.core/def</samp>](http://clojure.github.io/clojure/branch-master/clojure.core-api.html#clojure.core/def)
</td>
</tr>
</table>


 <samp>
(__def__ symbol)<br>
</samp>
 <samp>
(__def__ symbol init)<br>
</samp>
 <samp>
(__def__ symbol doc-string init)<br>
</samp>

---

Creates a global variable with the name of `symbol` and a namespace of the
current namespace.

If `init` is supplied, it is evaluated and the result is assigned to `symbol`.

`doc-string` is an optional documentation string.

`def` is one of ClojureScript's [special forms](http://clojure.org/special_forms)
and is used by many macros to define common elements (ie: `defn`, `defmacro`,
etc).

Supported metadata:

- `^:private boolean` - make non-accessible from other namespaces
- `^:dynamic boolean` - make [dynamically bindable][doc:cljs.core/binding] (usually named with [`earmuffs`][doc:syntax/earmuffs])
- `^:const boolean` - prevents redef and allows it to be used in [doc:cljs.core/case].
- `^:jsdoc [""]` - vector of JSDoc Tags for [Google Closure][closure-jsdoc] or [standard][other-jsdoc].
- `^:test (fn [] (assert ...))` - allows function to be tested with [doc:cljs.core/test].
- `^:doc ""` - doc-string (prefer the use of the `(def symbol doc-string init)`)

[closure-jsdoc]:https://developers.google.com/closure/compiler/docs/js-for-compiler?hl=en#tags
[other-jsdoc]:http://usejsdoc.org/#block-tags

Compiler will also add metadata:

- `:ns`
- `:name`
- `:file`
- `:line`, `:end-line`
- `:column`, `:end-column`
- `:source`
- `:arglists`

[doc:cljs.core/binding]:../cljs.core/binding.md
[doc:syntax/earmuffs]:../syntax/earmuffs.md

---

###### Examples:

```clj
(def a)
a
;;=> nil

(def b 42)
b
;;=> 42

(def c "an optional docstring" 42)
c
;;=> 42
```



---

###### See Also:

[`cljs.core/defn`](../cljs.core/defn.md)<br>
[`cljs.core/fn`](../cljs.core/fn.md)<br>
[`cljs.core/defmacro`](../cljs.core/defmacro.md)<br>
[`cljs.core/defmulti`](../cljs.core/defmulti.md)<br>

---




Parser code @ [github](https://github.com/clojure/clojurescript/blob/r971/src/clj/cljs/compiler.clj#L654-L679):

```clj
(defmethod parse 'def
  [op env form name]
  (let [pfn (fn ([_ sym] {:sym sym})
              ([_ sym init] {:sym sym :init init})
              ([_ sym doc init] {:sym sym :doc doc :init init}))
        args (apply pfn form)
        sym (:sym args)]
    (assert (not (namespace sym)) "Can't def ns-qualified name")
    (let [name (munge (:name (resolve-var (dissoc env :locals) sym)))
          init-expr (when (contains? args :init) (disallowing-recur
                                                  (analyze (assoc env :context :expr) (:init args) sym)))
          export-as (when-let [export-val (-> sym meta :export)]
                      (if (= true export-val) name export-val))
          doc (or (:doc args) (-> sym meta :doc))]
      (swap! namespaces update-in [(-> env :ns :name) :defs sym]
             (fn [m]
               (let [m (assoc (or m {}) :name name)]
                 (if-let [line (:line env)]
                   (-> m
                       (assoc :file *cljs-file*)
                       (assoc :line line))
                   m))))
      (merge {:env env :op :def :form form
              :name name :doc doc :init init-expr}
             (when init-expr {:children [init-expr]})
             (when export-as {:export export-as})))))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r971
└── src
    └── clj
        └── cljs
            └── <ins>[compiler.clj:654-679](https://github.com/clojure/clojurescript/blob/r971/src/clj/cljs/compiler.clj#L654-L679)</ins>
</pre>

-->

---



###### External doc links:

[`clojure.core/def` @ clojuredocs](http://clojuredocs.org/clojure.core/def)<br>
[`clojure.core/def` @ grimoire](http://conj.io/store/v1/org.clojure/clojure/1.7.0-beta3/clj/clojure.core/def/)<br>
[`clojure.core/def` @ crossclj](http://crossclj.info/fun/clojure.core/def.html)<br>

---

 <table>
<tr><td>
<img valign="middle" align="right" width="48px" src="http://i.imgur.com/Hi20huC.png">
</td><td>
Created for the upcoming ClojureScript website.<br>
[edit here] | [learn how]
</td></tr></table>

[edit here]:https://github.com/cljsinfo/cljs-api-docs/blob/master/cljsdoc/special/def.cljsdoc
[learn how]:https://github.com/cljsinfo/cljs-api-docs/wiki/cljsdoc-files

<!--

This information was too distracting to show to readers, but I'll leave it
commented here since it is helpful to:

- pretty-print the data used to generate this document
- and show how to retrieve that data



The API data for this symbol:

```clj
{:description "Creates a global variable with the name of `symbol` and a namespace of the\ncurrent namespace.\n\nIf `init` is supplied, it is evaluated and the result is assigned to `symbol`.\n\n`doc-string` is an optional documentation string.\n\n`def` is one of ClojureScript's [special forms](http://clojure.org/special_forms)\nand is used by many macros to define common elements (ie: `defn`, `defmacro`,\netc).\n\nSupported metadata:\n\n- `^:private boolean` - make non-accessible from other namespaces\n- `^:dynamic boolean` - make [dynamically bindable][doc:cljs.core/binding] (usually named with [doc:syntax/earmuffs])\n- `^:const boolean` - prevents redef and allows it to be used in [doc:cljs.core/case].\n- `^:jsdoc [\"\"]` - vector of JSDoc Tags for [Google Closure][closure-jsdoc] or [standard][other-jsdoc].\n- `^:test (fn [] (assert ...))` - allows function to be tested with [doc:cljs.core/test].\n- `^:doc \"\"` - doc-string (prefer the use of the `(def symbol doc-string init)`)\n\n[closure-jsdoc]:https://developers.google.com/closure/compiler/docs/js-for-compiler?hl=en#tags\n[other-jsdoc]:http://usejsdoc.org/#block-tags\n\nCompiler will also add metadata:\n\n- `:ns`\n- `:name`\n- `:file`\n- `:line`, `:end-line`\n- `:column`, `:end-column`\n- `:source`\n- `:arglists`",
 :ns "special",
 :name "def",
 :signature ["[symbol]" "[symbol init]" "[symbol doc-string init]"],
 :history [["+" "0.0-927"]],
 :type "special form",
 :related ["cljs.core/defn"
           "cljs.core/fn"
           "cljs.core/defmacro"
           "cljs.core/defmulti"],
 :full-name-encode "special/def",
 :source {:code "(defmethod parse 'def\n  [op env form name]\n  (let [pfn (fn ([_ sym] {:sym sym})\n              ([_ sym init] {:sym sym :init init})\n              ([_ sym doc init] {:sym sym :doc doc :init init}))\n        args (apply pfn form)\n        sym (:sym args)]\n    (assert (not (namespace sym)) \"Can't def ns-qualified name\")\n    (let [name (munge (:name (resolve-var (dissoc env :locals) sym)))\n          init-expr (when (contains? args :init) (disallowing-recur\n                                                  (analyze (assoc env :context :expr) (:init args) sym)))\n          export-as (when-let [export-val (-> sym meta :export)]\n                      (if (= true export-val) name export-val))\n          doc (or (:doc args) (-> sym meta :doc))]\n      (swap! namespaces update-in [(-> env :ns :name) :defs sym]\n             (fn [m]\n               (let [m (assoc (or m {}) :name name)]\n                 (if-let [line (:line env)]\n                   (-> m\n                       (assoc :file *cljs-file*)\n                       (assoc :line line))\n                   m))))\n      (merge {:env env :op :def :form form\n              :name name :doc doc :init init-expr}\n             (when init-expr {:children [init-expr]})\n             (when export-as {:export export-as})))))",
          :title "Parser code",
          :repo "clojurescript",
          :tag "r971",
          :filename "src/clj/cljs/compiler.clj",
          :lines [654 679]},
 :examples [{:id "a5f898",
             :content "```clj\n(def a)\na\n;;=> nil\n\n(def b 42)\nb\n;;=> 42\n\n(def c \"an optional docstring\" 42)\nc\n;;=> 42\n```"}],
 :known-as "define",
 :full-name "special/def",
 :clj-symbol "clojure.core/def"}

```

Retrieve the API data for this symbol:

```clj
;; from Clojure REPL
(require '[clojure.edn :as edn])
(-> (slurp "https://raw.githubusercontent.com/cljsinfo/cljs-api-docs/catalog/cljs-api.edn")
    (edn/read-string)
    (get-in [:symbols "special/def"]))
```

-->