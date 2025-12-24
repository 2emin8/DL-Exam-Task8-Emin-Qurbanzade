Task 8: Food Classification (5 Types)
Student: Emin Qurbanzade ID: S205 Seed: 20240205 Presentation

Dataset

Name: Food-101 (Selected Subset)

Classes: 5 (Pizza, Sushi, Ice Cream, French Fries, Tacos)

Training samples: 3,750 (750 images per class)

Test samples: 1,250 (250 images per class)

Model Architecture

Type: ResNet18 (Pre-trained on ImageNet)

Status: Frozen backbone (Feature Extraction)

Modified layers: Final Fully Connected (FC) layer replaced

Output: 5 classes (Linear layer: 512 → 5)

Training Comparison

Version 1

Optimizer: Adam

Learning rate: 0.0001

Batch size: 32

Test accuracy: 89.45%

Version 2 (Best)

Optimizer: SGD (with momentum=0.9)

Learning rate: 0.001

Batch size: 32

Test accuracy: 90.32%

Best Result

Best version: Version 2

Final test accuracy: 90.32%

Target accuracy: 85.0%

Status: ✓ Achieved

Analysis

Best performing class: Ice Cream (Distinct colors and shapes made it easy for the model to identify).

Worst performing class: Pizza (Occasionally confused with Tacos due to similar dough texture and melted cheese visual features).

Key observations: Version 2 (SGD) performed better with 90.32% accuracy because the momentum-based optimization allowed it to generalize better on the Food-101 dataset, achieving a more stable and higher final accuracy compared to Version 1 (Adam) which reached its peak earlier but with slightly lower precision. This demonstrates that for feature extraction tasks, SGD with momentum can often find a better global minimum than Adam.

Files

notebook.ipynb: Complete implementation with both training versions

results/training_comparison.png: Comparison plot of Version 1 vs Version 2

results/confusion_matrix.png: 5x5 confusion matrix from the best model (Version 2)

results/predictions.png: 10 sample predictions (Image, True label, Pred label)
