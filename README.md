# Sub-linear Time Image Search using LSH (Locality Sensitive Hashing)

## Project Overview
This project demonstrates a scalable image search system that performs sub-linear time searches using Locality Sensitive Hashing (LSH). The system is designed to search large image datasets efficiently by leveraging approximate nearest neighbor search, reducing computational costs without significantly sacrificing accuracy.

We utilize a Convolutional Neural Network (CNN) for feature extraction and LSH for fast querying based on cosine similarity.

## Key Features
- **Dataset:** We use the [Tiny-224](https://www.kaggle.com/datasets/hcfighting/tiny224) dataset consisting of 100,000 training images and 10,000 test images. The images belong to 200 different classes and have a resolution of 64x64x3.
- **CNN for Feature Extraction:** A deep learning model is used to extract semantic and contextual features from the images. The CNN transforms the images into meaningful vector representations of 1000 dimensions.
- **Locality Sensitive Hashing (LSH):** 
    - We use cosine similarity to hash the 1000-dimensional vectors into bins for efficient search.
    - The LSH algorithm allows us to trade off some accuracy for speed, making the search process faster without processing the entire dataset.

## Algorithm Workflow
1. **Input Processing:**
    - Images from the dataset are converted into 1000-dimensional vectors using CNN.
2. **LSH Hashing:**
    - The 1000-dimensional vectors are normalized to unit norm.
    - We use LSH to hash these vectors into `k` bins over `L` iterations, resulting in a total of `L * k` bins.
3. **Querying:**
    - A query image is processed through the CNN to generate its feature vector.
    - The LSH algorithm hashes the query vector and performs the similarity search over the relevant bins.

## Results
- The algorithm has shown significant improvements in query time with a minor reduction in accuracy.
- The results are averaged over 5 runs and demonstrate that the approach is suitable for large-scale image datasets.

## Conclusion
This project achieves a scalable and efficient solution for image search using CNN and LSH. By trading off minimal accuracy for speed, it enables sub-linear time searches over large datasets.

## References
- Dataset: [Tiny 224](https://www.kaggle.com/datasets/hcfighting/tiny224)
