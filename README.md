# KETI_ar


# Preparing Datasets
## Data preprocessing
Root set up on main2.py
* Image root line 16 ```root = '/syn_mnt/dataset/keti_ssl/0930_data/'.``` 
* Attribute set up root line 27 ```data = np.loadtxt("/syn_mnt/dataset/keti_ssl/0930_data/meta_info/relation_key.csv", dtype=str, delimiter=',')```
* Save file root line 60 ```mpimg.imsave(os.path.join('/syn_mnt/jyj/KETI_demo/cropped0930',f[:-4]+'_'+str(i)+'.jpg'),cropped_img)```
* Save pickle file line 94 ```with open('keti_dataset_0930.pkl', 'wb') as f:```
   
``` sh
$ python main2.py
```
## Training & Evaluation
To train the model
Specify root
* Cropped image: Line 195 ```imagepath = '/share_home/slurmjyj/KETI_demo/cropped0930/'```
* Pickel path : Line 186 ```picklepath = 'keti_dataset_0930.pkl'```
* Save model of best mA: Line 305 ```torch.save(model.state_dict(), 'best_mA.pth')``` 
``` sh
$ python train_KETI.py
```


To evaluate the performance on a validation set
* Cropped image: Line 90 ``` imagepath = '/share_home/slurmjyj/KETI_demo/cropped0930/' ```
* Pickle path: Line 91 ``` picklepath = 'keti_dataset_0930.pkl' ```
``` sh
$python infer_KETI.py
```
