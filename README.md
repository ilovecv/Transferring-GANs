# Transferring GANs generating images from limited data
# Abstract: 
Transferring the knowledge of pretrained networks to new domains by means of finetuning is a widely used practice for applications based on discriminative models. To the best of our knowledge this practice has not been studied within the context of generative deep networks. Therefore, we study domain adaptation applied to image generation with generative adversarial networks. We evaluate several aspects of domain adaptation, including the impact of target domain size, the relative distance between source and target domain, and the initialization of conditional GANs. Our results show that using knowledge from pretrained networks can shorten the convergence time and can significantly improve the quality of the generated images, especially when the target data is limited. We show that these conclusions can also be drawn for conditional GANs even when the pretrained model was trained without conditioning. Our results also suggest that density may be more important than diversity and a dataset with one or few densely sampled classes may be a better source model than more diverse datasets such as ImageNet or Places.

# Overview 
- [Dependences](#dependences)
- [Installation](#installtion)
- [Instructions](#instructions)
- [Results](#results)
# Dependences 
- **Tensorflow:** the version should be more 1.0(https://www.tensorflow.org/)
- **Dataset:** lsun-bedroom(http://lsun.cs.princeton.edu/2017/) or your dataset 

# Installation 
- Install tensorflow
- opencv 
# Instructions
- Using 'git clone https://github.com/yaxingwang/Transferring-GANs'

    you will get new folder whose name is 'Transferring-GANs' in your current path, then  use 'cd Transferring-GANs' to enter the downloaded new folder
    
- Download [pretrain models](https://drive.google.com/drive/folders/1KYzR-NEwKT1582USX31samfZ3JoJ5ija)

    uncompress downloaded folder to current folder, then you have new folder 'transfer_model'  which contains four folders: 'places', 'imagenet', 'celebA', 'bedroom'.

- Download dataset or use your dataset.
    
    you shoud split your dataset into two items: train and val, and build new folder(such as 'bedroom') inside of 'data'. Finally both of train and val folders is moved into 'bedroom' folder.
    Note: I have shown one example and you could make it with same same form.

- Run 'python transfer_gan.py'

   running code with default setting. The pretrained model can be seleted by changing the parameter 'TARGET_DOMAIN'
 
# Results 
Using pretrained models not only get high performance, but fastly attach convergence. In following figure, we show conditional and unconditional settings.
![unconditional_conditional](https://user-images.githubusercontent.com/16056485/40908899-5d8484be-67e8-11e8-894c-d4b19a54e48c.png)


