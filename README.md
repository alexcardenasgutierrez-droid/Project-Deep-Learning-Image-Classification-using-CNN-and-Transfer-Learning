# Deep Learning Image Classification using CNN and Transfer Learning

**Project Description:** A computer vision project comparing the performance of a custom-built Convolutional Neural Network (CNN) against state-of-the-art pre-trained transfer learning models for image classification.

## Dataset Description
The project utilizes the widely recognized **CIFAR-10** dataset.
* **Total Images:** 60,000 color images.
* **Image Dimensions:** 32x32 pixels.
* **Classes:** 10 distinct categories (e.g., airplanes, cars, birds, cats), perfectly balanced with 6,000 images per class.

## Research Goal
The objective was to understand the trade-offs in deep learning model development by first building and optimizing a CNN architecture from scratch, and then comparing its classification performance against established, pre-trained transfer learning models.

## Steps Taken



1. **Baseline Custom CNN:** Built a simple foundational architecture (`Conv2D` → `MaxPooling` → `Dense`).
2. **Regularization:** Implemented `BatchNormalization` and `Dropout` layers to prevent overfitting.
3. **Deeper Architecture:** Scaled the model by adding multiple convolutional layers (increasing filter size from 32 to 64).
4. **Data Augmentation:** Applied transformations like rotation, flipping, zooming, and shifting via `ImageDataGenerator` to artificially expand the training dataset and improve model robustness.
5. **Optimization & Callbacks:** Utilized patience-based Early Stopping with best-weight restoration to halt training at peak validation performance.
6. **Transfer Learning & Fine-Tuning:** 
   Adapted several pre-trained models for our specific dataset. For each model, we initially froze the base architecture to leverage the pre-trained weights, and then selectively unfroze the top 20% of the layers to fine-tune the network specifically for our 10-class classification task. The models tested include:
   * MobileNetV2
   * EfficientNetV2B0
   * NASNetMobile
   * DenseNet121
7. **Experiment Tracking:** Integrated **Weights & Biases (W&B)** for full experiment logging, metric tracking, and model artifact saving.

## Main Findings
By systematically scaling from a baseline CNN to complex transfer learning networks, we were able to benchmark the accuracy, computational cost, and convergence speed of each approach.

All model metrics, training curves, and hyperparameter experiments were actively tracked and logged using Weights & Biases. 
* 🔗 **View the full interactive project dashboard here:** [W&B CIFAR-10 FantasticFour Project](https://wandb.ai/Ironhack_cnn_project/cifar10_dataset_FantasticFour)

## Next Steps / Ideas for Improvement
* **Implement a VGG-Style Architecture:** Build a custom CNN from scratch inspired by the VGG19 architecture. By stacking multiple 3x3 convolutional layers with increasing depth before pooling, we can test if this deeper, classic architectural pattern improves feature extraction on the CIFAR-10 dataset compared to our simpler baseline CNN.
* **Model Interpretability (Grad-CAM):** Implement Gradient-weighted Class Activation Mapping (Grad-CAM) to visualize exactly which pixels the models are focusing on when making their predictions, helping to open the "black box" of our network.
* **Advanced Hyperparameter Tuning:** Utilize tools like Keras Tuner or Optuna to systematically search for the absolute optimal learning rates, dropout rates, and batch sizes across all our models.

## Repo Structure
| Folder/File | Description |
| :--- | :--- |
| **`Notebooks/`** | Contains the core Jupyter Notebooks for model training: `Baseline.ipynb`, `EfficientNetV2.ipynb`, and `MobileNetV2.ipynb`. |
| **`project_presentation.pdf`** | The slide deck used to present our methodology, architecture choices, and findings in class. |

## Authors
Built collaboratively by me [@alexcardenasgutierrez-droid](https://github.com/alexcardenasgutierrez-droid) together with [@suzanacracco-max](https://github.com/suzanacracco-max), [@echerif18](https://github.com/echerif18) and [@aitor-vergaramartin](https://github.com/aitor-vergaramartin) the Ironhack bootcamp of Data Science & Machine Learning.
