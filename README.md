# Atomic_Sentences

TO ADD LARGE FILES INTO GITHUB: 

brew install git-lfs
git lfs install
git lfs track "data/yourfile.csv"
git add .gitattributes data/yourfile.csv
git commit -m "Track large CSV with Git LFS"
git push origin main
