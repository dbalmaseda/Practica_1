# Proyecto Final Genómica Computacional 2020-2
## Mapeo SARS-CoV2

* Diana Balmaseda
* Gabriel Loya  
* Luis Tenorio



Para filtrar con ERNE:
`erne-filter --min-mean-phred-quality 20 --query1 SRR10971381_1.fastq.gz --query2 SRR10971381_2.fastq.gz --output-prefix erne-filter-trimmed`

Para indexar el genoma del SARS_CoV2:
`bowtie2-build MN908947.fna SARS_CoV2`
`cp bowtie2_archives/*.bt2 miniconda3/bin/indexes`

Para alinear los archivos con bowtie2 de manera local y guardar los reads alineados como archivos fastq en el directorio /aligned:
`bowtie2 --local --al-conc aligned/ -x miniconda3/bin/indexes/SARS_CoV2 -1 SRR10971381_1.fastq.gz -2 SRR10971381_2.fastq.gz > SARS_bowtie_local.sam`

Para obtener los estadísticos del alineamiento:
`samtools view -Sb SARS_bowtie_local.sam | samtools sort -o SARS_bowtie.sorted.bam && samtools flagstat SARS_bowtie.sorted.bam > stats.map.txt`
    
Para obtener el archivo bam sólo con las secuencias que alinearon al genoma de referencia:
`samtools sort SARS_bowtie_local.sam -o SARS-CoV2_local_sorted.bam`
`samtools view -b -F 4 SARS-CoV2_local_sorted.bam -o SARS_aligned_bowtie2.bam`
