## REVERSE ENNGINEERING

Maggiori dettagli a: http://people.unica.it/giorgiogiacinto/files/2016/05/14.ReverseEngineering.pdf

### ELF
•  Executable and Linkable Format
•  Eseguibile nei sistemi Linux (a 32 e a 64 bit)
–  Gli eseguibili a 32 e 64 bit NON sono gli stessi
–  Differenze, ad esempio, nella ges6one della memoria
•  Eseguibile diviso (generalmente) in qua-ro par5
•  ELF Header
–  Descrive le informazioni di base sul file
–  Esempio: Tipo di architeMura, indirizzi e dimensioni delle altre par6
•  Sec3on Header
–  Descrive la posizione di tuMe le sezioni dell’eseguibile
–  Obbligatoria nel file .o (prima del linking)
•  Program Header
–  Descrive le sezioni dell’eseguibile che vengono caricate in memoria durante l’esecuzione del programma (segmen?)
–  Obbligatoria nel file eseguibile
•  Data
–  I da6 veri e propri del file

### readelf
–  E’ un tool che trovate in qualsiasi distribuzione di Linux
–  Fornisce informazioni molto u6li sulla organizzazione del file

<PRE> <CODE> readelf –h sum_number </CODE>  </PRE>

 ### StruMura della Memoria Processo Linux X86 (2)
•  Heap
–  Memoria allocata dinamicamente
•  Stack
–  Composto da frames
–  Con6ene numerose informazioni rela6ve alle funzioni
–  Parametri funzioni, indirizzo di ritorno, variabili locali...
•  Ogni volta che una funzione viene invocata, un frame viene allocato in memoria
•  Func5on arguments
–  Gli argomen6 della funzione in memoria
•  Indirizzo di ritorno
–  L’indirizzo a cui la funzione deve ritornare al termine della sua esecuzione
•  Puntatore al frame
–  E’ considerato la “base” del frame
•  Variabili Locali
–  Le variabili definite nella funzione

### PER EFFETTUARE L?ANALISI STATICE BISOGNA DISASSEMBLARE L?ESEGUIBILE

Per fare questo, possiamo usare il tool objdump
–  objdump –d sum_number

•  Intel CISC
–  Complex Instruc6on Set Computer
–  Numero elevato di istruzioni (ma a noi ne interessano solo alcune!)
•  Convenzione AT&T per le istruzioni (opcode, sorgente, des5nazione)
–  Usata su Linux! (Su Windows si usa la convenzione Intel con sorgente e des6nazione
inver6te)
•  Indirizzamento a 32 bit
•  Li-le endian!
–  La memorizzazione avviene «al contrario»
–  Il byte MENO significa6vo viene memorizzato nell’indirizzo PIU’ BASSO

### GDB  (Gnu DeBugger)

E’ il programma open source «per eccellenza» per effe-uare l’analisi
dinamica di eseguibili X86/X64
•  Funziona su Linux, Windows, OSX
•  Una miriade di funzionalità!
•  Consente di interrompere l’esecuzione di un programma ad una specifica istruzione (breakpoints)
–  Potete analizzare la memoria e i registri!
•  Consente anche di impostare delle interruzioni condizionate
all’esecuzione di cer5 even5 (condi3onal breakpoints)
•  GDB consente di trovare bugs in un programma (o anche di sfru-arli a nostro vantaggio...)

