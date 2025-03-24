# Ideal-Sampling
AIM :
To construct and reconstruct an ideal sampling system using Python with the help of NumPy and SciPy, demonstrating the process of sampling a continuous-time signal and reconstructing it using interpolation techniques.

TOOLS REQUIRED :
1.Python – Programming language for implementing sampling and reconstruction.
2.NumPy – For numerical operations, including signal generation and discrete processing.
3.SciPy – For signal processing functions like interpolation and filtering.
4.Matplotlib – For visualizing the sampled and reconstructed signals.
5.Google Colab (Optional) – Cloud-based Python environment for running code without local setup.

PROGRAM :
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample
fs = 100
t = np.arange(0, 1, 1/fs) 
f = 5
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
reconstructed_signal = resample(signal_sampled, len(t))
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

OUTPUT WAVEFORM :
![image](https://github.com/user-attachments/assets/2e422796-e7ce-4de6-90cd-f43fe4771548)
![image](https://github.com/user-attachments/assets/ff948147-6d4b-4d41-ad1b-d32b1ef6dc6b)
![image](https://github.com/user-attachments/assets/99a3bb84-f780-47db-8fa6-1e7e94ef1832)

RESULT :
Therefore, the construction and reconstruction of ideal sampling using python was successfully verified using python.
