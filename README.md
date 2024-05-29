pacbio_smrttools: jiangyanyu/pacbio_smrttoolsv13:1.0
docker environment: ubuntu 22.04, smrttools v13.0 

pbfusion: jiangyanyu/pacbio_pbfusion40.4.0:1.0
1. get into docker
docker run --rm -it jiangyan/pacbio_pbfusionv0.4.0:1.0
2. pbfusion
pbfusion gff-cache --gtf gencode.v39.annotation.gtf --gtf-out gencode.v39.annotation.gtf.bin
pbfusion discover --gtf gencode.v39.annotation.gtf.bin --output-prefix isoseq --threads 8 852-1.bam
3.visualize
python3 visualize_fusion.py -o fusion_browser_shot.png -a gencode.v39.annotation.gtf -f isoseq.breakpoints.groups.bed -b 852-1.bam

TALON: computing very expensive!!! (step 2: pull TALON: docker pull jiangyanyu/talonv4:1.0 docker environment: python3.6)
However, TALON can be used to merge multiple samples to generate integrated PB IDs. (https://github.com/Magdoll/cDNA_Cupcake/wiki/Handling-multiple-samples:-Creating-a-master-transcriptome)


   
