# Downlaod Ensembl data

Current version of ensembl is 82, ensembl genomes' one is 29.

Ensembl provides rsync service.

Ensembl genomes only provide ftp.

## ensembl

### mysql

```bash
mkdir -p ~/data/ensembl82/mysql
cd ~/data/ensembl82/mysql

rsync -avP \
    --exclude='*_cdna_82*' \
    --exclude='*_vega_82*' \
    --exclude='*_funcgen_82*' \
    --exclude='*_otherfeatures_82*' \
    --exclude='*_variation_82*' \
    --exclude='*_rnaseq_82*' \
    --exclude='ensembl_*' \
    --exclude='*_mart_82' \
    rsync://ftp.ensembl.org/ensembl/pub/release-82/mysql/ \
    .

```

### fasta

```bash
mkdir -p ~/data/ensembl82/fasta
cd ~/data/ensembl82/fasta

rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/saccharomyces_cerevisiae .

rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-75/fasta/homo_sapiens . # GRCh37

rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/nomascus_leucogenys .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/pongo_abelii .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/gorilla_gorilla .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/pan_troglodytes .

rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/tarsius_syrichta .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/callithrix_jacchus .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/papio_anubis .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/chlorocebus_sabaeus .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/macaca_mulatta .

rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/drosophila_melanogaster .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/caenorhabditis_elegans .

rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/rattus_norvegicus .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/mus_musculus .

rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/tupaia_belangeri .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/otolemur_garnettii .
rsync -avP rsync://ftp.ensembl.org/ensembl/pub/release-82/fasta/microcebus_murinus .

```

## plants

### mysql

```bash
mkdir -p ~/data/ensembl82/mysql
cd ~/data/ensembl82/mysql

wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/mysql/arabidopsis_thaliana_core_29_82_10 .
wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/mysql/arabidopsis_lyrata_core_29_82_10 .

wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/mysql/oryza_sativa_core_29_82_7 .
wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/mysql/oryza_indica_core_29_82_2 .

wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/mysql/brassica_oleracea_core_29_82_1 .
wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/mysql/brassica_rapa_core_29_82_1 .

wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/mysql/solanum_lycopersicum_core_29_82_250 .
wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/mysql/solanum_tuberosum_core_29_82_4 .

mv ftp.ensemblgenomes.org/pub/plants/release-29/mysql/* .
rm -fr ftp.ensemblgenomes.org
find . -name ".listing" | xargs rm

# rsync -avP wangq@45.79.80.100:data/ensembl82/mysql/ ~/data/ensembl82/mysql
```

### fasta

```bash
mkdir -p ~/data/ensembl82/fasta
cd ~/data/ensembl82/fasta

wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/fasta/arabidopsis_thaliana .
wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/fasta/arabidopsis_lyrata .

wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/fasta/oryza_sativa .
wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/fasta/oryza_indica .

wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/fasta/brassica_oleracea .
wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/fasta/brassica_rapa .

wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/fasta/solanum_lycopersicum .
wget -m ftp://ftp.ensemblgenomes.org/pub/plants/release-29/fasta/solanum_tuberosum .

mv ftp.ensemblgenomes.org/pub/plants/release-29/fasta/* .
rm -fr ftp.ensemblgenomes.org
find . -name ".listing" | xargs rm

# rsync -avP wangq@45.79.80.100:data/ensembl82/fasta/ ~/data/ensembl82/fasta
```