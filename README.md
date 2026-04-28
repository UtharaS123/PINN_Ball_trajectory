# 🧠 Physics-Informed Neural Network (PINN) for Projectile Motion

This project implements a **Physics-Informed Neural Network (PINN)** using PyTorch to model the trajectory of a ball under gravity.

Unlike traditional neural networks, this model learns not only from **data** but also from **physical laws (ODE constraints)**, making it robust even with noisy observations.

---

## 🚀 Project Overview

We model the motion of a projectile governed by:

$$
h(t) = h_0 + v_0 t - \frac{1}{2} g t^2
$$

Instead of directly fitting this equation, the neural network learns it by:

* Fitting **noisy data points**
* Respecting the **underlying physics (differential equation)**
* Enforcing **initial conditions**

---

## 🧩 Key Features

* 📉 Handles **noisy experimental data**
* ⚖️ Combines:

  * Data Loss
  * Physics (ODE) Loss
  * Initial Condition Loss
* 🔁 Uses **automatic differentiation** for physics constraints
* 📊 Visual comparison with true analytical solution

---

## 🛠️ Tech Stack

* Python
* PyTorch
* NumPy
* Matplotlib

---

## 📂 Project Structure

```
.
├── pinn_projectile.py   # Main implementation
├── README.md           # Project documentation
```

---

## ⚙️ How It Works

### 1. Generate Synthetic Data

* Simulated trajectory with added noise

### 2. Neural Network Model

* Fully connected feedforward network (MLP)
* Uses Tanh activation

### 3. Loss Function

The total loss is a combination of:

* **Data Loss** → Fit noisy observations
* **ODE Loss** → Enforce physics:
  $$
  \frac{dh}{dt} = v_0 - g t
  $$
* **Initial Condition Loss** → Ensure:
  $$
  h(0) = h_0
  $$

---

## 📈 Results

The model successfully learns the trajectory by balancing data and physics:

* 🔴 Noisy data points
* ⚫ True analytical solution
* 🔵 PINN prediction

The PINN closely approximates the true solution despite noise.

---

## ▶️ How to Run

1. Install dependencies:

```bash
pip install torch numpy matplotlib
```

2. Run the script:

```bash
python pinn_projectile.py
```

---

## 💡 Why PINNs?

Physics-Informed Neural Networks are powerful because they:

* Reduce dependence on large datasets
* Incorporate domain knowledge directly into training
* Improve generalisation in scientific problems

---

## 📌 Future Improvements

* Extend to **2D/3D motion**
* Add **air resistance**
* Solve **partial differential equations (PDEs)**
* Apply to real-world sensor data

---

## 🤝 Contributions

Feel free to fork, improve, and submit a pull request!

---

## 📜 License

This project is open-source and available under the MIT License.

---

## ⭐ Acknowledgement

This project was inspired by the YouTube video:

Physics Informed Neural Networks explained for beginners | From scratch implementation and code
by Vizuara

The video provides an intuitive introduction to PINNs and a step-by-step implementation, which helped shape the structure of this project.

🔗 Watch here: [https://www.youtube.com/watch?v=your-link-here](https://www.youtube.com/watch?v=1AyAia_NZhQ&t=1388s)


