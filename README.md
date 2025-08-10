# Vision Guide Chandernagore College

**Vision Guide Chandernagore College** is an AI-powered campus navigation system designed to help users explore and find their way around the Chandernagore College campus. Leveraging deep learning and computer vision, the system uses Convolutional Neural Networks (CNNs) to recognize campus buildings and their orientations from images, providing text-based directions for effective navigation.

---

#### Project Overview

This project is built on a custom, manually annotated image dataset of Chandernagore College. The core model is a ResNet18 CNN, trained from scratch for a multi-output classification task: it simultaneously predicts both the building name (e.g., Administrative, Heritage) and the orientation (Front, Left, Right) from each image.


#### Methodology

- **Dataset:** 366 exclusive, in-house annotated images covering various campus buildings and their facades.
- **Model Architecture:** ResNet18, implemented for multi-output classification and trained completely from scratch—no transfer learning used.
- **Training:** Multiple experiments were run to optimize the model for both building and orientation prediction.


#### Challenges

- **Small & Imbalanced Dataset:** The limited number of images and uneven class distribution caused overfitting and restricted the model’s generalization capabilities.
- **Multi-Output Complexity:** Predicting both building and orientation, especially for subtle facade differences, proved challenging.
- **Transfer Learning Limitations:** Models using pre-trained weights showed unstable results, making training from scratch the preferred approach.


#### Results

- **Building Classification:** Achieved strong accuracy (78–99%) in recognizing buildings.
- **Orientation Classification:** Facade prediction accuracy was moderate (50–70%) and varied across experiments.
- **Best Model:** "Experiment 3" was selected as the final solution for its superior, more consistent results compared to transfer learning-based attempts.


#### Navigation Functionality

A dedicated Python function, `get_navigational_guidance`, generates text-based directions based on the model's predictions of the current building and facade, providing users with actionable, real-time navigation guidance.


#### Future Scope

- **Dataset Expansion:** Gather more images to improve generalization and class balance.
- **Advanced Augmentation:** Use sophisticated data augmentation techniques to enhance model robustness.
- **Edge Deployment:** Optimize the solution for deployment on edge devices (e.g., smartphones) for real-time, on-device navigation.

---

## Repository Structure

**Step 1: Data Preparation**  
- `/make_csv_data_from_all_img_data.ipynb` — Prepare a custom annotated CSV from the campus image folder structure.  
- `/ALL_IMG_DATA.csv` — The annotated CSV of campus images.

**Step 2: Experiments**  
- `/EXPERIMENTS_all_in_1_changable_parameter_2_output.ipynb` — Run model training and evaluation with different hyperparameters and configurations.

**Final Step: Final Model and Navigation**  
- `/final_project_1.ipynb` — Contains the final model, experiment details, and the `get_navigational_guidance` function.

---

## Data Organization & Folder Structure

To use this project with your own image data, organize your Google Drive as follows:

```
Project-College-Campus-Navigation/
└── ALL_IMAGES_DATA/
    ├── admin_front/
    ├── admin_left/
    ├── admin_right/
    ├── chemistry_front/
    ├── chemistry_left/
    ├── chemistry_right/
    ├── gurudeb_front/
    ├── gurudeb_left/
    ├── gurudeb_right/
    ├── heritage_front/
    └── heritage_left/
```

- Each subfolder inside `ALL_IMAGES_DATA` should contain images corresponding to that building and orientation class.
- Folder names must follow the format: `[building]_[orientation]` (e.g., `admin_front`, `chemistry_left`, `heritage_left`, etc.).
- Update the notebook code to mount your Google Drive and refer to this directory path.

<br> 

> [!IMPORTANT]  
> *This structure is necessary for the code and notebooks to correctly generate the CSV annotations and train the model. If you add new classes or orientations, follow the same naming convention.*

> [!CAUTION]   
> You need to also change the mounting code in notebooks accordingly 

---

## Usage & Access

> [!WARNING]    
> The original campus image dataset used for training and evaluation is stored privately in Google Drive and is not publicly accessible due to privacy and institutional policies. This repository contains only the code (Jupyter notebooks and related scripts).


**To use or reproduce this work:**
1. **Clone the repository:**
    ```bash
    git clone https://github.com/deep-works/Project-College-Campus-Navigation.git
    ```
2. **Prepare your data:**  
   Organize your annotated image data as described above in Google Drive and update paths in the notebook as needed.
3. **Install dependencies:**  
   All code is provided in Jupyter Notebook format and designed for Google Colab. See the notebooks for required Python libraries and setup instructions.
4. **Run the model:**  
   Follow the instructions in the notebooks to train or evaluate the ResNet18 classifier using your dataset.
5. **Navigation Guidance:**  
   Use the `get_navigational_guidance` function to obtain directions based on image predictions.


---

## Citation, License & Contact

*If you are a collaborator or researcher seeking access to the original dataset, please contact the project maintainers for information regarding data permissions. Users who utilize this work are requested to cite it appropriately or reference this repository in their project.*

**License:**  
This project is released under the GPL License.

**Contact:**  
For questions or collaboration, please contact [workofficialdeep@gmail.com](mailto:workofficialdeep@gmail.com).
