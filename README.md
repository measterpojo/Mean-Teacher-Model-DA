# Mean-Teacher-Model-DA
The Mean Teacher Model is a popular approach for semi-supervised learning, where a student model learns from a more stable teacher model that updates through Exponential Moving Average (EMA). It helps improve consistency between predictions and provides a smoother training signal.

Key Components of the Mean Teacher Model

Student Model: Learns from labeled and unlabeled data.

Teacher Model: A copy of the student that updates with EMA.

Consistency Loss: Encourages the student model to match the teacher’s predictions for unlabeled data.

Exponential Moving Average (EMA) Update: Each parameter in the teacher model is updated using a weighted average of its previous values and the corresponding parameters in the student model:


The PACS dataset is widely used for domain generalization in computer vision. It consists of four domains

Each domain contains seven categories: Dog, Elephant, Giraffe, Guitar, Horse, and Person2. The dataset is designed to test how well models generalize across different visual styles.


![image](https://github.com/user-attachments/assets/f65e6b68-623b-43fa-ba99-444bd9965109)


## Training Results

| Epoch | Supervised Loss | Unsupervised Loss | Domain Loss |
|-------|----------------|-------------------|-------------|
| 1     | 0.4814        | 0.0096            | 1.4051      |
| 2     | 0.4852        | 0.0074            | 1.3584      |
| 3     | 0.5211        | 0.0071            | 1.3781      |
| 4     | 0.4689        | 0.0079            | 1.4157      |
| 5     | 0.5057        | 0.0077            | 1.3789      |
| 6     | 0.4770        | 0.0070            | 1.3851      |
| 7     | 0.4953        | 0.0073            | 1.3895      |
| 8     | 0.4827        | 0.0061            | 1.3978      |
| 9     | 0.4742        | 0.0064            | 1.3708      |
| 10    | 0.4655        | 0.0063            | 1.3764      |

### Observations
- **Supervised Loss:** Remains stable across epochs, suggesting effective labeled learning.
- **Unsupervised Loss:** Very low, indicating the student model aligns well with the teacher.
- **Domain Loss:** Fluctuates slightly but stays within a consistent range, reinforcing domain adaptation.

Consider tweaking hyperparameters like `lambda_dann` or `alpha` if further refinements are needed. 🚀


![image](https://github.com/user-attachments/assets/65c9d092-ca54-4534-a313-1eaf88c177d2)

