# BoxingActionClassification

This detailed document outlines the design, methodology, and evaluation of the Boxing Psychological State Tracking System, a comprehensive project utilizing advanced machine learning and visualization techniques to assess boxers' mental and physical conditions. Below is a refined summary of the key aspects:

### **Boxing Psychological State Tracking System Overview**
This system evaluates the intersection of mental and physical states during boxing matches, leveraging injuries, knockdowns, and actions as indicators of performance. It integrates cutting-edge technologies like YOLOv8n for action detection, SHAP for model explainability, and an intuitive visualization interface for users.

---

### **Methodology**
1. **Action Classification Model Building**
   - **Model Selection:** YOLOv8n was chosen for its efficiency in handling multiple-object detection and its adaptability for fine-tuned boxing action classification.
   - **Tuning Parameters:** Network depth, number of epochs, and class definitions were optimized for task-specific accuracy.

2. **SHAP for Explainability**
   - Identifies regions in images contributing most to classification.
   - Assigns SHAP values to improve model transparency and user trust.

3. **Visualization Interface**
   - Displays analyzed data, including momentum shifts and psychological indicators, with model predictions.
   - Helps athletes and coaches identify significant mental state changes and their impact.

---

### **Dataset Preparation**
1. **Data Collection**
   - Boxing videos from diverse sources were annotated using **LabelImg**.
   - Critical moments like punches, knockdowns, and cuts were labeled for training.

2. **Labels Defined:**
   | ID   | Object/Action               | Label                              |
   |------|-----------------------------|------------------------------------|
   | 0-1  | Boxers                      | boxer1/boxer2                     |
   | 2-3  | Successful Straight Punch   | successfulstraightpunchboxer1/2   |
   | 4-5  | Unsuccessful Straight Punch | unsuccessfulstraightpunchboxer1/2 |
   | 6-7  | Successful Hook             | successfulhookboxer1/2            |
   | 8-9  | Unsuccessful Hook           | unsuccessfulhookboxer1/2          |
   | 10-11| Cuts                        | boxer1cut/boxer2cut               |
   | 12-13| Knockdowns                  | boxer1knockdown/boxer2knockdown   |

   - Frames were flipped, resized, normalized, and redundant data was discarded.

---

### **Evaluation Metrics**
1. **Model Outputs:**
   - **Confusion Matrix:** Measures classification accuracy; certain classes (e.g., boxer1, boxer2) show high accuracy, while others (e.g., hook types) demonstrate mild confusion.
   - **Precision-Recall Curves:** Highlights trade-offs between precision and recall.
   - **F1 Scores:** Average F1 score indicates robust classification performance for most actions, though challenges persist for complex labels like "unsuccessful hook."

2. **Training Performance:**
   - Metrics like decreasing loss, increasing precision, and recall trends signify effective learning and prediction improvements.

---

### **User Experience**
- **Interactive Features:**
  - Upload boxing videos/photos for real-time analysis.
  - Visualize fight metrics such as confidence shifts post-actions (e.g., knockdowns).
  - SHAP insights for psychometric analysis, aiding model developers in refining predictive logic.

- **Practical Benefits:**
  - Identifies pivotal moments and mental state changes in matches.
  - Equips coaches and athletes with actionable insights for performance enhancement.

---

This system showcases how integrating machine learning and visualization can redefine sports analytics by emphasizing mental and physical interplay, providing a pathway for advanced research and application in boxing. Let me know if you'd like further refinement or additional features!
