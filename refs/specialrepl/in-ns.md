## in-ns (repl)



 <table border="1">
<tr>
<td>special form (repl)</td>
<td><a href="https://github.com/cljsinfo/cljs-api-docs/tree/0.0-927"><img valign="middle" alt="[+] 0.0-927" title="Added in 0.0-927" src="https://img.shields.io/badge/+-0.0--927-lightgrey.svg"></a> </td>
<td>
[<img height="24px" valign="middle" src="http://i.imgur.com/1GjPKvB.png"> <samp>clojure.core/in-ns</samp>](http://clojure.github.io/clojure/branch-master/clojure.core-api.html#clojure.core/in-ns)
</td>
</tr>
</table>


 <samp>
(__in-ns__ name)<br>
</samp>

---

Only usable from a REPL.

Changes to the namespace `name`, creating it if needed.

Sets `*cljs-ns*` to the namespace `name`.



---

###### Examples:

```clj
(in-ns 'foo.core)
```



---





repl specials table @ [github](https://github.com/clojure/clojurescript/blob/r971/src/clj/cljs/repl.clj#L133-L162):

```clj
(defn repl
  "Note - repl will reload core.cljs every time, even if supplied old repl-env"
  [repl-env & {:keys [verbose warn-on-undeclared]}]
  (prn "Type: " :cljs/quit " to quit")
  (binding [comp/*cljs-ns* 'cljs.user
            *cljs-verbose* verbose
            comp/*cljs-warn-on-undeclared* warn-on-undeclared]
    (let [env {:context :statement :locals {}}]
      (-setup repl-env)
      (loop []
        (print (str "ClojureScript:" comp/*cljs-ns* "> "))
        (flush)
        (let [{:keys [status form]} (read-next-form)]
          (cond
           (= form :cljs/quit) :quit
           
           (= status :error) (recur)
           
           (and (seq? form) (= (first form) 'in-ns))
           (do (set! comp/*cljs-ns* (second (second form))) (newline) (recur))
           
           (and (seq? form) ('#{load-file clojure.core/load-file} (first form)))
           (do (load-file repl-env (second form)) (newline) (recur))
           
           (and (seq? form) ('#{load-namespace} (first form)))
           (do (load-namespace repl-env (second form)) (newline) (recur))
           
           :else
           (do (eval-and-print repl-env env form) (recur)))))
      (-tear-down repl-env))))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r971
└── src
    └── clj
        └── cljs
            └── <ins>[repl.clj:133-162](https://github.com/clojure/clojurescript/blob/r971/src/clj/cljs/repl.clj#L133-L162)</ins>
</pre>

-->

---



###### External doc links:

[`clojure.core/in-ns` @ clojuredocs](http://clojuredocs.org/clojure.core/in-ns)<br>
[`clojure.core/in-ns` @ grimoire](http://conj.io/store/v1/org.clojure/clojure/1.7.0-beta3/clj/clojure.core/in-ns/)<br>
[`clojure.core/in-ns` @ crossclj](http://crossclj.info/fun/clojure.core/in-ns.html)<br>

---

 <table>
<tr><td>
<img valign="middle" align="right" width="48px" src="http://i.imgur.com/Hi20huC.png">
</td><td>
Created for the upcoming ClojureScript website.<br>
[edit here] | [learn how]
</td></tr></table>

[edit here]:https://github.com/cljsinfo/cljs-api-docs/blob/master/cljsdoc/specialrepl/in-ns.cljsdoc
[learn how]:https://github.com/cljsinfo/cljs-api-docs/wiki/cljsdoc-files

<!--

This information was too distracting to show to readers, but I'll leave it
commented here since it is helpful to:

- pretty-print the data used to generate this document
- and show how to retrieve that data



The API data for this symbol:

```clj
{:description "Only usable from a REPL.\n\nChanges to the namespace `name`, creating it if needed.\n\nSets `*cljs-ns*` to the namespace `name`.",
 :ns "specialrepl",
 :name "in-ns",
 :signature ["[name]"],
 :history [["+" "0.0-927"]],
 :type "special form (repl)",
 :full-name-encode "specialrepl/in-ns",
 :source {:code "(defn repl\n  \"Note - repl will reload core.cljs every time, even if supplied old repl-env\"\n  [repl-env & {:keys [verbose warn-on-undeclared]}]\n  (prn \"Type: \" :cljs/quit \" to quit\")\n  (binding [comp/*cljs-ns* 'cljs.user\n            *cljs-verbose* verbose\n            comp/*cljs-warn-on-undeclared* warn-on-undeclared]\n    (let [env {:context :statement :locals {}}]\n      (-setup repl-env)\n      (loop []\n        (print (str \"ClojureScript:\" comp/*cljs-ns* \"> \"))\n        (flush)\n        (let [{:keys [status form]} (read-next-form)]\n          (cond\n           (= form :cljs/quit) :quit\n           \n           (= status :error) (recur)\n           \n           (and (seq? form) (= (first form) 'in-ns))\n           (do (set! comp/*cljs-ns* (second (second form))) (newline) (recur))\n           \n           (and (seq? form) ('#{load-file clojure.core/load-file} (first form)))\n           (do (load-file repl-env (second form)) (newline) (recur))\n           \n           (and (seq? form) ('#{load-namespace} (first form)))\n           (do (load-namespace repl-env (second form)) (newline) (recur))\n           \n           :else\n           (do (eval-and-print repl-env env form) (recur)))))\n      (-tear-down repl-env))))",
          :title "repl specials table",
          :repo "clojurescript",
          :tag "r971",
          :filename "src/clj/cljs/repl.clj",
          :lines [133 162]},
 :examples [{:id "e81eb3", :content "```clj\n(in-ns 'foo.core)\n```"}],
 :full-name "specialrepl/in-ns",
 :clj-symbol "clojure.core/in-ns"}

```

Retrieve the API data for this symbol:

```clj
;; from Clojure REPL
(require '[clojure.edn :as edn])
(-> (slurp "https://raw.githubusercontent.com/cljsinfo/cljs-api-docs/catalog/cljs-api.edn")
    (edn/read-string)
    (get-in [:symbols "specialrepl/in-ns"]))
```

-->