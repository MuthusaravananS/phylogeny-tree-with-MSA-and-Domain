# phylogeny-tree-with-MSA-and-Domain

## steps to create phylogenytree with domain informationa and MSA 

The script will generate and display the phylogeny tree, with MSA and domain distribution labels assigned to the tree leaves.

user can visualize the following files in a single figure:

    a multiple sequence alignment (MSA)
    a gene/protein tree in newick format
    a protein domain annotation in Pfam_scan output format

The inputs above can be combined freely, e.g. you may provide any combination such as

    tree + MSA + domains
    tree + MSA
    tree + domains
    MSA + domains or ... 
    
#Requirements

 requires Python2.7 or Python3.4 or higher and the following Python packages:

    ete3
```
pip install 'ete3==3.0.0b35'
```
    Biopython
```
pip install biopython
```
It is absolutely crucial that you're using ete3 version 3.0.0b35 and not the latest version.

#Input files 

Create .aln file using MUSCLE v3.8.1551 by Robert C. Edgar http://www.drive5.com/muscle
Create .nwk file using any phylogeny tree methods or tools, we recommend Neighbour joining tree from Mega software, https://www.megasoftware.net
create .pfam using pfam_scan-1.6-4 using attached pfam_scan.pl script as follows, 
```
./pfam_scan.pl -fasta /home/muthu/anaconda3/share/pfam_scan-1.6-4/*****.fasta -dir /home/muthu/PfamScan/ -outfile *****.pfam
```
save all files in same folder with main python script and in terminal excute the file as follows,
```
python Phylotree-v1.py -m candidate.aln -t candidate.nwk -d clear_candidate.pfam -s 0.8
```

# To install dependencies 

### Download and install MUSCLE v3.8.1551
Install MUSCLE v3.8.1551 on your system. You can download it from the official website or use package managers like Homebrew (for macOS) or apt-get (for Linux).
Prepare a file (let's say sequences.fasta) containing the GH sequences in FASTA format.
Open your terminal or command prompt and navigate to the directory containing the sequences.fasta file.
#### Execute the following command to run MUSCLE and align the sequences:

```
muscle -in sequences.fasta -out aligned_sequences.fasta

```
MUSCLE will generate the aligned sequences and save them in the aligned_sequences.fasta file.

### Download and install pfam_scan-1.6-4 

Download and install pfam_scan-1.6-4 from the Pfam website (https://pfam.xfam.org/tools).

### Download Mega software
official site for download, 
 https://www.megasoftware.net
 
Look for the Linux version of MEGA software and download the appropriate package based on your system architecture (32-bit or 64-bit).

Once the download is complete, open your terminal and navigate to the directory where the downloaded package is located.

Extract the contents of the package using the following command:

```
tar -xf MEGA-X-Linux.tar.gz

```
Replace MEGA-X-Linux.tar.gz with the actual name of the downloaded file.

Change into the extracted directory:
```
cd MEGAX

```
To start the installation, run the following command:
```
sudo ./install.sh

```

Follow the prompts provided by the installation script to complete the installation process. By default, the script will install MEGA in the /usr/local/MEGAX directory.

Once the installation is complete, you should be able to run MEGA software on your Linux system. You can launch it by searching for "MEGA" in your applications menu or by running the following command in the terminal:
```
/usr/local/MEGAX/megax
```
Please note that the installation steps may vary slightly depending on the specific version and package of MEGA software you are using. It's always a good idea to refer to the documentation provided with the downloaded package for any specific instructions or additional dependencies required.

