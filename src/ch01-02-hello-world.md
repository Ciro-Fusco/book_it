## Hello, World!

Ora che hai installato Rust, scriviamo il tuo primo programma in Rust. È
tradizione che quando si impara una nuovo linguaggio, si scriva un piccolo programma che stampa
il testo `Hello, World!` sullo schermo, per questo motivo faremo lo stesso qui!

> Nota: Questo libro implica una familiarità di base con la linea di comando. Rust non fa
> nessuna richiesta specifica in merito alla modifica o all'attrezzatura o al luogo in cui il codice viene scritto, quindi
> se si preferisce utilizzare un ambiente di sviluppo integrato (IDE) invece della
> riga di comando, sentiti libero di usare il tuo IDE preferito. Molti IDE ora
> supportano Rust; controlla la documentazione dell'IDE per i dettagli. Recentemente,
> Il team Rust si è concentrato sull'abilitazione di un grande supporto e progresso nell'ambito dell'IDE,
> si stanno facendo grandi progressi su questo fronte!

### Creare una directory per il progetto

Comincerai creando una directory per immagazzinare i tuoi progetti in Rust.A Rust non importa
dove si trova il tuo codice, ma per gli esercizi e i progetti in questo libro,
suggeriamo di creare una directory _projects_ nella tua home directory e di tenere tutti
i tuoi progetti lì.

Apri un terminale e scrivi il seguente comando per creare una directory _projects_
e una directory per il progetto “Hello, world!” all'interno della directory _projects_.

Per Linux, macOS, e PowerShell su Windows, inserisci questi comandi:

```console
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```

For Windows CMD, enter this:

```cmd
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
```

### Scrivere ed eseguire un programma Rust

Quindi, crea un nuovo file sorgente e chiamalo _main.rs_. I file Rust finiscono sempre con
l'estensione _.rs_ . Se stai usando più di una parola nel nome del tuo file, usa
un underscore per separarli. Per esempio, usa _hello_world.rs_ piuttosto che
_helloworld.rs_.

Ora apri il file _main.rs_ che hai appena creato e inserisci il codice nel listato 1-1.

<span class="filename">Filename: main.rs</span>

```rust
fn main() {
    println!("Hello, world!");
}
```

<span class="caption">Listing 1-1: A program that prints `Hello, world!`</span>

Salvare il file e tornare alla finestra del terminale. Su Linux o macOS, inserire
i seguenti comandi per compilare ed eseguire il file:

```console
$ rustc main.rs
$ ./main
Hello, world!
```

Su Windows, inserisci il comando `.\main.exe` invece di `./main`:

```powershell
> rustc main.rs
> .\main.exe
Hello, world!
```

A prescindere dal vostro sistema operativo, dovrebbe essere stampata a terminale la stringa `Hello, world!`
Se non si vede questo output, fare riferimento al
[“Troubleshooting”][troubleshooting]<!-- ignore --> sezione dell' installazione
per ottenere aiuto

Se è stato stampato `Hello, world!`, congratulazioni! Hai ufficialmente scritto
un programma in Rust.

### Anatomia di un programma Rust

Rivediamo in dettaglio quello che è appena successo nel tuo programma "Hello, world!".
Ecco il primo pezzo del puzzle:

```rust
fn main() {

}
```

Queste linee definiscono una funzione in Rust. La funzione `main` è speciale: è
sempre il primo codice che viene eseguito in ogni programma eseguibile Rust. La prima
linea dichiara una funzione chiamata `main` che non ha parametri e restituisce
niente. Se ci fossero dei parametri, andrebbero all'interno delle parentesi, `()`.

Inoltre, si noti che il corpo della funzione si tra due in parentesi graffe, `{}`. Rust le
richiede intorno ai corpi delle funzioni. E consigliato posizionare l'apertura
della parentesi graff asulla stessa linea della dichiarazione della funzione, aggiungendo uno spazio in mezzo.

Quando è stato scritto questo libro,era in fase di sviluppo uno strumento di formattazione automatica chiamato `rustfmt`.
Se si desidera attenersi a uno stile standard per i progetti Rust
, `rustfmt` formatterà il tuo codice. Il team Rust
prevede di includere questo strumento con la distribuzione Rust standard, insieme a
`rustc`. Quindi, a seconda di quando si legga questo libro, potrebbe già essere installato
sul tuo computer! Controlla la documentazione online per maggiori dettagli.

All'interno della funzione`main` è presente il seguente codice:

```rust
    println!("Hello, world!");
```

Questa linea fa tutto il lavoro di questo piccolo programma: stampa il testo a
schermo. Ci sono quattro dettagli importanti da notare:

1)Lo stile Rust è quello di indentare con quattro spazi, non con un tab.

2)Il `println! ` chiama una macro Rust. Se invece stessimo chiamando una funzione,
verrebbe inserito come `println` (senza la `!`). Parleremo delle macro Rust
più dettaglio nel capitolo 19. Per ora, basta sapere che utilizzando un `!`
stai chiamando una macro invece di una funzione normale.

3)`"Hello, world!" ` e la stringa che passiamo come un argomento
a `println! `.Così la stringa è stampata sullo schermo.

4)Terminiamo la linea con un punto e virgola (`;`).Esso indica che questa
istruzione è finita. La maggior parte delle linee di codice Rust
terminano con un punto e virgola.

### La compilazione e l'esecuzione sono passi separati

Prima di eseguire un programma Rust, è necessario compilarlo utilizzando il compilatore Rust
inserendo il comando `rustc` e passandogli il nome del tuo file sorgente, in questo modo:

```console
$ rustc main.rs
```

Se conosci C o C++, noterai che è simile a `gcc`
o `clang`. Dopo aver compilato con successo, Rust produce un eseguibile binario.

Su Linux, macOS, e Powershell su Windows, è possibile vedere l'eseguibile
inserendo il comando `ls` nella shell. Su Linux e macOS, vedrete due
file. Con Powershell su Windows, vedrai gli stessi tre file che
vedresti usando il CMD.

```text
$ ls
main  main.rs
```

Con il CMD su Windows, si deve inserire quanto segue:

```cmd
> dir /B %= the /B option says to only show the file names =%
main.exe
main.pdb
main.rs
```

Questo mostra il file di codice sorgente con l'estensione _.rs_ , il file eseguibile
(_main.exe_ su Windows, ma _main_ su tutte le altre piattaforme) e, quando si utilizza
Windows, un file contenente informazioni di debug con l'estensione _.pdb_ .
Da qui si esegue il file _main_ o _main.exe_ in questo modo:

```console
$ ./main # or .\main.exe on Windows
```

Se _main.rs_ era il tuo programma “Hello, world!”,l'istruzione precedente stamperà `Hello, world!` sul tuo terminale.

Se hai più familiarità con un linguaggio dinamico, come Ruby, Python, o
Javascript, potresti non conoscere come compilare ed eseguire un programma con
passi separati. Rust è un linguaggio compilato in anticipo, il che significa che puoi
compilare un programma e dare l'eseguibile a qualcun altro, il quale potrà eseguirlo
anche senza avere Rust installato. Se si dà a qualcuno un file _.rb_, _.py_, o
_. js_ , hanno bisogno di avere Ruby, Python, o Javascript
installato (rispettivamente). Ma in quei linguaggi, è necessario un solo comando per
compilare ed eseguire il programma. Tutto è un trade-off nel design del linguaggio..

Compilare con `rustc` va bene per programmi semplici, ma con progetti
più grandi, si dovranno gestire tutte le opzioni e rendere più facile la condivisione del tuo
codice. Successivamente, ti presenteremo lo strumento Cargo, che ti aiuterà a scrivere
programmi Rust del mondo reale.

[troubleshooting]: ch01-01-installation.html#troubleshooting
