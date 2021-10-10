# GRU-LPR

Code for paper [SC-LPR: Spatiotemporal Context based on LiDAR Place Recognition]. The paper is under review in Neurocomputing 2021. 


Pipeline overview.


## Requirements
We recommend python3.6. You can install required dependencies by:
```bash
pip install -r requirements.txt
```

## Training

### Data structure

The data structure is:

```bash
data
    |---00
    |    |---000000.json   
    |    |---000001.json
    |    |---...
    |
    |---01
    |    |---000000.json
    |    |---000001.json
    |    |---...
    |
    |---...
    |
    |---00.txt
    |---01.txt
    |---...


### Configuration file

Before training the model, you need to modify the configuration file in ./config according to your needs. The main parameters are as follows:
- graph_pairs_dir: the root dir of your dataset.
- batch_size: batch size, 256 in our paper.
- p_thresh: distance threshold for positive samples, e.g., 3m. If the distance between two samples is less than p_thresh meters, they will be treated as positive samples. The distance threshold for negative samples is set to 20 meters by default. Note that your training sample pairs should not contain samples with a distance greater than p_thresh meters and less than 20 meters.

## Acknowledgement

Thanks to the source code of some great works such as [SG-PR](https://github.com/kxhit/SG_PR), [DGCNN](https://github.com/WangYueFt/dgcnn).
