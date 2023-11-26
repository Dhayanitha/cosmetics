### COSMETIC COMPARISON 
The world of cosmetics can be a daunting place, especially for individuals with sensitive skin who are all too familiar with the potential perils of selecting the wrong product. Deciphering the ingredient lists can be akin to unraveling a complex code, particularly for those without a background in chemistry.

T-SNE, plays a pivotal role in establishing ingredient similarity, enabling the system to categorize products based on their underlying composition. Bokeh is employed, offering an intuitive and visually engaging way to explore the world of cosmetics

In the process, we construct a cosmetic comparison model that bridges the chasm between the enigmatic world of cosmetic ingredients and the everyday consumer, transforming the shopping experience into an informed and empowering journey.

### Hardware Requirements
The hardware requirements for the implementation of the proposed cosmetic product comparison system from handwritten images are outlined below:

High-Performance Workstation:
A workstation with a multicore processor (e.g., Intel Core i7 or AMD Ryzen 7) for parallel processing.

Graphics Processing Unit (GPU):
A dedicated GPU (e.g., NVIDIA GeForce RTX series) for accelerated computations, especially for deep learning tasks.
Memory (RAM):

Minimum 16GB of RAM to handle the computational demands of OCR and image processing tasks.
Storage:
Adequate storage space (preferably SSD) to accommodate large datasets and model files.

High-Resolution Display:
A high-resolution 5 for detailed image analysis and visualization.

### Software Requirements
The software requirements for the successful deployment of the cosmetic product comparison system are as follows:

Operating System:
A 64-bit operating system, such as Windows 10 or Ubuntu, for compatibility with modern deep learning frameworks.

Development Environment:
Python programming language (version 3.6 or later) for coding the OCR
system.

Machine Learning Frameworks:
Installation of machine learning frameworks, including KNN and t-SNE, to leverage pre-trained models and facilitate model training.

Sklearn Libraries:
Integration of sklearn libraries, such as TSNE, to incorporate reduction techniques for high dimensional data visualization.

### PROJECT ARCHITECTURE
![Minimalist Colorful Organizational Structure List Graph](https://github.com/Dhayanitha/cosmetics/assets/75235032/213bae21-faa6-41d7-9831-8debe197db40)

### PROGRAM
### IMPORTING DATA
```
# Import libraries
import pandas as pd
from sklearn.manifold import TSNE
import numpy as np
# Load the data
df = pd.read_csv("cosmetics.csv")
# Check the first five rows
display(df.sample(5))
# Inspect the types of products
df.Label.value_counts()
```
### TOKENIZATION
```
# Initialize dictionary, list, and initial index
ingredient_idx = {}
corpus = []
idx = 0
# For loop for tokenization
for i in range(len(moisturizers_dry)):
ingredients = moisturizers_dry['Ingredients'][i]
ingredients_lower = ingredients.lower()
tokens = ingredients_lower.split(', ')
corpus.append(tokens)
for ingredient in tokens:                                               
if ingredient not in ingredient_idx:
ingredient_idx[ingredient] = idx
idx += 1
# Check the result
print("The index for decyl oleate is", ingredient_idx['decyl oleate'])
```
### T-SNE REDUCTION
```
# Dimension reduction with t-SNE
model = TSNE(n_components = 2, learning_rate = 200, random_state = 42)
tsne_features = model.fit_transform(A)
# Make X, Y columns
moisturizers_dry['X'] = tsne_features[:,0]
moisturizers_dry['Y'] = tsne_features[:,1]
```
### OUTPUT
![tsne](https://github.com/Dhayanitha/cosmetics/assets/75235032/f890fb33-9f09-44ca-987e-977176657fc0)
![plot](https://github.com/Dhayanitha/cosmetics/assets/75235032/725d4558-1744-4e96-93e6-a3da787a278a)

### RESULT
In essence, this project bridges the chasm between the enigmatic world of cosmetic ingredients and the everyday consumer, transforming the shopping experience into an informed and empowering journey. By leveraging data science, it not only demystifies product choices but also minimizes the risks associated with skin sensitivities, ultimately revolutionizing the way we shop for cosmetics.
