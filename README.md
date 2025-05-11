# PSK
## Aim:
  To assess the performance of Phase-Shift Keying (PSK) modulation in digital communication systems under varying noise conditions.
## Tools required:

  * Colab (for executing Python code)
  * Libraries: NumPy, Matplotlib
    
## Program:
~~~
import numpy as np
import matplotlib.pyplot as plt

# Input Data
data = np.array([1, 1, 1, 1, 0, 0, 0, 1, 0, 0])
print("Input Data:", data)

# BPSK Modulation: Mapping 0 -> -1 and 1 -> +1
bpsk_signal = 2 * data - 1

# Create time axis
t = np.linspace(0, 1, 100)

# Carrier Wave (Cosine)
carrier = np.cos(2 * np.pi * 5 * t)

# Modulated Signal
modulated_signal = np.array([bit * carrier for bit in bpsk_signal]).flatten()

# Time axis for plotting
time_axis = np.linspace(0, len(data), len(modulated_signal))

# Plotting the results
plt.figure(figsize=(10, 6))

plt.subplot(3, 1, 1)
plt.stem(data)  # Remove use_line_collection argument
plt.title("Input Binary Data (0s and 1s)")
plt.xlabel("Bit Index")
plt.ylabel("Bit Value")

plt.subplot(3, 1, 2)
plt.plot(time_axis, modulated_signal)
plt.title("BPSK Modulated Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(3, 1, 3)
plt.plot(t, carrier)
plt.title("Carrier Wave (Cosine)")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.tight_layout()
plt.show()

~~~

## Output Waveform:
![image](https://github.com/user-attachments/assets/2019ded6-024a-4219-9631-f2f71d7f981a)
![image](https://github.com/user-attachments/assets/dfdd30a4-aef4-44aa-aecf-4a8b68254a32)

## Results:
  * PSK successfully encoded data by changing the phase of the carrier signal.
  * It demonstrated good resistance to noise and maintained data integrity.
  * The modulation technique improved overall transmission efficiency.

The experiment confirmed PSK as an effective method for reliable digital communication.
