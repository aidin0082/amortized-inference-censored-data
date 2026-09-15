# Amortized Neural Inference for Progressively Censored Data

Official TensorFlow/Keras implementation of the paper:  
**"Amortized Neural Inference vs. Classical Estimation: A Benchmark for Progressively Censored Data with Binomial Removals"**

This repository provides a comprehensive benchmarking framework that bridges classical statistical inference (Maximum Likelihood, Expectation-Maximization) and Bayesian MCMC with modern, amortized neural estimators for reliability analysis.

## 📌 Features
* **Classical & Bayesian Baselines:** Full implementation of MLE, EM algorithm, and MCMC sampling for the Reflected Modified Kumaraswamy (RMK) distribution under progressive Type-II censoring.
* **Dual-Track Neural Feature Engineering:** 
  * **Track A:** A novel 17-dimensional position-aware summary statistic vector designed to capture complex censoring topologies (e.g., center of mass, concentration).
  * **Track B:** A raw-padded sequence representation with a binary mask channel.
* **Amortized Estimator Emulators:** Multi-Layer Perceptron (MLP) and Variational Bayesian Neural Network (BNN) architectures for near-instantaneous inference.
* **$\beta$-NLL MC-Dropout:** A custom variance-weighted Monte Carlo Dropout model that resolves the catastrophic variance collapse of standard BNNs, decoupling aleatoric from epistemic uncertainty.

## 🚀 Installation & Requirements
To run the simulations and reproduce the paper's figures, you need Python 3.8+ and the libraries listed in `requirements.txt`.

Clone the repository and install the dependencies via pip:

git clone [https://github.com/yourusername/amortized-inference-censored-data.git](https://github.com/yourusername/amortized-inference-censored-data.git)
cd amortized-inference-censored-data
pip install -r requirements.txt


*(Note: TensorFlow and TensorFlow Probability are required for the neural network components. If running on a GPU, ensure CUDA is properly configured.)*

## 💻 Usage

The entire pipeline (data generation, model training, Monte Carlo simulation, real-data analysis, and plotting) is unified in a single script. The classic Lieblein & Zelen (1956) ball bearing dataset is included directly within the code.

Simply execute the script or run the Jupyter Notebook:

python main_simulation.py

*(If you are using a Jupyter Notebook, simply "Restart & Run All".)*

**Outputs Generated:**
Upon completion, the script will automatically generate and save all CSV data tables and publication-quality figures (`fig1` to `fig4`) directly to your working directory.

## 📝 Citation

If you find this code or methodology useful in your research, please cite our paper:

@article{rahimidorabad2026amortized,
  title={Classical vs. Data-Driven Estimation: A Comparative Study for Progressively Censored Data with Binomial Removals},
  author={Rahimi Dorabad, Aydin and Karami, Amirhossein and Kohansal, Akram},
  journal={Communications in Statistics - Simulation and Computation},
  year={2026},
  publisher={Taylor & Francis}
}
