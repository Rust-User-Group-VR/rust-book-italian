# The Rust Programming Language

[The Rust Programming Language](title-page.md)
[Prefazione](foreword.md)
[Introduzione](ch00-00-introduction.md)

## Cominciare con Rust

- [Iniziare](ch01-00-getting-started.md)
    - [Installazione](ch01-01-installation.md)
    - [Hello, World!](ch01-02-hello-world.md)
    - [Hello, Cargo!](ch01-03-hello-cargo.md)

- [Programmare un indovinello](ch02-00-guessing-game-tutorial.md)

- [Concetti comuni di programmazione](ch03-00-common-programming-concepts.md)
    - [Variabili e mutabilità](ch03-01-variables-and-mutability.md)
    - [Tipi di dati](ch03-02-data-types.md)
    - [Funzioni](ch03-03-how-functions-work.md)
    - [Commenti](ch03-04-comments.md)
    - [Control Flow](ch03-05-control-flow.md)

- [Comprendere le proprietà](ch04-00-understanding-ownership.md)
    - [Cosa sono le proprietà?](ch04-01-what-is-ownership.md)
    - [Reference e Borrowing](ch04-02-references-and-borrowing.md)
    - [Lo Slice Type](ch04-03-slices.md)

- [Utilizzare Strutture per strutturare dati correlati](ch05-00-structs.md)
    - [Definire e Istanziare Strutture](ch05-01-defining-structs.md)
    - [Un esempio di programma utlizzando Strutture](ch05-02-example-structs.md)
    - [Sintassi Dei Metodi](ch05-03-method-syntax.md)

- [Enums e Pattern Matching](ch06-00-enums.md)
    - [Definire un Enum](ch06-01-defining-an-enum.md)
    - [Il `match` Control Flow Construct](ch06-02-match.md)
    - [Controllo del Flow coinciso con `if let`](ch06-03-if-let.md)

## Alfabetizzazione di base Rust

- [Gestione di progetti in crescita con Pacchetti, Crates e Moduli](ch07-00-managing-growing-projects-with-packages-crates-and-modules.md)
    - [Pacchetti e Crates](ch07-01-packages-and-crates.md)
    - [Definizione dei Moduli per il controllo dello Scope e della Privacy](ch07-02-defining-modules-to-control-scope-and-privacy.md)
    - [Percorsi per fare riferimento a un elemento nel Tree del modulo](ch07-03-paths-for-referring-to-an-item-in-the-module-tree.md)
    - [Portare i percorsi dentro lo Scope con la keyword `use`](ch07-04-bringing-paths-into-scope-with-the-use-keyword.md)
    - [Separare dei Moduli in File Diversi](ch07-05-separating-modules-into-different-files.md)

- [Collezioni Comuni](ch08-00-common-collections.md)
    - [Memorizzare liste di valori utilizzando vettori](ch08-01-vectors.md)
    - [Memorizzare testo codificato UTF-8 utlizzando Stringhe](ch08-02-strings.md)
    - [Memorizzare Chiavi con valori associati nelle mappe hash](ch08-03-hash-maps.md)

- [Gestione Degli Errori](ch09-00-error-handling.md)
    - [Errori irreversibili con `panic!`](ch09-01-unrecoverable-errors-with-panic.md)
    - [Errori recuperabili con `Result`](ch09-02-recoverable-errors-with-result.md)
    - [`panic!` oppure `panic!`](ch09-03-to-panic-or-not-to-panic.md)

- [Tipi generici, tratti e tempi di vita](ch10-00-generics.md)
    - [Tipi di dati generici](ch10-01-syntax.md)
    - [Tratti: definizione del comportamento condiviso](ch10-02-traits.md)
    - [Convalida dei reference con Tempi Di Vita](ch10-03-lifetime-syntax.md)

- [Scrivere test automatizzati](ch11-00-testing.md)
    - [Come Scrivere i Tests](ch11-01-writing-tests.md)
    - [Controllare come i Tests vengono eseguiti](ch11-02-running-tests.md)
    - [Organizzazione dei Tests](ch11-03-test-organization.md)

- [Un progetto I/O: Creazione di un programma a riga di comando (CLI)](ch12-00-an-io-project.md)
    - [Accettazione degli argomenti della riga di comando](ch12-01-accepting-command-line-arguments.md)
    - [Lettura di un file](ch12-02-reading-a-file.md)
    - [Utilizzare il Refactoring per migliorare la modularità e la gestione degli errori](ch12-03-improving-error-handling-and-modularity.md)
    - [Sviluppare la funzionalità della libreria con Test Driven Development](ch12-04-testing-the-librarys-functionality.md)
    - [Lavorare con le variabili d'ambiente](ch12-05-working-with-environment-variables.md)
    - [Scrittura di Messaggi di Errore in Standard di Errore anziché in Output Standard](ch12-06-writing-to-stderr-instead-of-stdout.md)

## Pensare in Rust

- [Caratteristiche del linguaggio funzionale: Iteratori e Closures](ch13-00-functional-features.md)
    - [Closures: Funzioni anonime che catturano il loro ambiente](ch13-01-closures.md)
    - [Elaborare una serie di elementi con iteratori](ch13-02-iterators.md)
    - [Migliorare il nostro progetto I/O](ch13-03-improving-our-io-project.md)
    - [Confronto delle prestazioni: Cicli e Iteratori](ch13-04-performance.md)

- [Maggiori informazioni su Cargo and Crates.io](ch14-00-more-about-cargo.md)
    - [Personalizzazione delle Build con Profili di Rilascio](ch14-01-release-profiles.md)
    - [Pubblicazione di una Crate su Crates.io](ch14-02-publishing-to-crates-io.md)
    - [Aree di lavoro Cargo](ch14-03-cargo-workspaces.md)
    - [Installazione di file binari da Crates.io con `cargo install`](ch14-04-installing-binaries.md)
    - [Estendere Cargo con comandi personalizzati](ch14-05-extending-cargo.md)

- [Puntatori Intelligenti](ch15-00-smart-pointers.md)
    - [Utilizzo di `Box<T>` per puntare ai dati nell'Heap](ch15-01-box.md)
    - [Trattare i puntatori intelligenti come reference regolari con il tratto `Deref`](ch15-02-deref.md)
    - [Esecuzione del codice in modalità Cleanup con il tratto `Drop`](ch15-03-drop.md)
    - [`Rc<T>`, Il puntatore intelligente con Conteggio dei reference](ch15-04-rc.md)
    - [`RefCell<T>` ed il Pattern di mutabilità interiore](ch15-05-interior-mutability.md)
    - [I cicli di reference possono causare memory leak](ch15-06-reference-cycles.md)

- [Concorrenza impavida](ch16-00-concurrency.md)
    - [Utilizzare Threads per eseguire codice contemporaneamente](ch16-01-threads.md)
    - [Utilizzo del passaggio di messaggi per trasferire dati tra Thread](ch16-02-message-passing.md)
    - [Concorrenza a stato condiviso](ch16-03-shared-state.md)
    - [Concorrenza estensibile con i tratti `Sync` e `Send`.](ch16-04-extensible-concurrency-sync-and-send.md)

- [Caratteristiche della Programmazione Orientata agli oggetti di Rust](ch17-00-oop.md)
    - [Characteristics of Object-Oriented Languages](ch17-01-what-is-oo.md)
    - [Using Trait Objects That Allow for Values of Different Types](ch17-02-trait-objects.md)
    - [Implementing an Object-Oriented Design Pattern](ch17-03-oo-design-patterns.md)

## Advanced Topics

- [Patterns and Matching](ch18-00-patterns.md)
    - [All the Places Patterns Can Be Used](ch18-01-all-the-places-for-patterns.md)
    - [Refutability: Whether a Pattern Might Fail to Match](ch18-02-refutability.md)
    - [Pattern Syntax](ch18-03-pattern-syntax.md)

- [Advanced Features](ch19-00-advanced-features.md)
    - [Unsafe Rust](ch19-01-unsafe-rust.md)
    - [Advanced Traits](ch19-03-advanced-traits.md)
    - [Advanced Types](ch19-04-advanced-types.md)
    - [Advanced Functions and Closures](ch19-05-advanced-functions-and-closures.md)
    - [Macros](ch19-06-macros.md)

- [Final Project: Building a Multithreaded Web Server](ch20-00-final-project-a-web-server.md)
    - [Building a Single-Threaded Web Server](ch20-01-single-threaded.md)
    - [Turning Our Single-Threaded Server into a Multithreaded Server](ch20-02-multithreaded.md)
    - [Graceful Shutdown and Cleanup](ch20-03-graceful-shutdown-and-cleanup.md)

- [Appendix](appendix-00.md)
    - [A - Keywords](appendix-01-keywords.md)
    - [B - Operators and Symbols](appendix-02-operators.md)
    - [C - Derivable Traits](appendix-03-derivable-traits.md)
    - [D - Useful Development Tools](appendix-04-useful-development-tools.md)
    - [E - Editions](appendix-05-editions.md)
    - [F - Translations of the Book](appendix-06-translation.md)
    - [G - How Rust is Made and “Nightly Rust”](appendix-07-nightly-rust.md)
