# Ideal-Sampling
# Aim:
To demonstrate the process of ideal sampling, where a continuous sinusoidal signal is sampled at a sufficient rate and accurately reconstructed without loss of information.

# Tools required:

Python

NumPy

Matplotlib

SciPy

# Program:
```
#Impulse Sampling
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
```
# Output Waveform:
![image](https://github.com/user-attachments/assets/3368ab08-9ba8-46ee-b435-c1fedc6fba05)
![image](https://github.com/user-attachments/assets/62bbba07-2eb9-475c-b5d0-0270400d7dc0)
![image](https://github.com/user-attachments/assets/7a96c772-e1d8-4660-bfa3-66046aea60a5)



# Results:

The original continuous sine wave was successfully sampled at 100 Hz. The sampled signal was plotted using discrete red markers. The signal was reconstructed using resampling techniques, closely matching the original signal.

