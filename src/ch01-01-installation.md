## Installazione

Il primo passo è quello di installare Rust. Scaricheremo Rust attraverso `rustup`, uno
strumento a linea di comando per la gestione delle versioni Rust e tools associati. Ti servirà
una connessione internet per il download.

> Nota: Se preferisci non usare `rustup` per qualche motivo, si prega di consultare [Rust
> pagina di installazione](https://www.rust-lang.org/tools/install) per altre opzioni.

I seguenti passaggi installano l'ultima versione stabile del compilatore Rust.
La stabilità di Rust garantisce che tutti gli esempi nel libro che
vengono compilati continueranno a essere compilati anche con versioni più recenti di Rust. L'output potrebbe
differire leggermente tra le versioni, perché Rust migliora spesso i messaggi di errore
e di warning. In altre parole, qualsiasi nuova versione stabile di Rust si installi
utilizzando questi passaggi dovrebbe funzionare come previsto con il contenuto di questo libro.

> ### Notazione da riga di comando
>
> In questo capitolo e in tutto il libro, mostreremo alcuni comandi utilizzati nel
> terminale. Le linee che si dovrebbero inserire in un terminale iniziano tutte con `$`.
> Non hai bisogno di digitare il carattere `$`; indica l'inizio di ogni
> comando. Le linee che non iniziano con `$` in genere mostrano l'output
> del comando precedente. Inoltre, gli esempi specifici di Powershell useranno `>`
> piuttosto che `$`.

### Installazione di `rustup` su Linux o macOS

Se stai usando Linux o macOS, apri un terminale e inserisci il seguente comando:

```console
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

Il comando scarica uno script e avvia l'installazione del `rustup`,
che installa l'ultima versione stabile di Rust. Potrebbe essere richiesta
la tua password per proseguire. Se l'installazione è riuscita, apparirà la seguente riga:

```text
Rust is installed now. Great!
```

Inoltre, avrai bisogno di un linker di qualche tipo. E' probabile che ne avrai uno già
installato, ma se quando tenterai di compilare un programma Rust otterrai errori che indicano
che un link non può essere eseguito, ciò significa che il linker non è installato sul vostro
sistema e avrete bisogno di installarne uno manualmente. I compilatori C di solito contengono già
un linker. Controlla la documentazione della tua piattaforma su come installare una compilatore C.
Inoltre, alcuni pacchetti Rust dipendono da codice in C e avranno bisogno di un compilatore C. Pertanto, potrebbe valerne la pena installarne uno ora.

### Installare `rustup` su Windows

Su Windows, vai a [https://www.rust-lang.org/tools/install][install] e segui
le istruzioni per l'installazione di Rust. Ad un certo punto dell'installazione,
riceverai un messaggio indicando che avrai bisogno anche degli strumenti di compilazione C++ per
Visual Studio 2013 o successivo. Il modo più semplice per ottenerlo è quello di
installare [Build Tools for Visual Studio 2019][visualstudio].Quando chiederà quale
workloads installare controlla che "C++ build tools" sia selezionato e che il Windows 10 SDK e il pacchetto della lingua Inglese siano inclusi.

[installazione]: https://www.rust-lang.org/tools/install
[visualstudio]: https://visualstudio.microsoft.com/visual-cpp-build-tools/

Il resto di questo libro usa comandi che funzionano sia in _cmd.exe_ che in Powershell.
Se ci sono differenze specifiche, spiegheremo quale usare.

### Aggiornamento e disinstallazione

Dopo aver installato Rust tramite `rustup`, l'aggiornamento all'ultima versione è
facile. Dalla tua shell, esegui il seguente script di aggiornamento:

```console
$ rustup update
```

Per disinstallare Rust e `rustup`, esegui il seguente script di disinstallazione dalla
shell:

```console
$ rustup self uninstall
```

## Risoluzione dei problemi

Per verificare se Rust è installato correttamente, aprire una shell e inserire questa
riga:

```console
$ rustc -version
```

Dovresti vedere il numero di versione, l'hash del commit e la data del commit per l'ultima
versione stabile rilasciata nel seguente formato:

```text
rustc x.y.z (abcabcabc yyyy-mm-gg)
```

Se vedi queste informazioni, hai installato Rust con successo! Se non
vedi queste informazioni e sei su Windows, controlla che Rust sia nel tuo `%PATH%`
delle variabili di sistema. Se questo è tutto corretto e Rust ancora non funziona, ci sono
un po' di posti in cui puoi ottenere aiuto. Il più semplice è il canale #beginners su
[the official Rust Discord][discord]. Lì, puoi chattare con altri Rustaceans
(un soprannome sciocco con cui chiamiamo noi stessi) che potranno aiutarti. Altre risorse
puoi trovarle qui [the Users forum][users] e qui [Stack Overflow][stackoverflow].

[discord]: https://discord.gg/rust-lang
[users]: https://users.rust-lang.org/
[stackoverflow]: https://stackoverflow.com/questions/tagged/rust

### Documentazione locale

L'installazione di Rust include anche una copia della documentazione locale, quindi
è possibile leggerla offline. Eseguire `rustup doc` per aprire la documentazione locale nel
tuo browser.

Ogni volta che non conosci cosa fare o come usare un tipo o una funzione fornita dalla libreria standard, utilizza la documentazione per scoprirlo!
