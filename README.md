# Privacy-Preserving-Brain-Tumor-Classification-with-FL-and-Diffusion-Based-Synthetic-MRI-Augmentation

Central nervous system malignancies, particularly gliomas, pose significant diagnostic challenges due to their complex morphology and inter-observer variability in MRI interpretation. This study proposes a robust, privacy-preserving federated learning (FL) framework for multi-class brain tumor classification that addresses non-IID data distributions, class imbalance, and limited data availability across institutions. The framework integrates three core innovations: (i) a three-tier FL architecture optimized for IID, extreme non-IID with shared holdout data, and privacy-sensitive synthetic augmentation scenarios; (ii) an advanced preprocessing pipeline featuring adaptive brain region extraction, bilateral filtering, and BONE colormap enhancement; and (iii) diffusion-based generative modeling for anatomically precise, privacy-compliant MRI synthesis, guided by clinically optimized prompt engineering. Using an adapted VGG19 architecture with partial fine-tuning and Grad-CAM interpretability, the system was trained and validated on a 7,023-scan multi-institutional dataset. Results demonstrate state-of-the-art performance, achieving almost 99\% accuracy under IID conditions with data augmentation. Remarkably, under extreme non-IID settings where baseline models failed to converge, the proposed framework attained clinic-ready diagnostic accuracy (nearly 95\%) with merely 5\% globally shared holdout data, representing a paradigm shift in decentralized learning robustness. The proposed approach offers a scalable, interpretable, and regulation-compliant solution for real-world neuro-oncology, bridging the gap between AI research and clinical deployment. 

## **Problem Statement**

Central nervous system malignancies, particularly gliomas, present significant diagnostic challenges due to their complex morphological characteristics and substantial inter-observer variability in MRI interpretation. Conventional centralized learning approaches face limitations in handling distributed medical data across institutions while preserving patient privacy and complying with regulatory constraints. This project introduces a privacy-preserving federated learning (FL) framework for robust multi-class brain tumor classification, specifically designed to address non-IID data distributions, severe class imbalance, and limited data availability across decentralized healthcare entities.

## Proposed Framework

<p align="center">
  <img src="Framework1-iid.pdf" alt="Federated Learning Framework for Brain Tumor Classification">
</p>
<p align="center">
  Architecture of the proposed federated learning framework for brain tumor classification
</p>

The proposed federated learning framework for brain tumor classification is illustrated in the figure above. It presents a comprehensive methodology for distributed model training using MRI scans while maintaining data privacy. The framework incorporates several key components:

1.  **Federated Learning Scenarios**: The system supports three operational modes: (i) conventional IID data partitioning (Case 1), (ii) extreme non-IID distribution with minimal shared holdout data (Case 2), and (iii) privacy-sensitive non-IID setting with synthetic data augmentation (Case 3).

2.  **Standardized Preprocessing**: All participating institutions implement a unified preprocessing pipeline including adaptive brain region extraction, bilateral filtering, and BONE colormap enhancement to ensure data consistency.

3.  **Federated Training Protocols**: The framework extends FedAvg with three specialized variants featuring distinct initialization strategies: ImageNet pretraining (Case 1), domain-specific holdout pretraining (Case 2), and synthetic data pretraining (Case 3).

4.  **Adaptive Model Architecture**: A modified VGG19 architecture with frozen base layers and fine-tuned final convolutional blocks is employed, optimized for tumor classification through either uniform or class-balanced stratified aggregation.

5.  **Privacy-Preserving Synthetic Data**: Diffusion-based generative modeling enables anatomically precise, privacy-compliant MRI synthesis for data augmentation in privacy-sensitive environments.

6.  **Comprehensive Evaluation**: Framework effectiveness is assessed through quantitative metrics (multi-class accuracy, sensitivity/specificity, macro-F1) and qualitative Grad-CAM analyses to verify anatomical relevance and model interpretability.
