# Convolutional Autoencoder Designs for Anomaly Detection

Each branch of this repo contains an implementation of a one-class anomoly detector using different autoencoder designs.

###Branch Directory
* **Basic_AE_MSE:** Basic autoencoder with MSE loss
* **Basic_AE_SSIM:** Basic autoencoder with SSIM loss
* **Beta-VAE:** Variational autoencoder with Beta parameter
* **DAE:** Denoising autoencoder
* **VAE:** Variational autoencoder

Each autoencoder uses the same CNN structure. The encoder side is shown below:

[insert picture]

The 'main' branch of this repo contains the final report on the findings. 

## Objective

Explore how different designs perform on varied, sparse datasets to ultimately find the best generalized autoencoder design. 

## The Datasets

Each of the following datasets used contained 15-20 images, presenting unique challenges for training.

**Roofing Screws:**
[insert normal image] 
*Caption: Example of a nominal image* [insert anomalous image] *Caption: Example of an anomalous image*

**Pasta: ***
[insert normal image] 
*Caption: Example of a nominal image* [insert anomalous image] *Caption: Example of an anomalous image*

**Capsules:**
[insert normal image] 
*Caption: Example of a nominal image* [insert anomalous image] *Caption: Example of an anomalous image*

## Testing and Results

*The testing philosphy employed was to try to be as systematic as possible given time constraints, with the ultimate goal of comparing each design variation. 
*Averaging across 3 starting seeds for weight init was used to evaluate results. 
*An AUROC score using SSIM loss was used to evaluate the effectiveness of the models.

*This stage would have been way more thorough if we had incorporated hyperparam tuning aids such as 'Optuna' and 'scikit-learn'.*

### Testing Process
1. **Determine a decent CNN:** Evaluated different CNNs and their varying attributes. The primary goal at this stage was to find a 'good enough' model to serve as a foundation for testing the autoencoders. 
2. **Determine a decent reconstruction loss:** Limited comparison to MSE vs SSIM.
3. **Parameter Tuning:** Tested different parameters for the base models and any autoencoder specific parameters (ex: beta values, noise factor)
4. **Autoencoder Comparison:** Compared best results of each optimized autoencoder against the others.

### Results
[insert  denoising reconstruction]
*Caption: AUROC score* [insert beta variation reconstruction]
*Caption: AUROC score*

Pictured above are the reconstruction from the two best performing models and their corresponding AUROC scores.

*Please see the 'Project Report' PDF in the main branch for a more comprehensive breakdown of the results.*

## Areas to Improve

If this project was continued, future testing would include: 
* Changing evaluation metric (exploring outside of AUROC)
* Experimenting and improving more on the CNN design
* Conducting a more comprehensive hyperparamter check (using hyperparam tuning aids)
* Attempting different forms of weight initialization

## Conclusion

Ultimately, it is hard to find a single design that works generally well for every dataset and every anomaly, especially with sparse training examples. It was most interesting to see in practice how different models performed better at certain dataset problems. This reaffirms the **"No Free Lunch" theorem**, which states that no single algorithm is universally superior.  

## Authors

Alanna Cunha

Tara Golonka