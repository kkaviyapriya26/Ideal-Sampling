# Ideal-Sampling
## Aim:
  To demonstrate the sampling and reconstruction of a continuous-time signal using Python.
## Tools required:
- Python IDE (Numpy)
## Program:
~~~~
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
~~~~
## Output Waveform:
![image](https://github.com/user-attachments/assets/7ba19940-e254-4b19-ba9f-e772776e05c0)

![image](https://github.com/user-attachments/assets/82203fd9-28a7-4bfa-95cf-8c085a7ac5ea)

![image](https://github.com/user-attachments/assets/7f4e9b44-f8c7-43e6-a2bd-91c8aaf2889d)

## Results:
The experiment demonstrated accurate signal sampling and reconstruction using sinc interpolation. The reconstructed waveform closely matched the original signal, validating the Nyquist-Shannon Sampling Theorem. Proper sampling ensures that a continuous signal can be perfectly restored from discrete data.
