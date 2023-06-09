# Tutorial Docking 2 Molekul


## Perangkat lunak yang dibutuhkan 
1. ADFR Tools (Version 1.2) https://ccsb.scripps.edu/adfr/download/1067/
2. Mgl Tools (Version 1.5.7) https://ccsb.scripps.edu/download/262/
3. Windows terminal https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701
4. Avogadro (Version 1.2) https://drive.google.com/file/d/1DzRjlV0pYcBXxgXDfhlkOl55sLogvPEB/view?usp=sharing
5. Chimera https://www.cgl.ucsf.edu/chimera/cgi-bin/secure/chimera-get.py?file=win64/chimera-1.16-win64.exe
6. Marvin Sketch https://drive.google.com/file/d/18WN28mtb_ayVKFc09CgDaI5VBJVdESm9/view?usp=sharing

## Buatkan PATH

Yang harus dimasukaan dalam path ada 2 yaitu:

1. C:\Program Files (x86)\MGLTools-1.5.7,

2. C:\Program Files (x86)\ADFRsuite-1.0\bin and the location folder
## Preparasi Dua Molekul
1. Download Beta Cyclodextrin dan Fluconazole di Pubchem [https://pubchem.ncbi.nlm.nih.gov/compound/beta-CYCLODEXTRIN](https://pubchem.ncbi.nlm.nih.gov/compound/Fluconazole) dan https://pubchem.ncbi.nlm.nih.gov/compound/Amphotericin-b#section=2D-Structure
2. Lakukan optimasi geometri dengan menggunakan Avogadro dengan medan gaya General Amber Force Field (GAFF)
3. Simpan dalam format .pdb. Ubah nama Beta Cyclodextrin sebagai rec.pdb dan fluconazole sebagai lig.pdb
4. Buka file Autodock Tools, preparasi rec.pdb dengan cara Klik File Read Molecules cari protein dengan nama rec.pdb >
Dilakukan penambahan Hidrogen dengan Edit-Add Hidrogen-All > Edit tambahkan muatan gasteiger > Edit-Hidrogen Merge Non Polar > Grid-Macromolecules-Choose > save protein dengan rec.pdbqt
5. Buka file Autodock Tools, preparasi lig.pdb dengan cara Dilakukan penambahan Hidrogen dengan Edit-Add Hidrogen-All >
Edit tambahkan muatan gasteiger > Edit-Hidrogen Merge Non Polar > Ligand-Input-choose > Pilih ligand.pdb > ligand-Toorsion tree-detect root > Klik Ligand-Torsion Tree-Choose Torsions, Klik Done > Klik Ligand-Torsion Tree-Set Number of Torsions Pilih fewest atom, > selanjutnya klik Dismiss >
Klik ligand-output-save as dengan lig.pdbqt

## Perintah di terminal untuk mengetahui Grid Box menggunakan Autogrid (Menggunakan Terminal)
1. Pastikan file prepare_gpf.py sudah ada difolder kerja, file ini bisa didownload menggunakan https://downgit.github.io/#/home dengan cara copy alamat ini https://github.com/purnawanpp/Docking-4ieh/blob/main/prepare_gpf.py ke website tersebut, lalu klik download 
2. `python.exe prepare_gpf.py -l lig.pdbqt -r rec.pdbqt -y`
3. `autogrid4 -p rec.gpf -l rec.glg`

## Simulasi Molecular Docking 
1. Jalankan script berikut di google colab: https://github.com/purnawanpp/dock_2compound/blob/main/Autodock_GPU.ipynb
2. Pilih Runtime > change Runtime Type > pilih GPU > Save
3. Upload semua file yang dipreparasi tadi ke google colab
4. Jalankan google colab
5. Download file final.pdb
6. Download file dengan format lig.dlg

## Catatan
1. Jika hasil dockingnya positif dan menjauhi dari jaraknya tukar mana obat yang menjadi rec.pdb dan lig.pdb pada step 3 pada preparasi molekul
