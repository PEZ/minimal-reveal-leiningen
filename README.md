# minimal Leiningen reveal project w/ nrepl middleware

To check that the Reveal nrepl middleware works for you, you can try this first without Calva:

## Start the nREPL server

In one terminal:

```sh
lein update-in :dependencies conj '[nrepl,"1.0.0"]' -- update-in :plugins conj '[cider/cider-nrepl,"0.28.5"]' -- update-in '[:repl-options,:nrepl-middleware]' conj '["cider.nrepl/cider-middleware"]' -- with-profile +reveal repl
nREPL server started on port ... on host localhost - nrepl://localhost:...
```

Then you should see some REPL info and the REPL prompt.

And you should see the Reveal window open. Blank at first, then output similar to what you see in the terminal

## Connect to the nREPL server

In another terminal:

```sh
lein repl :connect
Connecting to nREPL at ...
```

Again you should see some REPL info and the REPL prompt. And you should see the same things echoed in the Reveal window.

Evaluate something on that prompt. Say:

```clojure
user=> 42
42
```

You should see this evaluation happening in the Reveal window too.

## Using Calva

Jack-in selecting the deps.edn project type and select to launch with the alias `:reveal-nrepl-middleware`.

You should see the Reveal window open.

Load `src/hello.clj` and evaluate something there.

You should see the evaluation echo in the Reveal window.