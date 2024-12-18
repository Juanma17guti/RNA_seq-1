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

Antes de poder analizar cualquier resultado tenemos que ver la calidad de las secuencias que hemos obtenido. Para ello utilizamos los isguientes comandos en terminal: 
  1. Utilizamos la herramienta **fastqc**: 


