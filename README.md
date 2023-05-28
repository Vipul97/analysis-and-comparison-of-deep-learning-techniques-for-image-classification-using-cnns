# Analysis and Comparison of Deep Learning Techniques for Image Classification using CNNs

## Abstract
Deep learning techniques have been developed to address specific challenges related to image classification. However, selecting the optimal implementation of these techniques for a specific task can be challenging. To better understand CNN’s, we investigate the effects that hyper-parameters have on a model. We primarily examine three aspects of CNN’s: the layer architecture, optimizer, and data augmentation. In particular, different combinations of hyper-parameters are tested, and the accuracy of the models are compared. For convenience, the CIFAR-10 data set is used to train the model, and for efficiency, Ray Tune is used to test different combinations of hyper-parameters.

**View the report [here](https://github.com/Vipul97/analysis-and-comparison-of-deep-learning-techniques-for-image-classification-using-cnns/blob/main/deliverables/analysis_and_comparison_of_deep_learning_techniques_for_image_classification_using_cnns.pdf).**

## Data Source
The dataset is available at https://www.cs.toronto.edu/~kriz/cifar.html.

## Results
We chose a relatively simple baseline architecture in order to focus on the impacts of hyper-parameter adjustments. Our original architecture consisted of three convolutional layers, with 16, then 32, then 64 channels. We used batch normalization and max pooling after each one. The kernel sizes were 3x3, 3x3, and 6x6 with pad sizes of 2, 1, and 1. After these convolutional layer we had one fully connected layer with 10 nodes, each one signifying a separate category. We used stochastic gradient descent with Nesterov momentum as the optimizer. We used no data augmentation with this model. After optimizing the parameters, our final model’s convolutional layers had channel sizes of 32, 64, and 128. Our kernel sizes were 3, 5, and 7 with padding sizes of 2, 3, and 3. The final model also had an additional hidden fully connected layer with 1024 nodes between the final convolutional layer and the 10 node layer. We maintained stochastic gradient descent with momentum, however learning rate and momentum parameters were modified. Our final model performed best using CIFAR-10 Auto-Augmentation. Our hyper-parameter adjustments and data modification were able to bring the over test accuracy from 65.1% to 74.3% while keeping the same overall architecture.

|        Metric       | Pre-tuned |  With Best Hyper-parameters   | Best Optimizer | Best Augmentation | Final Model | 
| -------------------:| :-------: | :---------------------------: | :------------: | :---------------: | :---------: |
| Validation Accuracy |   71.57%  |             75.28%            |     77.07%     |       78.23%      |  **78.23%** |
|       Test Accuracy |   65.07%  |             70.13%            |     73.72%     |       74.34%      |  **74.34%** |

## Contributors
<table>
  <tr>
    <td align="center"><a href="https://github.com/EZeng1259"><img src="https://avatars.githubusercontent.com/u/59375083?v=4" width="100px;" alt=""/><br /><sub><b>Eric Zeng</b></sub></a><br /></td>
    <td align="center"><a href="https://github.com/patrickhickeyj"><img src="https://avatars.githubusercontent.com/u/119631395?v=4" width="100px;" alt=""/><br /><sub><b>Patrick Hickey</b></sub></a><br /></td>
    <td align="center"><a href="https://github.com/Vipul97"><img src="https://avatars.githubusercontent.com/u/16150834?v=4" width="100px;" alt=""/><br /><sub><b>Vipul Gharde</b></sub></a><br /></td>
    <td align="center"><a href="https://github.com/yf245"><img src="https://avatars.githubusercontent.com/u/95952523?v=4" width="100px;" alt=""/><br /><sub><b>Yating Fang</b></sub></a><br /></td>
  </tr>
</table>
