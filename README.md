# Immersion Suits with Thermal Protection Testing: Analysis, Feasibility, and Implementation Study

**Author: Francisco Broissin - B.Sc. Solid State Physics - Universidad Complutense Madrid, Spain 1986
ALcochete, Portugal - February 2026 

## Overview

This study explores the potential of using an advanced manikin equipped with sensors and an Artificial Intelligence (AI) model for objective performance testing of immersion suits with thermal protection. The goal is to provide a standardized and consistent method for evaluating the effectiveness of such suits, moving beyond subjective assessments.

The project is structured into three main sections:

*   **Section I: Human Body Thermal Comfort Prediction Parameters**
*   **Section II: Test Manikin - Hardware Definition**
*   **Section III: Manikin - Software Design: Artificial Intelligence based Dummy**

All code is provided as open source for transparency, verification, and potential further development.

## Section I: Human Body Thermal Comfort Prediction Parameters

This section focuses on understanding and predicting thermal comfort and temperature descent in the human body during seawater immersion. It includes:

1.  **Input Parameters Definition:** Establishing key physiological and environmental factors (e.g., initial body temperature, seawater temperature, 'clo' value).
2.  **Model for Thermal Comfort and Temperature Descent Estimate:** Development of a computational model incorporating heat transfer principles to simulate temperature changes over time.
3.  **Data Analysis and Key Findings:** Analysis of simulation results for scenarios with and without an immersion suit, highlighting the impact on core body temperature and thermal comfort.
4.  **Comparative Plots for Torso, Hands and Feet:** Visualizing temperature descent differences across various body parts under different insulation conditions.

### Key Findings from Simulations:

*   **Rapid Heat Loss:** Simulations demonstrate rapid and significant heat loss in cold seawater, especially in extremities.
*   **Suit Effectiveness:** An immersion suit (higher 'clo' value) significantly slows core body temperature decline and prolongs thermal comfort and potential survival time.
*   **Vulnerable Extremities:** Even with a suit, extremities like hands and feet remain highly susceptible to rapid cooling, though the suit mitigates the rate of heat loss.

## Section II: Test Manikin - Hardware Definition

This section details the design of a comprehensive dummy (manikin) for experimental measurements, outlining essential parameters, sensor placement strategy, and recommended sensor types with their uncertainties.

1.  **Essential Parameters and Magnitudes to Measure:** Identification of critical temperature (core, skin, suit surfaces, seawater) and heat flux measurements.
2.  **Manikin Design and Sensor Placement Strategy:** A detailed plan for sensor distribution across critical body regions (head, torso, arms, hands, legs, feet) to capture comprehensive thermal data.
3.  **Recommended Sensor Types and Measurement Uncertainty:** Specification of high-precision thermistors, PRTs, thermocouples, and heat flux transducers with their respective desired uncertainties.

## Section III: Manikin - Software Design: Artificial Intelligence Based Dummy

This section describes the development of the AI model that processes manikin sensor data to predict thermal comfort categories.

1.  **Synthetic Dataset for Training a Manikin AI Model:** Creation of a realistic synthetic dataset based on simulation results, augmented with noise to mimic real-world sensor variability.
2.  **Definition and Assignment of Thermal Comfort Categories:** Establishment of distinct thermal comfort categories (e.g., 'Comfortable', 'Slightly Cool', 'Cool', 'Very Cold', 'Hypothermic Risk') with clear temperature thresholds.
3.  **Data Preparation for Machine Learning:** Preprocessing of the synthetic data, including feature scaling (`StandardScaler`) and target encoding (`LabelEncoder`).
4.  **Artificial Intelligence Model Architecture - Building and Training a Multivariate Regression Model (MLP):** Construction, compilation, and training of a Multi-Layer Perceptron (MLP) model using `tensorflow.keras` to predict thermal comfort categories from sensor readings.

### AI Model Performance Evaluation:

*   The MLP model achieved a **Training Accuracy of 99.31%** and a **Test Accuracy of 95.89%**.
*   **Strong Performance in Extreme Categories:** The model showed excellent performance for 'Comfortable' and 'Hypothermic Risk' categories, indicating its effectiveness as an early warning system.
*   **Challenges with Minority Classes:** Performance on intermediate categories ('Cool', 'Slightly Cool', 'Very Cold') was less robust due to limited samples in the synthetic dataset.

### Predictions for Unseen Data: Input Your Real Test Data Here

This notebook provides a functional code block (`10.3 - Predictions for unseen data: Input your real test data here`) where users can input real-world sensor data from an immersion suit test. The trained AI model will then predict the thermal comfort category based on these inputs.

#### How to use the Prediction Tool:

1.  **Run the Notebook:** Execute all cells in the notebook sequentially to ensure the model is trained and all necessary variables are loaded.
2.  **Navigate to Cell 10.3:** Locate the code cell under the heading "III. Part 10.3 - Predictions for unseen data: Input your real test data here".
3.  **Run the Cell:** Execute this code cell.
4.  **Input Sensor Readings:** The cell will prompt you to enter values for each required sensor (temperatures, heat flux) for a single time instance. Follow the on-screen instructions and ranges.
5.  **Get Prediction:** After entering all values, the model will output the predicted thermal comfort category and the probabilities for each category.

## Appendix A & B

*   **Appendix A: Bibliography:** A curated list of academic textbooks on Physics, Thermodynamics, Heat Transfer, and Fluid Mechanics, providing the theoretical foundation for this study.
*   **Appendix B: Software Licence: MIT Licence:** Details the open-source licensing for this project.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
