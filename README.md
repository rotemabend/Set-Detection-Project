Set Card Detection Project
This project focuses on the use of computer vision and deep learning to detect and classify cards from the SET game within a board image. The workflow includes identifying card regions using computer vision techniques and employing convolutional neural networks (CNNs) for accurate classification.

Card Detection
The card detection process utilizes OpenCV and follows these steps:

Edge Detection: Convert the image to an edge map to highlight card boundaries.
Contour Extraction: Extract all contours from the image and filter them based on size, selecting those within a range of the average size * 0.6 to isolate the twelve cards.
Preprocessing: Fill the edges of card images with white pixels to enhance compatibility with CNN input.
Card Classification
For each detected card, the following steps were performed:

1. Color Detection
Using OpenCV, a color mask was applied to detect the predominant color (red, green, or purple) on each card. Pixel counts for each color were measured, and the most frequent color was selected.

2. Number, Shading, and Size Detection
Two separate CNNs were utilized:

CNN 1: Classifies the number of shapes and shape type.
CNN 2: Classifies the shading pattern (solid, striped, or outlined).
CNN Training
The CNNs were trained using a dataset of card images sourced from Kaggle's SET Card dataset. This dataset provided diverse examples that were essential for accurate feature detection and classification.