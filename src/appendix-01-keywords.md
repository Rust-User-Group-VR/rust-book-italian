## Appendice A: Parole Chiave

Il seguente elenco contiene le parole chiave riservate per attuali o futuri utilizzi del linguaggio Rust. In quanto tali, non possono essere utilizzati come identificatori (tranne che come identificatori grezzi come discuteremo nella sezione “[Identificatori Grezzi][identificatori-grezzi]<!-- ignore -->”). Gli identificatori sono nomi
di funzioni, variabili, parametri, campi di struct, moduli, crates, costanti,
macro, valori static, attributi, tipi, tratti o lifetimes.

[identificatori-grezzi]: #identificatori-grezzi

### Parole chiave attualmente in uso

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

Gli *identificatori grezzi* sono la sintassi che ti consente di utilizzare le parole chiave dove di norma non sarebbe consentito. Si utilizza un identificatore grezzo anteponendo ad una parola chiave `r#`.

Ad esempio, `match` è una parola chiave. Se provi a compilare la seguente funzione
che usa `match` come nome:

<span class="filename">Filename: src/main.rs</span>

```rust,ignore,does_not_compile
fn match(needle: &str, haystack: &str) -> bool {
    haystack.contains(needle)
}
```

apparirà questo errore:

```text
error: expected identifier, found keyword `match`
 --> src/main.rs:4:4
  |
4 | fn match(needle: &str, haystack: &str) -> bool {
  |    ^^^^^ expected identifier, found keyword
```

L'errore dice che non puoi utilizzare la parola chiave `match` come funzione
identificatore. Per usare `match` come nome di una funzione, devi usare la sintassi dell'identificatore, così:

<span class="filename">Filename: src/main.rs</span>

```rust
fn r#match(needle: &str, haystack: &str) -> bool {
    haystack.contains(needle)
}

fn main() {
    assert!(r#match("foo", "foobar"));
}
```

Questo codice verrà compilato senza errori. Nota il prefisso `r#` sulla funzione
name nella sua definizione e dove la funzione viene chiamata in `main`.

Gli identificatori grezzi ti consentono di utilizzare qualsiasi parola tu scelga come identificatore, anche se
quella parola sembra essere una parola chiave riservata. Questo ci dà più libertà di
scegliere i nomi degli identificatori, oltre a permetterci di integrarci con i programmi scritti
una lingua in cui queste parole non sono parole chiave. Inoltre, gli identificatori grezzi
ti permettono di usare librerie scritte in un'edizione di Rust diversa da quella che il tuo crate
utilizza. Ad esempio, `try` non è una parola chiave nell'edizione 2015 ma è nell'edizione 2018. Se dipendi da una libreria scritta utilizzando l'edizione 2015 e
ha una funzione `try`, dovrai usare la sintassi dell'identificatore grezzo, `r#try` in
in questo caso, per chiamare quella funzione dal codice dell'edizione 2018. Vedi [Appendice
E][appendix-e]<!-- ignore --> for more information on editions.

[appendix-e]: appendix-05-editions.md
