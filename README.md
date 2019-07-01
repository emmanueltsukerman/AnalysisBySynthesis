# Towards the first adversarially robust neural network model on MNIST

The ABS model is a robust (w.r.t. Adversarial Examples) classifier on MNIST. For more details checkout our paper "Towards the first adversarially robust neural network model on MNIST
https://arxiv.org/abs/1805.09190 [1]. 

This code provides the pre-trained ABS models and baselines such as:
a vanilla CNN, a binary CNN, a Nearest Neighbour classifier, the model of Madry et al. [2] and our Analysis by Synthesis (**ABS**) model. 

A random selection of adversarial examples for the different models can be seen below. 

<p align="center">
      <img src="exp/imgs/qualitative.png" alt="dist advs"/><br/>
      <em> Smallest adversarial examples for different architectures. </em>
</p>



To generate adversarial examples and run the code agnostic of the deeplearning framework (e.g. tensorflow, torch), we use foolbox [3]. 
Foolbox support decision-, score- and gradient-based attacks. For gradient-based attacks, the gradients can either be calculated directly or estimated with the model scores and finite difference based methods. 
Additionally some model specific attacks (LatentDescent) are provided. 

Lastly we also compute distal (also called trash) adversarial examples which are unrecognizabale images which are classified with high confidence.  

<p align="center">
      <img src="exp/imgs/distal_adversarials.png" alt="dist advs"/><br/>
      <em> Distal adversarials which are classiefied as "1" with >90% certainty. </em>
</p>



 
[1] Lukas Schott, Jonas Rauber, Matthias Bethge, and Wieland Brendel. Towards the first adversarially robust neural network model on mnist. International Conference for Learning Representations 2019, 2019. URL https://arxiv.org/abs/1805.09190


[2] Aleksander Madry, Aleksandar Makelov, Ludwig Schmidt, Dimitris Tsipras, and Adrian Vladu. Towards deep
learning models resistant to adversarial attacks. In _International Conference on Learning Representations_, 2018. URL https://openreview.net/forum?id=rJzIBfZ

[3] Jonas Rauber and Wieland Brendel. Foolbox Documentation. Read the Docs, 2018. URL https://media.readthedocs.org/pdf/foolbox/latest/foolbox.pdf 
