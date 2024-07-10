# K-Means Clustering for Image Compression

## Overview
This project demonstrates the application of K-Means clustering to compress the colors of a photographic image. Using a photograph of tulips, we explore the impact of applying K-Means clustering to image compression, illustrating how different values of k affect the resultant image.

## Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Introduction
Image compression is a crucial technique in various fields, such as computer vision and graphics. This project uses the K-Means clustering algorithm to reduce the number of colors in an image, thereby compressing it. By examining how the algorithm clusters the pixel colors, we gain a deeper understanding of the K-Means process and its impact on the data.

## Installation
To run this project locally, follow these steps:

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/k-means-image-compression.git
    ```

2. Navigate to the project directory:
    ```sh
    cd k-means-image-compression
    ```

3. Install the required dependencies:
    ```sh
    pip install -r requirements.txt
    ```

## Usage
1. Load and preprocess the image:
    ```python
    import matplotlib.pyplot as plt
    img = plt.imread('tulips.jpg')
    ```

2. Apply K-Means clustering to compress the image and visualize the results. For example:
    ```python
    from sklearn.cluster import KMeans
    import numpy as np

    def cluster_image(k, img):
        img_flat = img.reshape(img.shape[0] * img.shape[1], 3)
        kmeans = KMeans(n_clusters=k, random_state=42).fit(img_flat)
        new_img = img_flat.copy()
        for i in np.unique(kmeans.labels_):
            new_img[kmeans.labels_ == i, :] = kmeans.cluster_centers_[i]
        new_img = new_img.reshape(img.shape)
        plt.imshow(new_img)
        plt.axis('off')
        plt.show()

    cluster_image(3, img)
    ```

3. Experiment with different values of k to see how the number of clusters influences the resultant image.

## Results
Through this project, we have applied the K-Means algorithm to compress the colors of a photographic image. By examining how the algorithm clusters the pixel colors, we've gained a deeper understanding of the K-Means process and its impact on the data. We explored the effects of setting different values for k, ranging from 2 to 10, and observed how the number of clusters influences the resultant image.

## Contributing
Contributions are welcome! Please read the [contributing guidelines](CONTRIBUTING.md) first. You can submit issues or fork the project and create a pull request.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
- **Name**: Michael Yisa
- **LinkedIn**: [Michael Yisa](https://www.linkedin.com/in/michael-yisa-382a9b249)

Feel free to explore the project, raise issues, and contribute!

