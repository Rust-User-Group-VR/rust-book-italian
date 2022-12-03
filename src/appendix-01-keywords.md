## Appendice A: Parole Chiave

Il seguente elenco contiene le parole chiave riservate per attuali o futuri utilizzi del linguaggio Rust. In quanto tali, non possono essere utilizzati come identificatori (except
as raw identifiers as we’ll discuss in the “[Identificatori Grezzi][identificatori-grezzi]<!-- ignore -->” section). Gli identificatori sono nomi
di funzioni, variabili, parametri, campi di struct, moduli, crates, costanti,
macro, valori static, attributi, tipi, tratti o lifetimes.

[identificatori-grezzi]: #identificatori-grezzi

### Keywords Currently in Use

Di seguito è riportato un elenco di parole chiave attualmente in uso, descritte con le relative funzionalità.

* `as` - esegue il casting primitivo, disambigua il tratto specifico che contiene
  un elemento o rinomina gli elementi nelle istruzioni `use`
* `async` -  restituisce un `Future` invece di bloccare il thread corrente
* `await` - sospendere l'esecuzione fino a quando il risultato di un `Future` non è pronto
* `break` - esce da un ciclo immediatamente
* `const` - definisce elementi costanti o puntatori grezzi costanti
* `continue` - continua alla successiva iterazione del ciclo
* `crate` - in un percorso del modulo, fa riferimento al root della crate
* `dyn` - invio dinamico a un oggetto di tipo tratto
* `else` - fallback per i costrutti di control flow `if` e `if let`
* `enum` - definisce un'enumerazione
* `extern` - collega una funzione esterna o una variabile
* `false` - valore Booleano falso
* `fn` - definisce una funzione o il tipo di puntatore di funzione
* `for` - esegue il ciclo sugli elementi di un iteratore, implementa un tratto o specifica la
  durata di rango superiore
* `if` - branch basato sul risultato di un'espressione condizionale
* `impl` - implementa funzionalità intrinseche o di tratto
* `in` - parte della sintassi del ciclo `for`
* `let` - associa un valore a una variabile.
* `loop` - ciclo incondizionato
* `match` - abbinare un valore ai pattern
* `mod` - definisce un modulo
* `move` - fa in modo che una closure si impossessi di tutte le sue catture
* `mut` - denota la mutabilità in references, puntatori grezzi o associazioni di pattern
* `pub` - denota la visibilità pubblica nei campi struct, nei blocchi `impl` o nei moduli
* `ref` - vincola per riferimento
* `return` - restituzione da una funzione
* `Self` - un alias di tipo per il tipo che stiamo definendo o implementando
* `self` - argomento del metodo o modulo corrente
* `static` - variabile globale o ciclo di vita che dura l'intera esecuzione del programma
* `struct` - definisce una struttura
* `super` - modulo padre del modulo corrente
* `trait` - definisce un tratto
* `true` - valore Booleano vero
* `type` - definisce un alias di tipo o un tipo associato
* `union` - definisce una [unione][union]<!-- ignore -->; è solo una parola chiave quando viene utilizzata
  in una dichiarazione di tipo union
* `unsafe` - denota codice, funzioni, tratti o implementazioni come non sicuri
* `use` - porta i simboli dentro lo scope
* `where` - denota clausole che vincolano un tipo
* `while` - ciclo condizionale in base al risultato di un'espressione

[union]: ../reference/items/unions.html

### Parole chiave riservate per uso futuro

Le seguenti parole chiave non hanno ancora alcuna funzionalità ma sono riservate da
Rust per un potenziale uso futuro.

* `abstract`
* `become`
* `box`
* `do`
* `final`
* `macro`
* `override`
* `priv`
* `try`
* `typeof`
* `unsized`
* `virtual`
* `yield`

### Identificatori Grezzi

*Raw identifiers* are the syntax that lets you use keywords where they wouldn’t
normally be allowed. You use a raw identifier by prefixing a keyword with `r#`.

For example, `match` is a keyword. If you try to compile the following function
that uses `match` as its name:

<span class="filename">Filename: src/main.rs</span>

```rust,ignore,does_not_compile
fn match(needle: &str, haystack: &str) -> bool {
    haystack.contains(needle)
}
```

you’ll get this error:

```text
error: expected identifier, found keyword `match`
 --> src/main.rs:4:4
  |
4 | fn match(needle: &str, haystack: &str) -> bool {
  |    ^^^^^ expected identifier, found keyword
```

The error shows that you can’t use the keyword `match` as the function
identifier. To use `match` as a function name, you need to use the raw
identifier syntax, like this:

<span class="filename">Filename: src/main.rs</span>

```rust
fn r#match(needle: &str, haystack: &str) -> bool {
    haystack.contains(needle)
}

fn main() {
    assert!(r#match("foo", "foobar"));
}
```

This code will compile without any errors. Note the `r#` prefix on the function
name in its definition as well as where the function is called in `main`.

Raw identifiers allow you to use any word you choose as an identifier, even if
that word happens to be a reserved keyword. This gives us more freedom to
choose identifier names, as well as lets us integrate with programs written in
a language where these words aren’t keywords. In addition, raw identifiers
allow you to use libraries written in a different Rust edition than your crate
uses. For example, `try` isn’t a keyword in the 2015 edition but is in the 2018
edition. If you depend on a library that’s written using the 2015 edition and
has a `try` function, you’ll need to use the raw identifier syntax, `r#try` in
this case, to call that function from your 2018 edition code. See [Appendix
E][appendix-e]<!-- ignore --> for more information on editions.

[appendix-e]: appendix-05-editions.html
