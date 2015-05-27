## <img width="48px" valign="middle" src="http://i.imgur.com/Hi20huC.png"> cljs.core/aget

 <table border="1">
<tr>
<td>function</td>
<td><a href="https://github.com/cljsinfo/api-refs/tree/0.0-927"><img valign="middle" alt="[+] 0.0-927" src="https://img.shields.io/badge/+-0.0--927-lightgrey.svg"></a> </td>
<td>
[<img height="24px" valign="middle" src="http://i.imgur.com/1GjPKvB.png"> <samp>clojure.core/aget</samp>](http://clojure.github.io/clojure/branch-master/clojure.core-api.html#clojure.core/aget)
</td>
</tr>
</table>

 <samp>
(__aget__ array i)<br>
(__aget__ array i & idxs)<br>
</samp>

```
Returns the value at the index.
```

---

 <pre>
clojurescript @ r1803
└── src
    └── cljs
        └── cljs
            └── <ins>[core.cljs:128-133](https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L128-L133)</ins>
</pre>

```clj
(defn aget
  ([array i]
     (cljs.core/aget array i))
  ([array i & idxs]
     (apply aget (aget array i) idxs)))
```


---

 <pre>
clojurescript @ r1803
└── src
    └── clj
        └── cljs
            └── <ins>[core.clj:254-259](https://github.com/clojure/clojurescript/blob/r1803/src/clj/cljs/core.clj#L254-L259)</ins>
</pre>

```clj
(defmacro aget
  ([a i]
     (list 'js* "(~{}[~{}])" a i))
  ([a i & idxs]
     (let [astr (apply core/str (repeat (count idxs) "[~{}]"))]
      `(~'js* ~(core/str "(~{}[~{}]" astr ")") ~a ~i ~@idxs))))
```

---

```clj
{:ns "cljs.core",
 :name "aget",
 :signature ["[array i]" "[array i & idxs]"],
 :shadowed-sources ({:code "(defmacro aget\n  ([a i]\n     (list 'js* \"(~{}[~{}])\" a i))\n  ([a i & idxs]\n     (let [astr (apply core/str (repeat (count idxs) \"[~{}]\"))]\n      `(~'js* ~(core/str \"(~{}[~{}]\" astr \")\") ~a ~i ~@idxs))))",
                     :filename "clojurescript/src/clj/cljs/core.clj",
                     :lines [254 259],
                     :link "https://github.com/clojure/clojurescript/blob/r1803/src/clj/cljs/core.clj#L254-L259"}),
 :history [["+" "0.0-927"]],
 :type "function",
 :full-name-encode "cljs.core_aget",
 :source {:code "(defn aget\n  ([array i]\n     (cljs.core/aget array i))\n  ([array i & idxs]\n     (apply aget (aget array i) idxs)))",
          :filename "clojurescript/src/cljs/cljs/core.cljs",
          :lines [128 133],
          :link "https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L128-L133"},
 :full-name "cljs.core/aget",
 :clj-symbol "clojure.core/aget",
 :docstring "Returns the value at the index."}

```