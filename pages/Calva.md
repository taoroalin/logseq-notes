---
title: Calva
---

## Jack in command
### lein update-in :dependencies conj [nrepl"0.8.2"] -- update-in :dependencies conj [clj-kondo"2020.04.05"] -- update-in :dependencies conj [cider/piggieback"0.4.2"] -- update-in :plugins conj [cider/cider-nrepl"0.23.0"] -- update-in [:repl-options^ :nrepl-middleware] conj '["cider.nrepl/cider-middleware"]' -- update-in [:repl-options^ :nrepl-middleware] conj '["cider.piggieback/wrap-cljs-repl"]' -- with-profile +dev repl :headless

### with profile dev

### headless

### lein update-in: update-in project ...args

### lein update-in :dependencies conj '[nrepl"0.8.2"]' -- update-in :dependencies conj '[clj-kondo"2020.04.05"]' -- update-in :dependencies conj '[cider/piggieback"0.4.2"]' -- update-in :plugins conj '[cider/cider-nrepl"0.23.0"]' -- update-in '[:repl-options :nrepl-middleware]' conj '["cider.nrepl/cider-middleware"]' -- update-in '[:repl-options :nrepl-middleware]' conj '["cider.piggieback/wrap-cljs-repl"]' -- with-profile +dev figwheel :headless

---
title: calva
---

## 
