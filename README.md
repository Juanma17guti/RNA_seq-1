# 🧬Análisis Transcriptómico🧬

## Descripción del Proyecto 📁
Este proyecto se basa en el artículo científico:
Fu, Nai Yang, et al. "EGF-mediated induction of Mcl-1 at the switch to lactation is essential for alveolar cell survival." Nature Cell Biology 17.4 (2015): 365–375.

El estudio analiza cómo el gen Mcl-1, un regulador crítico de la supervivencia celular, es inducido por EGF en el momento clave de la lactancia, asegurando la funcionalidad de las células alveolares en las glándulas mamarias.

### Objetivo 🎯
- **Tipo de análisis:** Análisis transcriptómico.
- **Propósito:** Exploración de datos y obtención de insights a partir de datasets públicos.

---

## 1. Inicio 🏁
Recuerda que al final del todo tienes definiciones de las diferentes herramientas utilizadas

Para comenzar necesitamos:  
### 🛠️ Entorno Conda  
El ambiente computacional diseñado para este proyecto:  
[RNA_seq-1.yml](https://github.com/Juanma17guti/Conda_env_list/blob/main/RNA_seq-1.yml). Puedes aprender a utilizar conda pinchado [aqui](https://juanma17guti.github.io/Conda_env_list/#descripción-general) obtienes una pequeña guia. 

### 📂 Lecturas crudas (FASTQ)  
Datos de secuenciación originales directamente desde el NCBI:  
[Lecturas_Crudas](https://trace.ncbi.nlm.nih.gov/Traces/sra-reads-be/fastq?acc=SRR1552444).  

### 🔢 Conteos genéticos en crudo  
Archivo con los conteos genéticos:  
[Conteos_crudos](https://ftp.ncbi.nlm.nih.gov/geo/series/GSE60nnn/GSE60450/suppl/GSE60450%5FLactation%2DGenewiseCounts%2Etxt%2Egz).  

🚀Descarga los diferentes archivos y habre tu entorno conda. Comenzamos a trabajar🚀 

---

## 2. Calidad 

Antes de poder analizar cualquier resultado tenemos que ver la calidad de las secuencias que hemos obtenido. Para ello utilizamos los siguientes comandos en terminal: 
  1. Utilizamos la herramienta **fastqc**: 
```
fastqc Lecturas_Crudas -o X #X es la Ruta donde quieres que se guarde el resultado
```
  2. Utilizamos la herramienta **TrimGalore**:
```
trim_galore Lecturas_Crudas -o X
```
  3. Volvemos a utilizar **fastqc** después del filtrado con trimgalore y coparamos los resultados.
```
fastqc Lecturas_Crudas_trimed -o X
```

Varios comandos para ver la diferncias entre antes y después: 
  1. Para ver el tamaño de las secuencias, con esto podemomos compara las secuencias que han sido eliminadas: 
```
zgrep '@SRR1552444' Lecturas_crudas | wc -l
zgrep '@SRR1552444' Lecturas_crudas_trimed | wc -l
```
  2. Podemos observar tambien el resultado en los acchivos HTML que genera fastqc. 
```
firefox nombre_del_archivo.html
```



### 🔧 Herramientas: 
- **fastqc:** Una herramienta de bioinformática utilizada para evaluar la calidad de los datos NGS. Su función principal es realizar un análisis de calidad de las lecturas o reads de secuenciación, generando un informe detallado sobre diferentes aspectos, como la calidad base, la distribución de longitudes de las lecturas, la presencia de secuencias adaptadoras, la composición de bases, la diversidad de las secuencias y más. El objetivo es identificar posibles problemas en los datos que puedan afectar el análisis posterior, como la existencia de sesgos en la secuenciación o la presencia de contaminación.(Otros ejemplos: MultiQC, fastp)
- **TrimGalore:** Una herramienta de bioinformática utilizada para el recorte y la calidad de las lecturas de secenciacion de NGS. Su principal función es eliminar lecturas de baja calidad y secuencias adaptadoras de los datos de secuenciación, mejorando así la calidad de las lecturas antes de realizar análisis posteriores como ensamblaje o alineación.

