# Task 3: Multimodal ML - Housing Price Prediction Using Images + Tabular Data

## Objective
Predict housing prices using both structured (tabular) data and house images, combining a Convolutional Neural Network (CNN) for visual features with a Multi-Layer Perceptron (MLP) for tabular features in a single fused regression model.

## Dataset
Houses Dataset (Ahmed and Moustafa)
Link: https://github.com/emanhamed/Houses-dataset

- 535 houses, each with 4 room images (bathroom, bedroom, frontal, kitchen) and structured attributes (bedrooms, bathrooms, area, zip code, price)
- A standard public benchmark dataset for combined image + tabular housing price prediction, satisfying both the tabular and image data requirements from a single paired source

## Approach
1. **Load Tabular Data** - bedrooms, bathrooms, area, zip code, and price loaded from the dataset's info file
2. **Load and Match Images** - each house's 4 room photos are resized and tiled into a single 128x128 composite image (2x2 montage), giving the CNN one combined visual input per house, matching the original paper's approach
3. **Preprocess Tabular Data** - zip code one-hot encoded, numeric features (bedrooms, bathrooms, area) scaled with MinMaxScaler, target price scaled separately for training stability
4. **Train/Test Split** - 80/20 split applied identically across images, tabular features, and target to keep both modalities aligned
5. **Build CNN Branch** - a small custom 3-block Conv2D -> BatchNorm -> MaxPooling network reduced to a 16-dimensional image embedding (a custom CNN, rather than a pretrained backbone, was used deliberately given the small dataset size)
6. **Build Tabular Branch (MLP)** - a 3-layer dense network reduced to an 8-dimensional tabular embedding
7. **Feature Fusion** - the CNN and MLP embeddings are concatenated and passed through a final dense layer to predict price (late fusion architecture)
8. **Train** - the combined model trained end-to-end for 50 epochs
9. **Evaluate** - predictions inverse-transformed back to real dollar values before computing MAE and RMSE
10. **Baseline Comparison** - a tabular-only Random Forest model trained for comparison against the multimodal model

## Results

| Model | MAE | RMSE |
|---|---|---|
| Tabular-Only (Random Forest) | $137,725.70 | $215,042.73 |
| Multimodal (CNN + MLP) | $159,337.67 | $276,806.02 |

## Key Findings
- The multimodal CNN+MLP model did not outperform the tabular-only Random Forest baseline on this dataset. This runs counter to the intuitive assumption that adding images should always improve accuracy.
- This is explained by the small dataset size (535 houses). CNNs typically require far more training examples to learn generalizable visual features, while Random Forest is well suited to small, structured tabular data and resists overfitting through ensembling.
- Price-relevant information in this dataset appears to already be well captured by structured features like zip code and square footage, meaning the limited image data added noise rather than a useful signal.
- General takeaway for multimodal ML: additional modalities only help when there is sufficient data to learn from them. A honest negative result, correctly diagnosed, is a valid and useful finding.

## Files in This Repo
```
task3-multimodal-housing-price-prediction/
├── task3-multimodal-housing-price-prediction.ipynb
└── README.md
```

## Skills Gained
- Multimodal machine learning
- Convolutional Neural Networks (CNNs)
- Feature fusion (image + tabular)
- Regression modeling and evaluation

---

## Internship Task

**AI/ML Engineering Internship**

**DevelopersHub Corporation**

**Task 5:** Multimodal ML – Housing Price Prediction Using Images + Tabular Data      

---