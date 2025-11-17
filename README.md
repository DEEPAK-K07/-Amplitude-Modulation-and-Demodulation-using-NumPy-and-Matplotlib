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

```
import numpy as np 
import matplotlib.pyplot as plt 
Am = 14.3
Fm = 550
Ac = 28.6 
Fc = 5500 
Fs = 295000 
t = np.arange(0, 2/Fm, 1/Fs) 
em = Am * np.sin(2 * np.pi * Fm * t) 
plt.subplot(3, 1, 1) 
plt.plot(t, em) 
plt.grid() 
ec = Ac * np.sin(2 * np.pi * Fc * t) 
plt.subplot(3, 1, 2) 
plt.plot(t, ec) 
plt.grid() 
eam = (Ac + (Am * np.sin(2 * np.pi * Fm * t))) * np.sin(2 * np.pi * Fc * t) 
plt.subplot(3, 1, 3) 
plt.plot(t, eam) 
plt.grid() 
plt.tight_layout() 
plt.show()

```

 __Output__:

<img width="630" height="469" alt="download" src="https://github.com/user-attachments/assets/c7ae9698-f33a-4c67-9ced-7a1472e07ed6" />


 __Result__:

The message signal, carrier signal, and amplitude modulated (AM) signal will be displayed in separate plots. Thus, AM is implemented using numPy and Matplotlib.
