# Práctica 1
Esta es la práctica 1 de genómica computacional semtre 2020-2 
## Comandos de la Práctica 01
Diana Balmaseda Villarreal

### Parte I.
echo "$SHELL" /bin/bash
mkdir data | mkdir filtered | mkdir raw_data | mkdir meta | mkdir scripts | mkdir figures | mkdir archive
mv filtered/ data/ mv raw_data/ data/

Respuesta 4: El orden y la organización de los directorios creados se debe a una convención para así hacer más fácil el uso de los archivos al compartir la información.

### Parte II.
chmod u+x delay.sh
ls -l
Imprime la primera línea de texto, duerme 30 segundos con el comando sleep 30 luego imprime la última línea.
./delay.sh &
killall sleep

### Parte III.
El covid-19 o SARS-CoV-2 es un virus que pertenece a la familia coronaviridae, estos virus se clasifican en alpha, beta, gamma y delta, el covid-19 pertenece a la clase beta. Se sabe que este está relacionado con un tipo de coronavirus que parecen los murciélagos, aunque fue necesario in hospedero intermediario para que llegara al humano, también se sabe que ha mutado muy rápidamente y por los análisis hechos el diferentes paises se sabe que el virus que afecta a diferentes paises no es el mismo en todo sentido por lo que el virus ha evolucionado muy rápidamente. Este virus está compuesto de una cadena sencilla de RNA enrollada dentro de una dicoproteína de membrana, rodeada de proteína espiculas glicosilada(S) este úne al receptor en la célula.
El saber la anatomía y estructura de este virus nos pertmite la realización de vacunas para crear anticuerpos que inhiban la unión de el virus. Se realizan 4 fases para el desarrollo de una vacuna y más de mil millones de inversión. Actualmente hay 51 proyectos de creación de vacuna. 

mv 'sequence (1).fasta' sequence_1.fasta
mv sra_data.fastq.gz ~/Desktop/genomica_2020-2/dbalmaseda_p01/data/raw_data/

### Parte IV.
ln -s ~/Desktop/genomica_2020-2/dbalmaseda_p01/data/raw_data/...
mkdir protein | mv sequence_2.faa ~/Desktop/genomica_2020-2/dbalmaseda_p01/data/filtered/proteins
head -n 2 sequence_#.faa >> ~/Desktop/genomica_2020-2/dbalmaseda_p01/comandos.txt
>pdb|6VYB|C Chain C, spike glycoprotein
MGILPSPGMPALLSLVSLLSVLLMGCVAETGTQCVNLTTRTQLPPAYTNSFTRGVYYPDKVFRSSVLHST
>pdb|6VYB|B Chain B, spike glycoprotein
MGILPSPGMPALLSLVSLLSVLLMGCVAETGTQCVNLTTRTQLPPAYTNSFTRGVYYPDKVFRSSVLHST
>pdb|6VYB|A Chain A, spike glycoprotein
MGILPSPGMPALLSLVSLLSVLLMGCVAETGTQCVNLTTRTQLPPAYTNSFTRGVYYPDKVFRSSVLHST

head -n 3 sequence_#.faa >> glycoproteins.faa 

cd.. | head -n 5 sequence.fasta
>NC_045512.2 Severe acute respiratory syndrome coronavirus 2 isolate Wuhan-Hu-1, complete genome
ATTAAAGGTTTATACCTTCCCAGGTAACAAACCAACCAACTTTCGATCTCTTGTAGATCTGTTCTCTAAA
CGAACTTTAAAATCTGTGTGGCTGTCACTCGGCTGCATGCTTAGTGCACTCACGCAGTATAATTAATAAC
TAATTACTGTCGTTGACAGGACACGAGTAACTCGTCTATCTTCTGCAGGCTGCTTACGGTTTCGTCCGTG
TTGCAGCCGATCATCAGCACATCTAGGTTTCGTCCGGGTGTGACCGAAAGGTAAGATGGAGAGCCTTGTC
grep '>' -c sequence.fasta 
1

zless sra_data.fasta.gz | head -n 5
>SRR11241254.1.1 1 length=40
GTTAAAGGTTTATACCTTCCCAGGTAACAAACCAACCAAC
>SRR11241254.2.1 2 length=40
GTTAAAGGTTTATACCTTCCCAGGTAACAAACCAACCAAC
>SRR11241254.3.1 3 length=40

zless sra_data.fasta.gz | grep '>' -c 
131950

zless sra_data.fastq.gz | head -n 12 >> ~/Desktop/genomica_2020-2/dbalmaseda_p01/comandos.txt

@SRR11241254.1.1 1 length=40
GTTAAAGGTTTATACCTTCCCAGGTAACAAACCAACCAAC
+SRR11241254.1.1 1 length=40
GGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGG
@SRR11241254.2.1 2 length=40
GTTAAAGGTTTATACCTTCCCAGGTAACAAACCAACCAAC
+SRR11241254.2.1 2 length=40
GGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGG
@SRR11241254.3.1 3 length=40
GTTAAAGGTTTATACCTTCCCAGGTAACAAACCAACCAAC
+SRR11241254.3.1 3 length=40
GGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGG
Utilicé el patrón '@SRR' y me dieron 131950, zless sra_data.fastq.gz | grep SRR -c

.faa codifica aminoácidos mientras que .fastq y .fasta codifican  nucleótidos, la diferencia entre .fastq y .fasta está a continuación.
	Tienen el mismo número de genes, secuencias, pero el formato fastq tiene la información extra especificada abajo.
	El formato .fastq es una extensión al formato fasta pero este nos indica la calidad asociada a cada nucleótido. LAs líneas indican lo siguiente:
1. Nombre de la secuencia
2. Secuencia
3. +/ Nombre de la secuencia
4. Valor de calidad codificado

less solo nos da toda la información mientras que less -S sólo nos da la primera fila.
less -S sequence.gff3 | cut -f3 | grep gene -c
11
