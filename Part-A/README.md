# cs6910-Assignment2
### Part A: Building and training a CNN model from scratch for classification:


## Training:
Wandb framework is used to track the loss and accuracy metrics of training and validation. Moreover, bayesian sweeps have been performed for various hyper parameter configurations. 
The sweep configuration and default configurations of hyperparameters are specficied as follows:

# configure sweep parameters
sweep_config={
  
  "method": "bayes",
  "metric": {
      "name": "val acc",
      "goal": "maximize"   
    },
  "parameters": {
        "max_epochs": {
            "values": [5,7,9]
        },
        "num_filter":{
            "values":[[64,64,64,64,64],[32,64,128,256,512],[32,32,32,32,32],[512,256,128,64,32]]
        },
        "filter_size":{
            "values":[[3,3,3,3,3],[5,5,5,5,5],[11,9,7,5,3]]  
        },
        "cnn_act_fun":{
            "values":['relu','gelu','mish','silu']
        },
        "data_aug":{
            "values":[True,False]
        },
        "batch_norm": {
            "values": [True,False]
        },
        "dense_act_fun":{
            "values":['relu','gelu','mish','silu']
        },
        "dropout":{
            "values":[0.1,0.2,0.3]
        },
        "dense_size":{
            "values":[128,256,512]
        },
        "mystride":{
            "values":[2,3,5]
        }
    }
}
