# progress

A simple progress bar widget for the command line in zepto.

# Installation

```
zeps install hellevre/progress
```

# Example Output

```
[###                                               ] 6% (31/500) Elapsed Time: 00:00:04 ETA: 00:01:02
```

# Usage

You can either build a progress bar yourself (using `make-progress-bar`) or
create a context in which it will run (using `with-progress-bar`).

```clojure
(define my-progress (make-progress-bar 100)) ; 100 is the total size of elements, step size will be 10
(define my-progress (make-progress-bar 100 1)) ; the same as above, but the step size will be 1
(update-progress-bar my-progress 10) ; 10 elements have ben processed


(with-progress :as my-progress :to 100 :step 10 ; the same as above, but creating a context
  (for 101 ((update-progress-bar my-progress i) (system "sleep" ["0.1"])))
  (write "Done!")
  (exit 0))
```

<hr/>

Have fun!
