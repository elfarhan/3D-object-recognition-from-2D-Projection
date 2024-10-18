# MLHO: 3D Object Recognition from 2D Projection

## Overview

MLHO is a project that investigates whether it's possible to recognize 3D objects from their 2D projections (shadows). The idea is inspired by the video ["The average area of a shadow"](https://www.youtube.com/watch?v=ltLUadnCyi0) by 3Blue1Brown. This project explores multiple synthetic shapes and uses machine learning models, including logistic regression and convolutional neural networks (CNNs), to classify objects based on their shadows.

## Contributors 
- Liam Farhan (Formaly Mohamad Al Farhan)
- Emil Reiter
- Mahmoud Sharaf

## Project Structure

### Data Generation and Preprocessing

- **3D Shapes**: We generated 3D meshes for several shapes, including:
  - Cube
  - Pyramid
  - Tetrahedron
  - Diamond
  - Dodecahedron
  - Icosahedron
  - Torus
  - Cylinder
  - Cow
  - Human

- **Projection**: We used perspective projection to create shadows. In this projection method, the light source is replaced by a viewer, and the objects are projected onto a screen.
- For each object we generate hundereds of shadow images by choosing a random orientation and porjecting the object onto the screen.

- **Preprocessing**: 
  - Edge detection was applied by comparing pixel values to identify object boundaries and generate images containing only the edges. 
  - Data was compressed and cast into boolean values. To handle memory limitations, all images were resized to 200x200.

### Machine Learning Models

#### 1. **Multinomial Logistic Regression**
   - **Training**: The model was trained with L2 regularization.
   - **Accuracy**: Achieved a classification accuracy of approximately 60%, which improved slightly (to 62%) when using edge-detected data.

#### 2. **Deep Neural Networks (DNNs)**
   - **Performance**: The model performed better on full shapes than edge-detected data. Using dropout regularization, a learning rate of `0.00001`, and Adam optimizer, the best results were achieved with a batch size of 40.

#### 3. **Convolutional Neural Networks (CNNs)**
   - CNN architectures, such as VGG and LeNet, were used with varying configurations. 
   - **Results**: 
     - Highest accuracy of 97.58% was achieved using a Conv-Conv-Pool architecture.
     - CNNs proved to be superior to DNNs for this task.


## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/mlho.git
