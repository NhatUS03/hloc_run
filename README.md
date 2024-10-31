# Sript để chạy các pipeline cho mô hình hloc
**NOTE: Đảm bảo đang ở root Hierachical-Localization**
## Dữ liệu test 
### Tải dữ liệu và setup môi trường
- Setup môi trường:
```
pip install -r requirements.txt
```
- Tải dữ liệu SfM
```
mkdir datasets/South-Building
wget https://cvg-data.inf.ethz.ch/local-feature-evaluation-schoenberger2017/South-Building.zip -P "datasets/South-Building"
unzip -q datasets/South-Building.zip -d "datasets/South-Building/"
```
- Tải dữ liệu Aachen 
```
mkdir datasets/aachen

# Image
wget "https://data.ciirc.cvut.cz/public/projects/2020VisualLocalization/Aachen-Day-Night/images/database_and_query_images.zip"  -P "datasets/aachen"
unzip -q "datasets/aachen/database_and_query_images.zip" -d "datasets/aachen"

# 3D-models
wget "https://data.ciirc.cvut.cz/public/projects/2020VisualLocalization/Aachen-Day-Night/3D-models/aachen_cvpr2018_db.nvm"  -P "datasets/aachen"
wget "https://data.ciirc.cvut.cz/public/projects/2020VisualLocalization/Aachen-Day-Night/aachen.db"  -P "datasets/aachen"
```
- Tải dữ liệu InLoc 

```
# Datasets 
mkdir datasets/inloc

# DUC1
wget "https://data.ciirc.cvut.cz/public/projects/2020VisualLocalization/InLoc/cutouts/DUC1.zip" -P "datasets/inloc"
unzip -q "datasets/inloc/DUC1.zip" -d "datasets/inloc"

# DUC2
wget "https://data.ciirc.cvut.cz/public/projects/2020VisualLocalization/InLoc/cutouts/DUC2.zip" -P "datasets/inloc"
unzip -q "datasets/inloc/DUC2.zip" -d "datasets/inloc"
```
### Chạy mô hình 
```
# SfM 
python3 pipeline_SfM.py 

# Aachen
python3 pipeline_Aachen.py

# InLoc
python3 pipeline_InLoc.py
```
### Copy kết quả
```
scp -r username@remote_host:outputs /path/to/local/destination (. if you want to copy to current directory)
``` 
### Xoá dữ liệu (nếu cần)
```
rm -rf datasets/South-Building
rm -rf datasets/aachen
rm -rf datasets/inloc
```
## Dữ liệu thực tế
### Tải dữ liệu và setup môi trường
### Chạy mô hình 
### Copy kết quả
### Xoá dữ liệu (nếu cần)



from IPython import get_ipython
ipython = get_ipython()

if '__IPYTHON__' in globals():
    ipython.magic('load_ext autoreload')
    ipython.magic('autoreload 2')
