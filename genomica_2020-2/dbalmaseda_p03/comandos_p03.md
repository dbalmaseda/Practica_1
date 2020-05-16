# Comandos de la Práctica 03
## Diana Balmaseda Villarreal

## Parte I. 
01. 
  * La secuencia `sequence_x.fasta` pertenece a `Mycoplasma genitalium strain G-37 16S ribosomal RNA`  
  * Es una región genómica de importancia. 16S rRNA es empleado para reconstruir filogenias ya que tienen una baja tasa de evolución.
  * Un marcador molecular (genético) es una secuencia de ADN con una locación conocida dentro de un cromosoma. (NIH)
  * Los marcadores genéticos son importantes ya que nos ayudan a vincular una enfermedad genética con su gen responsable.

02. 
BLAST | Definición | Aplicación
----- | ---------- | -----------
blastn | Basic Local Alignment Search Tool for nucleotides | Compara una secuencia de nucleótidos contra una base de datos que contiene secuencias de nucleótidos |
blastp | Este es un BLAST con gaps, para comparación de proteínas | Se emplea para comparar secuencias de aminoácidos contra bases de aminoácidos|
tblastn | BLAST traducido a nucleótidos | Una secuenia de proteínas es comparada con la traducción de 'six-frame' de secuencias en una bases de datos de nucleótidos |

03. En el artículo [The genome of Leishmania adleri from a mammalian host highlights chromosome fission in Sauroleishmania](https://www.nature.com/articles/srep43747.pdf) realizaron el análisis de la librería ` MARV/ET/1975/HO174 `, donde `HO174` se refiere a una especie de Leishmanias. Primero se realizó el análisis de calidad usando FastQC, luego dependiendo de los alineamientos del FastQC fueron eliminados los primer de la secuencias de PCR, a continuación determinaron los contaminantes de ADN usando BLASTn, finalmente se corrió otra ves el FastQC para eliminar el contenido de excesos de GC. A continuación estas lecturas procesadas fueron ensambladas *de novo* empleando Velvet v1.2.09 con kmer de 53. 
# Parte II.
01. El problrema de los puentes de Euler consiste en 4 islas conectadas por 7 puentes, la idea es pasar por los 7 puentes sin pasar dos veces por el mismo puente. No se puede resolver dado que al representar el problema en forma de gráfica, siendo las islas los nodos y los puentes las aristas, entonces cada nodo tiene grado impar por lo que en algún momento al entrar a una ciudad ya no podras salir de esta sin usar el mismo puente. 

02. 

03. **N50** se refiere a una medida de la longitud media de un conjunto de secuencias nucleótidas, este estadístico es empleado en el ensambe de genomas para la longitud de los *contig*. Desde un punto de vista matemático el **N50** se define como la longitud N por la cual el 50% de todas las bases en las secuencias de longitud L<N
 Dado un conjunto de *contig*, **L50** se define como el menor número de *contigs* tal que la suma de su longitud sea la mitad de la longitud del genoma.
# Referencias.
* BLAST. (2019, 8 de octubre). Wikipedia, La enciclopedia libre. [wiki_Blast](https://es.wikipedia.org/w/index.php?title=BLAST&oldid=120045072)

* Coughlan, S., Mulhair, P., Sanders, M. et al. The genome of Leishmania adleri from a mammalian host highlights chromosome fission in Sauroleishmania. Sci Rep 7, 43747 (2017). https://doi.org/10.1038/srep43747 

