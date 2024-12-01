# Tutorial de utilização da pipeline BACTOPIA para montagem de contigs de bactérias
Link do github da pipeline: https://github.com/bactopia/bactopia

# Instalação:
# 1) Criação do ambiente conda:
### Recomendado - utilizar micromamba
mamba create -n bactopia -c conda-forge -c bioconda bactopia

### Utilizando conda
conda create -n bactopia -c conda-forge -c bioconda bactopia

# 2) Ativando o ambiente:
conda activate bactopia

# 3) Acessando os datasets:
bactopia datasets

--------------------------------
# Execução:
### Paired-end
bactopia --R1 R1.fastq.gz --R2 R2.fastq.gz --sample SAMPLE_NAME \
         --datasets datasets/ --outdir OUTDIR

### Single-End
bactopia --SE SAMPLE.fastq.gz --sample SAMPLE --datasets datasets/ --outdir OUTDIR

### Multiple Samples
bactopia prepare MY-FASTQS/ > fastqs.txt
bactopia --fastqs fastqs.txt --datasets datasets --outdir OUTDIR

### Single ENA/SRA Experiment
bactopia --accession SRX000000 --datasets datasets --outdir OUTDIR

### Multiple ENA/SRA Experiments
bactopia search "staphylococcus aureus" > accessions.txt
bactopia --accessions accessions.txt --dataset datasets --outdir ${OUTDIR}

--------------------------------
# Análise de dados

