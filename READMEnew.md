# KETI_ar

## Requirements
``` sh
pip install -r requirements.txt
```

## Data preprocessing
Root set up on preprocess_main_new.ipynb
First Block
* data_root 16 ```root = '/share_home/toolkit/datasets/ketivg/'.``` 
* v```
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
