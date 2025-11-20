# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

__Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

__Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer 

__Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


__Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

__Program__:

```c
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import hilbert

# Parameters
A_c = 28.6  # Carrier amplitude
f_c = 5500  # Carrier frequency in Hz
f_m = 550    # Message frequency in Hz
A_m = 14.3  # Message amplitude
sampling_frequency = 1000  # Sampling frequency in Hz
duration = 1  # Duration of the signal in seconds

# Time axis
t = np.linspace(0, duration, int(sampling_frequency * duration))

# Message Signal
m_t = A_m * np.cos(2 * np.pi * f_m * t)

# Carrier Signal
c_t = A_c * np.cos(2 * np.pi * f_c * t)

# Amplitude Modulation (AM) Signal
s_t = (1 + m_t) * c_t

# AM Demodulation using Hilbert Transform
analytic_signal = hilbert(s_t)
envelope = np.abs(analytic_signal)
demodulated_message = (envelope - A_c) / A_m

# Plotting the Results
plt.figure(figsize=(12, 10))

# Original Message Signal
plt.subplot(4, 1, 1)
plt.plot(t, m_t)
plt.title('Original Message Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

# Carrier Signal
plt.subplot(4, 1, 2)
plt.plot(t, c_t)
plt.title('Carrier Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

# Amplitude Modulated (AM) Signal
plt.subplot(4, 1, 3)
plt.plot(t, s_t)
plt.title('Amplitude Modulated (AM) Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

# Demodulated Signal
plt.subplot(4, 1, 4)
plt.plot(t, demodulated_message)
plt.title('Demodulated Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

plt.tight_layout()
plt.show()

```

 __Output__:

<img width="1189" height="990" alt="download (2)" src="https://github.com/user-attachments/assets/da9ec31b-e6f5-409e-9e83-3171f3a5f973" />



 __Result__:

The message signal, carrier signal, and amplitude modulated (AM) signal will be displayed in separate plots. Thus, AM is implemented using numPy and Matplotlib.
