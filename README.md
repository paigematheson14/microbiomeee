# microbiomeee


# 1st have to figure out what species are what based on COI data. We have HCO and LCO which are the beginning and ends of the COI gene. but they were all weird and not merging properly so just trying to blast LCO to see if we can identify species based on that one fragment. 

Data is denoised fasta files from Ang's script. First thing I am doing is getting the top hit from each fasta file 


for file in *-LC.denoise.good.fasta; do
  sample=$(basename "$file" -LC.denoise.good.fasta)
  vsearch -derep_fulllength "$file" \
    -sizein -sizeout \
    -topn 1 \
    -output "LC_top1/${sample}.top1.fasta"
done
