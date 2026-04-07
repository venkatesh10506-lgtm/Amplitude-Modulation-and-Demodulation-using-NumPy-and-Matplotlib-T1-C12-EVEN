# Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib-T1-C12-EVEN
Aim:

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries.

Apparatus Required:

Software: Python with NumPy and Matplotlib libraries Hardware: Personal Computer

Theory:

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of the message signal. The general form of an AM signal is:

Algorithm:

Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency.
Generate Time Axis: Create a time vector for the signal duration.
Generate Message Signal: Define the message signal as a cosine wave.
Generate Carrier Signal: Define the carrier signal as a cosine wave.
Modulate Signal: Apply the AM formula to obtain the modulated signal.
Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

PROGRAM :

```
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import hilbert

# Parameters
Ac = 24.2          # Carrier amplitude
Am = 12.1          # Message amplitude
Fc = 446          # Carrier frequency (Hz)
Fm = 892           # Message frequency (Hz)
Fs = 8920         # Sampling frequency (Hz)

# Time axis
t = np.arange(0, 2/Fm, 1/Fs)

# Message signal
m = Am * np.sin(2 * np.pi * Fm * t)

# Carrier signal
c = Ac * np.sin(2 * np.pi * Fc * t)

# AM modulation
am_signal = (Ac + m) * np.sin(2 * np.pi * Fc * t)

# Plotting
plt.figure(figsize=(10, 8))

plt.subplot(4, 1, 1)
plt.plot(t, m)
plt.title("Message Signal")
plt.grid(True)

plt.subplot(4, 1, 2)
plt.plot(t, c)
plt.title("Carrier Signal")
plt.grid(True)

plt.subplot(4, 1, 3)
plt.plot(t, am_signal)
plt.title("AM Modulated Signal")
plt.grid(True)

# AM Demodulation using envelope detector
demodulated_signal = np.abs(hilbert(am_signal)) - Ac

plt.subplot(4, 1, 4)
plt.plot(t, demodulated_signal)
plt.title("Demodulated Signal")
plt.grid(True)

plt.tight_layout()
plt.show()
```

TABULATION : 

![WhatsApp Image 2026-04-07 at 12 37 12 PM](https://github.com/user-attachments/assets/819b5a9f-cdcf-466e-a764-6abff3e039d1)


Output:

![WhatsApp Image 2026-04-07 at 12 37 13 PM](https://github.com/user-attachments/assets/d4b7369e-ff3d-419e-b4c7-fc4716c37d0f)
<img width="758" height="544" alt="Screenshot 2026-04-07 123905" src="https://github.com/user-attachments/assets/fea5db27-51ba-418c-98a4-16d51a61f6fc" />


Result:

![WhatsApp Image 2026-04-07 at 12 37 13 PM (1)](https://github.com/user-attachments/assets/3c0a067e-c261-44f3-bb86-a49b2bd41085)
