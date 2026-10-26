# Assignment No. 2
## AI-Based Mini Application Development: Integrating ML/DL Models into Android with TensorFlow Lite

**Question No. 1:** [CLO-02, PLO-03, P4, Rubrics → {Coding, Outcome}, Points (10)]

### Objective
The objective of this assignment is to help students understand an existing GitHub repository, explore its implementation, and develop a small AI-based Android application. The work combines a **comprehensive study** and a **hands-on implementation** of integrating Machine Learning (ML) and Deep Learning (DL) models into an Android application using **TensorFlow Lite (TFLite)**, delivered as a single cohesive solution.

### Assignment Description
Students are required to begin by cloning the provided GitHub repository and understanding its structure, source code, dependencies, and working mechanism. After understanding the repository, students must develop a small AI-based mini application of their own choice, using the repository as a starting point or reference.

Students are free to select any application idea, domain, or use case, provided that the project incorporates AI functionality (on-device inference with TensorFlow Lite) and remains within the scope of a mini assignment. The implementation should be simple, functional, thoroughly commented, and clearly documented.

**Provided GitHub repository:**
[https://github.com/Uzair390-Del/NumberGuessingAppTflite.git](https://github.com/Uzair390-Del/NumberGuessingAppTflite.git)

---

### Part A: Conceptual Study
The report must address the following conceptual aspects.

#### A1. Embedding ML/DL Models in Android Applications
- Explain what it means to embed an ML/DL model in an Android application.
- Discuss its importance in real-world mobile applications such as **image recognition, text classification, and prediction systems**.
- Highlight the **benefits** (for example low latency, offline use, privacy, reduced server cost) and the **challenges** (for example limited memory, battery, and compute, model size, device variability) of on-device ML inference.

#### A2. TensorFlow Lite (TFLite)
- Give a detailed explanation of TensorFlow Lite, including its **definition**.
- Compare TFLite with **standard TensorFlow**.
- Justify using TFLite in Android applications in terms of **performance, model size, and efficiency**.

#### A3. Step-by-Step Process of Using TFLite in Android
Explain the complete process, covering:
1. Converting a TensorFlow model into `.tflite` format.
2. Adding the model and the required dependencies in Android Studio.
3. Understanding the role of the **TFLite Interpreter**.
4. Preparing input data.
5. Running inference.
6. Interpreting the output results.

---

### Part B: Practical Implementation

### Task 1: Clone and Understand the GitHub Repository
1. Open the GitHub repository link provided above.
2. Clone the repository to your local system using Git https://github.com/Uzair390-Del/NumberGuessingAppTflite.git.
3. Explore the repository structure, source code, dependencies, and README file.
4. Open and **execute** the project in Android Studio.
5. Understand how the existing project works and identify the relevant components that can support your mini application.
6. Document your understanding of the repository and explain how it relates to your proposed AI-based application.

### Task 2: Analyze the Real-World Android TFLite Application
Analyze the cloned project and explain:
- **How the model is loaded** (model file location, interpreter initialization).
- **How predictions are generated** (running inference with the Interpreter).
- **How input and output are handled** (data preparation, buffers, shapes, and types).
- **How results are displayed** in the user interface.
- **Thoroughly comment the code** to demonstrate a clear understanding of ML integration in Android.

### Task 3: Develop an AI-Based Mini Application
1. Select an AI-based application idea of your own choice.
2. Design and implement a small, functional application using suitable tools, libraries, frameworks, or AI models (with TensorFlow Lite for on-device inference).
3. Use the provided repository as a starting point or reference, where applicable.
4. Explain the application's purpose, features, workflow, and implementation.
5. Test the application and provide evidence of its functionality through screenshots or other relevant results.

---

### Required Submissions
Students must submit **two separate assignments covering the same mini-project**.

#### Submission 1: Theory Report — Assignment No. 2
The theory report (PDF) must include the following sections:

1. Title page with assignment number, project title, student name, roll number, course, and submission date.
2. Introduction and objectives of the project.
3. Embedding ML/DL models in Android: meaning, importance in real-world applications, benefits, and challenges of on-device inference.
4. TensorFlow Lite: definition, comparison with standard TensorFlow, and justification for Android (performance, model size, efficiency).
5. Step-by-step process of using TFLite in Android (model conversion to `.tflite`, adding the model and dependencies, TFLite Interpreter, input preparation, inference, output interpretation).
6. Overview and purpose of the provided GitHub repository.
7. Repository cloning procedure and explanation of its structure.
8. Analysis of the repository: model loading, prediction generation, input/output handling, and result display in the UI.
9. Proposed AI-based application and its objectives.
10. Technologies, tools, libraries, and AI models used.
11. System design, workflow, and implementation methodology.
12. Explanation of the application's main features and functionality.
13. Testing, results, screenshots, and discussion.
14. Conclusion and references, including the original GitHub repository link.

#### Submission 2: Practical Report — Implementation and Code
The practical submission must contain the complete implementation and supporting technical documentation, including:

1. The GitHub repository link used for the assignment.
2. Evidence of cloning the repository and understanding its structure.
3. The complete source code of the developed AI-based mini application, **thoroughly commented**.
4. Relevant code snippets in a properly formatted PDF document, with brief explanations.
5. A complete project repository containing the necessary code files, configuration files, and other required resources.
6. A **zipped Android Studio project** containing the working application.
7. A README file explaining the project, prerequisites, installation, dependencies, and execution instructions.
8. Screenshots demonstrating the application's execution and output.
9. A practical report in PDF format explaining the implementation and how to run the application.

### Deliverables (as per Question No. 1)
- A **PDF report** covering the conceptual explanation and implementation analysis.
- A **zipped Android Studio project** containing the working application.

### Submission Guidelines
- Both submissions must cover the same AI-based mini-project.
- The theory report must be submitted separately under the title **Assignment No. 2**.
- The practical submission must include the complete GitHub repository, code snippets PDF, implementation report PDF, and the zipped Android Studio project.
- Students may choose any AI application idea, but the project must remain small, practical, and suitable for a mini assignment.
- All code must be properly organized and commented, and students must understand and be able to explain their implementation.
- Clearly acknowledge the original GitHub repository, external libraries, datasets, AI models, and other resources used.
- Students must ensure that their repository and submitted files are accessible and complete.

### Expected Learning Outcomes
Upon completion of this assignment, students should be able to:
- Explain what it means to embed ML/DL models in Android and discuss the benefits and challenges of on-device inference.
- Explain TensorFlow Lite and justify its use over standard TensorFlow on mobile devices.
- Convert a TensorFlow model to `.tflite` and integrate it into an Android Studio project.
- Use the TFLite Interpreter to prepare input, run inference, and interpret output.
- Clone, execute, and understand an existing GitHub repository and analyze its structure and source code.
- Design and develop a basic AI-based Android application.
- Document technical work through theory and practical reports.
- Manage and present source code using GitHub and supporting documentation.

### Final Deliverables Checklist
- [ ] Theory Report — Assignment No. 2 (PDF), including conceptual explanation and implementation analysis
- [ ] Practical Implementation Report (PDF)
- [ ] Code Snippets and Explanation (PDF)
- [ ] Complete GitHub Repository Link
- [ ] Complete, thoroughly commented Source Code and README
- [ ] Zipped Android Studio Project (working application)
- [ ] Application Screenshots and Testing Evidence