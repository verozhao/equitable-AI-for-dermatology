
# Equitable AI For Dermatology Team SPF

### **👥 Team Members**

| Name | GitHub Handle | Contribution |
| ----- | ----- | ----- |
| Brianna Anaya  | @Briannanaya | Worked with EfficientNet CNN, Date Exploration and Data Augmentation|
| Veronica Zhao | @verozhao | Worked with Ensembled MobileNetV2, EfficientNetB0, and DenseNet121 |
| Shahed Ahmed | @Shahed4 | Worked with Sequential, EfficientNetB0, InceptionV3, and MobileNetV2 |
| Maame Abena | @abenaoboateng | Worked with EfficientNet CNN & Expanded Data Augmentation |
| Samin Chowdhury | @rafsamins | Worked with EfficientNetB0, MobileNetV2, and InceptionV3 |
| Khadija Dial | @Kdial17 | Worked with the Sequential & Inceptionv3 model |

---

## **🎯 Project Highlights**

* Built a InceptionV3 using transfer learning, data augmentation, and fine-tuning techniques to solve the Kaggle Skin Condition classification competition.
* Achieved an F1 score of 54% and a ranking of 23/74 teams on the final Kaggle Leaderboard
* Used SHAP to interpret model decisions
* Implemented apdatitive data adaptation to optimize results within compute constraints

🔗 [Equitable AI for Dermatology | Kaggle Competition Page](https://www.kaggle.com/competitions/bttai-ajl-2025/overview)



## **👩🏽‍💻 Setup & Execution**

**Provide step-by-step instructions so someone else can run your code and reproduce your results. Depending on your setup, include:**

* How to clone the repository
Start by cloning the repository to your local machine: bash Copy Edit
> git clone https://github.com/Shahed4/AJL-Team-SPF
> cd AJL-Team-SPF
* How to install dependencies
The project requires several dependencies, which are listed in the requirements.txt file. You can install them using pip:
> pip install -r requirements.txt
* How to set up the environment
It's recommended to create a virtual environment to manage dependencies. Here’s how you can set it up:

1) Create a virtual environment:
> python -m venv venv
2) Activate the virtual environment: 
- On Windows:
> .\venv\Scripts\activate
- On macOS/Linux:
> source venv/bin/activate
* How to access the dataset(s)
The dataset used in this project is provided through the Kaggle competition [BTTAI AJL 2025](https://www.kaggle.com/competitions/bttai-ajl-2025/overview)
* How to run the notebook or scripts
The project includes a Python notebook that you can run to execute the code:
Open the notebook (e.g., model_training.ipynb) in Jupyter or any compatible notebook interface.
Execute the cells to train the model or perform other tasks.


## **🏗️ Project Overview**

* This project is part of a Kaggle competition sponsored by Break Through Tech and the Algorithmic Justice League, aiming to build more inclusive AI models in dermatology. The competition involves Break Through Tech AI Fellows from various programs, including Virtual, MIT, and UCLA, with mentorship from data science and AI TAs.
* The primary goal of this competition is to develop a machine learning model capable of classifying 21 different skin conditions across diverse skin tones. Given the historical underrepresentation of darker skin tones in dermatology AI datasets, this project seeks to address bias and improve model performance across all demographics. The competition evaluates submissions based on a weighted average F1 score.
* AI-driven diagnostic tools are increasingly used in healthcare, yet biases in training data can lead to disparities in diagnosis and treatment. By developing an inclusive dermatology AI model, this project contributes to reducing healthcare inequities, ensuring better diagnostic accuracy for historically marginalized communities. Our work aligns with ongoing research at institutions such as Stanford and MIT Media Lab, promoting fairness and explainability in AI models.

---

## **📊 Data Exploration**

**Dataset description**

* The competition dataset consists of dermatological images labeled with 21 different skin conditions. It includes metadata such as skin tone distribution and lesion types. To enhance model performance and fairness, we may incorporate external datasets and employ augmentation techniques.

**Data Exploration & Preprocessing Approaches**
- **Handling Class Imbalance:** Given the known imbalance in skin tone representation, we utilize data augmentation techniques such as flipping, rotation, and brightness adjustments to ensure fair representation across all skin tones.
- **Transfer Learning:** We fine-tune pre-trained convolutional neural networks (CNNs) to adapt them to our classification task, optimizing performance while reducing computational costs.
- **Fairness and Explainability:** Using AI fairness tools like Fairlearn, we analyze model biases and adjust our preprocessing pipeline accordingly.

**Challenges**

##### Class Imbalance  
- The dataset has an uneven distribution of skin tones, with lighter skin tones being overrepresented.  
- Certain skin conditions appear less frequently, making it difficult for the model to learn their patterns effectively.  

##### Variability in Image Quality  
- Images vary in resolution, lighting, and focus, which can affect model performance.  
- Some images may have noise that obscure skin conditions.  

##### Bias and Fairness Concerns  
- Existing dermatology AI models have historically struggled with darker skin tones due to biased training data.  
- Need to ensure that the model performs equitably across all demographic groups.  


### EDA Visualizations
**Class Distribution:** A bar chart displaying the frequency of each skin condition in the dataset, highlighting any class imbalances.
<img width="1019" alt="image" src="https://github.com/user-attachments/assets/122c5c4f-1394-4beb-a522-9988e0e914c3" />

**Skin Tone Representation:** A pie chart or histogram illustrating the distribution of skin tones across the dataset, revealing potential biases (1-lightest skin, 6-darkest skin).
   <img width="718" alt="image" src="https://github.com/user-attachments/assets/6a7fcd90-4c0d-4776-a69d-1e9e4f3be146" />
**Sample Image Augmentation:** A grid showcasing examples of augmented images, demonstrating transformations used to balance the dataset.
<img width="793" alt="image" src="https://github.com/user-attachments/assets/fa835906-78f5-493b-bed5-a4905525d84b" />

---

## **🚀 Next Steps & Future Improvements**

* One limiation of our model is its computational complexity. While InceptionV3 is highly efficient in extracting multi-scale features,
  it has a deep and wide architecture with multiple branches, making it computationally expensive. This can lead to a higher risk of overfitting especiallly of the dataset is small.
  Additionally, compared to simpler architectures like ResNet or MobileNet, InceptionV3 can be harder to fine-tune, as freezing/unfreezing layers affects multiple convolutional branches.
* With more time and resources, we would like to: increase the dataset size by collecting more high-quality images, explore transfer learning by use a pretrained InceptionV3 model and fine-tune the later layers, and lastly experiment with regularization and use more GPPU/CPU power for faster training time.

## **🧠 Model Development**

Models Used

We experimented with multiple deep learning architectures to achieve optimal performance:

EfficientNetB0: A lightweight and highly efficient convolutional neural network that balances performance and computational cost.

Sequential Model: A custom-built CNN model designed for interpretability and baseline comparison.

InceptionV3: A powerful architecture optimized for image classification tasks, leveraging factorized convolutions and auxiliary classifiers.

Ensembled MobileNetV2 & DenseNet121: A hybrid approach combining MobileNetV2 (for efficiency) and DenseNet121 (for feature reuse and deep representations) to improve classification accuracy.

Feature Selection & Hyperparameter Tuning Strategies

Feature Selection:

Used principal component analysis (PCA) and feature maps from pre-trained models to extract meaningful representations.

Applied data augmentation techniques (rotation, flipping, brightness adjustment) to enhance model generalization.

Hyperparameter Tuning:

Learning Rate Optimization: Experimented with values in the range of 1e-5 to 1e-3 using the ReduceLROnPlateau scheduler.

Batch Size: Evaluated batch sizes of 16, 32, and 64 to balance memory efficiency and convergence speed.

Dropout & Regularization: Applied dropout rates between 0.2 and 0.5 to prevent overfitting.

Optimizer Selection: Compared Adam, RMSprop, and SGD with momentum to find the best optimizer for each model.

Training Setup

Data Split:

80% Training, 10% Validation, 10% Test to ensure a robust evaluation pipeline.

Evaluation Metric:

Accuracy, Precision, Recall, F1-score to assess classification performance.


## **📈 Results & Key Findings**


* Performance metrics (e.g., Kaggle Leaderboard score, F1-score)
Kaggle Leaderboard score: 23/74
F-1 Score: 54%
Model Performance: 
Confusion Matrix
![image](https://github.com/user-attachments/assets/d9cba501-5a57-4dcc-943e-8e46a28a8a28)


## **🖼️ Impact Narrative**
**Addressing Model Fairness:**
- To ensure fairness in the model, several steps were taken to account for dataset imbalances and mitigate biases related to skin tones:
Data Augmentation for Underrepresented Groups:
- Since the dataset contained fewer images of darker skin tones (Fitzpatrick scales 4, 5, and 6), data augmentation techniques were applied to increase representation
- These techniques included rotation, flipping, zooming, brightness adjustments, and contrast changes to artificially expand the dataset while preserving the key features of skin conditions.
- This aimed to create a more balanced dataset, ensuring the model learns from diverse skin tones rather than being biased towards overrepresented lighter tones.

**Exploratory Data Analysis (EDA) to Identify Biases:**
- The dataset was analyzed to determine the distribution of skin tones and medical conditions, highlighting any existing imbalances.
- The visualization of the Fitzpatrick scale distribution helped to confirm the underrepresentation of darker skin tones.
- The model’s performance was later monitored across different skin tones to assess whether classification accuracy varied significantly between lighter and darker skin types.

**Handling Class Imbalance for Skin Conditions:**
-Some skin conditions, such as seborrheic keratosis and basal-cell carcinoma-morpheiform, were underrepresented in the dataset.
- Additional images of these conditions were synthetically generated or given more weight in training through oversampling techniques to prevent the model from being biased toward more common conditions.

**Validation Set Performance Assessment:**
- A validation set was used to evaluate how well the model performed across different Fitzpatrick skin types and ensure it was not disproportionately misclassifying darker skin tones.
- Performance metrics such as precision, recall, and F1-score were monitored separately for each skin type to identify disparities in prediction accuracy.


**Ethical Considerations & Bias Mitigation Strategies:**
- The dataset was examined for any inherent biases that could lead to skewed predictions.
- Bias detection methods were explored to ensure that misclassifications were not disproportionately affecting any particular demographic.
- If disparities were detected, model fine-tuning was implemented, including adjusting loss functions and using fairness-aware algorithms.

**Broader Impact of This Work:**
This project has significant implications for healthcare equity, AI fairness, and dermatological diagnostics:

**Improving Diagnostic Accuracy Across Skin Tones:**
- Historically, dermatology datasets have been heavily biased towards lighter skin tones, leading to misdiagnosis and delayed treatment for patients with darker skin.
- By ensuring the model performs well across all Fitzpatrick scales, this work contributes to reducing racial disparities in dermatological AI systems.

**Enhancing Accessibility to AI-Powered Skin Condition Detection:**
- If integrated into real-world clinical settings or mobile health applications, this model could help bridge gaps in access to dermatological care, particularly for underserved communities.
- Individuals who may not have immediate access to dermatologists could benefit from AI-driven preliminary assessments, leading to earlier intervention and improved health outcomes.
