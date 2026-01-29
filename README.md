# Phys-R1: Physically Grounded Video Reasoning

<p align="center">
    <img src="https://img.shields.io/badge/Task-Video--Reasoning-red" alt="Task">
    <img src="https://img.shields.io/badge/Framework-Decoupled--Simulation-blue" alt="Framework">
    <img src="https://img.shields.io/badge/Method-GRPO--Gaussian-green" alt="Method">
    <img src="https://img.shields.io/badge/Status-ICML--2026-orange" alt="Status">
</p>

**Phys-R1** is a physically grounded reasoning framework that extends Large Multimodal Models (LMMs) beyond "visual intuition." By externalizing latent physical variables (mass, friction, velocity) and aligning them with a physics simulator, Phys-R1 achieves robust, verifiable reasoning in dynamic scenes.

---

## 🚀 News
* **[2026.01]** Phys-R1 paper submitted to ICML 2026.
* **[2026.01]** Release of the Phys-R1 codebase and Gaussian-Kernel GRPO implementation.

---

## 💡 Key Contributions

- **Decoupled Grounder-Verifier Pipeline**: Moves away from end-to-end black-box guessing. The **Grounder** (Policy) proposes structured physical hypotheses, while the **Verifier** (Simulator) provides deterministic feedback.
- **Gaussian-Kernel GRPO**: A novel reinforcement learning objective designed for **continuous physical parameters**, solving the sparse reward problem in complex dynamics.
- **Latent Dynamics Alignment**: A specialized training objective that ensures the model's internal Chain-of-Thought (CoT) matches the actual physical laws of the environment.
- **Structured JSON Reasoning**: Models explicitly output `<json>` blocks containing estimated physical properties, making the reasoning process fully interpretable.

---

## 🛠️ Architecture

![Architecture](https://via.placeholder.com/1000x400?text=Phys-R1+Framework+Diagram:+Grounder+->+JSON+->+Simulator+->+Reward)

1.  **Video Input**: Raw frames of a dynamic scene.
2.  **Reasoning (CoT)**: The model "thinks" about forces, masses, and friction.
3.  **Parameter Extraction**: Outputs a structured JSON (e.g., `{"mass": 0.5, "friction": 0.2}`).
4.  **Verification**: A physics engine (PyBullet/MuJoCo) simulates the hypothesis.
5.  **Alignment**: Feedback loop via Gaussian-Kernel GRPO to refine predictions.

---

## 📦 Installation

```bash
# Clone the repo
git clone [https://github.com/your-username/Phys-R1.git](https://github.com/your-username/Phys-R1.git)
cd Phys-R1

# Create environment
conda create -n physr1 python=3.10
conda activate physr1

# Install dependencies
pip install -r requirements.txt
# Requires a physics backend
pip install pybullet mujoco
