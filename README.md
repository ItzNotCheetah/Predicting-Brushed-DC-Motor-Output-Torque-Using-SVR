# Robotics Motor Torque Prediction using SVR

## 📌 Project Overview
Accurate torque estimation is critical in robotics for motion control, load detection, and fault prevention.  
This project uses **Support Vector Regression (SVR) with a Radial Basis Function (RBF) kernel** to predict the output torque of a robotic motor from electrical, mechanical, and thermal sensor data.

The model captures **nonlinear relationships** between motor current, speed, temperature, and torque that are not well represented by linear regression models.

---

## ⚙️ Motor Model Description
The dataset represents a **brushed DC motor** commonly used in:
- Mobile robots
- Small robotic arms
- Educational and competition robotics platforms

Torque generation follows standard DC motor physics:

\[
\tau = K_t \cdot I
\]

Nonlinear effects included in the model:
- Back-EMF at high rotational speeds
- Temperature-dependent resistance
- Measurement and sensor noise

---

## 📊 Dataset
The dataset used in this project is **physics-informed synthetic data**, generated using standard DC motor equations and realistic operating ranges.  
This approach is commonly used in robotics research when physical hardware access is limited.

### Features
| Feature | Description |
|------|------------|
| `motor_current_A` | Motor current (A) |
| `motor_speed_rpm` | Motor rotational speed (RPM) |
| `motor_temperature_C` | Motor temperature (°C) |
| `motor_voltage_V` | Supply voltage (V) |
| `torque_Nm` | Output torque (Nm) — **target variable** |

---

## 🎯 Prediction Target
- **Motor Output Torque (Nm)**

---

## 🤖 Model
- **Algorithm:** Support Vector Regression (SVR)
- **Kernel:** Radial Basis Function (RBF)

### Why SVR with RBF?
- Motor behavior is **nonlinear** due to back-EMF and thermal effects
- SVR performs well on **medium-sized, noisy sensor datasets**
- RBF kernel captures complex feature interactions without overfitting

---

## 📈 Visualization
The primary visualization plots **motor current vs output torque**:

- Red points: Measured torque values
- Blue curve: SVR-predicted torque

Motor current was selected as the main feature for visualization because torque is physically proportional to current, while nonlinear effects introduce deviations captured by the RBF kernel.

---

## 🚀 Results
The SVR model produces a smooth nonlinear torque curve that:
- Accurately follows the physical torque–current relationship
- Accounts for speed and temperature effects
- Outperforms linear regression on nonlinear regions

---

## 🔧 Technologies Used
- Python
- NumPy
- Pandas
- Matplotlib
- scikit-learn

---

## 📌 Future Improvements
- Compare SVR performance with linear regression and random forest models
- Extend the model to predict motor efficiency or power consumption
- Apply the approach to real-world motor sensor data
- Integrate torque prediction into a closed-loop control simulation

