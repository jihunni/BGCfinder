# BGCfinder : Biosynthetic Gene Cluster detection with Graph Neural Network

BGCfinder detects biosynthetic gene clusters in bacterial genomes using deep learning. BGCfinder takes a fasta file containing protein sequences and convert each of them into a graph. Graph neural network takes the input graphs to detect biosynthetic gene cluster.

- Developer : Jihun Jeung (jihun@gm.gist.ac.kr, jeung4705@gmail.com)
- Github repository : https://github.com/jihunni/BGCfinder
- PyPI project website : https://pypi.org/project/BGCfinder/

Installation requirement:
- PyTorch
- PyTorch Geometric
- Prodigal (https://github.com/hyattpd/Prodigal)

To construct the conda environment,
```bash
$ conda create --name BGCfinder --clone base
$ conda init bash
$ conda activate BGCfinder
$ conda install pytorch cudatoolkit=11.3 -c pytorch
$ conda install pyg -c pyg
$ pip install BGCfinder
```

To download the BGCfinder model and test files,
```bash
$ bgc-download
```

To find the protein-coding gene in bacterial genome (Installation of `Prodigal` is required for this step),
```bash
$ prodigal -f gff -i bacterial_genome_seq.fasta -a bacterial_protein_seq.fasta -o bacterial_genome_seq.gff 
```

To run BGCfinder with a fasta file containing amino acid sequence with CPU (recommended),
```bash
bgcfinder bacterial_genome.fasta -o output_filename.tsv -l log_record.log -d False
```

To run BGCfinder with a fasta file containing amino acid sequence with GPU,
```bash
bgcfinder bacterial_genome.fasta -o output_filename.tsv -l log_record.log -d True
```

The development environment of BGCfinder : 
```
'torch==1.10.0',
'torch-geometric==2.0.2',
'torch-scatter==2.0.9',
'torch-sparse==0.6.12'
```
