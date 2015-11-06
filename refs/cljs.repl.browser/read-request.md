## cljs.repl.browser/read-request



 <table border="1">
<tr>
<td>function</td>
<td><a href="https://github.com/cljsinfo/cljs-api-docs/tree/0.0-927"><img valign="middle" alt="[+] 0.0-927" title="Added in 0.0-927" src="https://img.shields.io/badge/+-0.0--927-lightgrey.svg"></a> </td>
</tr>
</table>


 <samp>
(__read-request__ rdr)<br>
</samp>

---







Source code @ [github](https://github.com/clojure/clojurescript/blob/r971/src/clj/cljs/repl/browser.clj#L160-L164):

```clj
(defn read-request [rdr]
  (let [line (.readLine rdr)]
    (cond (.startsWith line "POST") (read-post line rdr)
          (.startsWith line "GET") (read-get line rdr)
          :else {:method :unknown :content line})))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r971
└── src
    └── clj
        └── cljs
            └── repl
                └── <ins>[browser.clj:160-164](https://github.com/clojure/clojurescript/blob/r971/src/clj/cljs/repl/browser.clj#L160-L164)</ins>
</pre>

-->

---



###### External doc links:

[`cljs.repl.browser/read-request` @ crossclj](http://crossclj.info/fun/cljs.repl.browser/read-request.html)<br>

---

 <table>
<tr><td>
<img valign="middle" align="right" width="48px" src="http://i.imgur.com/Hi20huC.png">
</td><td>
Created for the upcoming ClojureScript website.<br>
[edit here] | [learn how]
</td></tr></table>

[edit here]:https://github.com/cljsinfo/cljs-api-docs/blob/master/cljsdoc/cljs.repl.browser/read-request.cljsdoc
[learn how]:https://github.com/cljsinfo/cljs-api-docs/wiki/cljsdoc-files

<!--

This information was too distracting to show to readers, but I'll leave it
commented here since it is helpful to:

- pretty-print the data used to generate this document
- and show how to retrieve that data



The API data for this symbol:

```clj
{:ns "cljs.repl.browser",
 :name "read-request",
 :type "function",
 :signature ["[rdr]"],
 :source {:code "(defn read-request [rdr]\n  (let [line (.readLine rdr)]\n    (cond (.startsWith line \"POST\") (read-post line rdr)\n          (.startsWith line \"GET\") (read-get line rdr)\n          :else {:method :unknown :content line})))",
          :title "Source code",
          :repo "clojurescript",
          :tag "r971",
          :filename "src/clj/cljs/repl/browser.clj",
          :lines [160 164]},
 :full-name "cljs.repl.browser/read-request",
 :full-name-encode "cljs.repl.browser/read-request",
 :history [["+" "0.0-927"]]}

```

Retrieve the API data for this symbol:

```clj
;; from Clojure REPL
(require '[clojure.edn :as edn])
(-> (slurp "https://raw.githubusercontent.com/cljsinfo/cljs-api-docs/catalog/cljs-api.edn")
    (edn/read-string)
    (get-in [:symbols "cljs.repl.browser/read-request"]))
```

-->