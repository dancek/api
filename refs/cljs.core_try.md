## <img width="48px" valign="middle" src="http://i.imgur.com/Hi20huC.png"> cljs.core/try

 <table border="1">
<tr>
<td>macro</td>
<td><a href="https://github.com/cljsinfo/api-refs/tree/0.0-927"><img valign="middle" alt="[+] 0.0-927" src="https://img.shields.io/badge/+-0.0--927-lightgrey.svg"></a> </td>
<td>
[<img height="24px" valign="middle" src="http://i.imgur.com/1GjPKvB.png"> <samp>clojure.core/try</samp>](http://clojure.github.io/clojure/branch-master/clojure.core-api.html#clojure.core/try)
</td>
</tr>
</table>

 <samp>
(__try__ & forms)<br>
</samp>

```
(try expr* catch-clause* finally-clause?)

 Special Form

 catch-clause => (catch protoname name expr*)
 finally-clause => (finally expr*)

Catches and handles JavaScript exceptions.
```

---

 <pre>
clojurescript @ r1803
└── src
    └── clj
        └── cljs
            └── <ins>[core.clj:963-991](https://github.com/clojure/clojurescript/blob/r1803/src/clj/cljs/core.clj#L963-L991)</ins>
</pre>

```clj
(defmacro try
  [& forms]
  (let [catch? #(and (seq? %) (= (first %) 'catch))
        [body catches] (split-with (complement catch?) forms)
        [catches fin] (split-with catch? catches)
        e (gensym "e")]
    (assert (every? #(clojure.core/> (count %) 2) catches) "catch block must specify a prototype and a name")
    (if (seq catches)
      `(~'try*
        ~@body
        (catch ~e
            (cond
             ~@(mapcat
                (fn [[_ type name & cb]]
                  `[(instance? ~type ~e) (let [~name ~e] ~@cb)])
                catches)
             :else (throw ~e)))
        ~@fin)
      `(~'try*
        ~@body
        ~@fin))))
```


---

```clj
{:ns "cljs.core",
 :name "try",
 :signature ["[& forms]"],
 :history [["+" "0.0-927"]],
 :type "macro",
 :full-name-encode "cljs.core_try",
 :source {:code "(defmacro try\n  [& forms]\n  (let [catch? #(and (seq? %) (= (first %) 'catch))\n        [body catches] (split-with (complement catch?) forms)\n        [catches fin] (split-with catch? catches)\n        e (gensym \"e\")]\n    (assert (every? #(clojure.core/> (count %) 2) catches) \"catch block must specify a prototype and a name\")\n    (if (seq catches)\n      `(~'try*\n        ~@body\n        (catch ~e\n            (cond\n             ~@(mapcat\n                (fn [[_ type name & cb]]\n                  `[(instance? ~type ~e) (let [~name ~e] ~@cb)])\n                catches)\n             :else (throw ~e)))\n        ~@fin)\n      `(~'try*\n        ~@body\n        ~@fin))))",
          :filename "clojurescript/src/clj/cljs/core.clj",
          :lines [963 991],
          :link "https://github.com/clojure/clojurescript/blob/r1803/src/clj/cljs/core.clj#L963-L991"},
 :full-name "cljs.core/try",
 :clj-symbol "clojure.core/try",
 :docstring "(try expr* catch-clause* finally-clause?)\n\n Special Form\n\n catch-clause => (catch protoname name expr*)\n finally-clause => (finally expr*)\n\nCatches and handles JavaScript exceptions."}

```