# python_42
python_42



Simple Integral Calculator and Plotter

A beginner-friendly Python program that calculates the indefinite and definite integral of a mathematical function and visualizes the area under the curve using a plot.

Features

Compute indefinite integrals symbolically.

Compute definite integrals over a given range.

Visualize the function and shade the area under the curve for definite integrals.

Minimal, clean, and beginner-friendly code with PEP 8-compliant comments.

Uses SymPy for symbolic math and Matplotlib for plotting.

Requirements

Python 3.8+

SymPy

NumPy

Matplotlib

Install dependencies with pip:

pip install sympy numpy matplotlib

Usage

Open integral_plot.py (or your Python file containing the code).

Modify the function f = x**2 to any other symbolic function you want to integrate.

Run the script:

python integral_plot.py


The program prints:

The indefinite integral of the function.

The definite integral over the range [0, 3].

A plot of the function and the shaded integral area is displayed.

Example Output
Indefinite Integral of x^2: x**3/3
Definite Integral of x^2 from 0 to 3: 9


A plot will also appear showing the curve of f(x) = x^2 and the shaded area under the curve from x=0 to x=3.

Code Structure

Variable Definition: x = sp.symbols('x')

Function Definition: f = x**2

Indefinite Integral: sp.integrate(f, x)

Definite Integral: sp.integrate(f, (x, 0, 3))

Plotting: Uses matplotlib.pyplot to draw the curve and shaded area.

License

This project is open-source and available under the MIT License.



# Simple Integral in Python

import sympy as sp
import numpy as np
import matplotlib.pyplot as plt

# Define the variable
x = sp.symbols('x')

# Define the function to integrate
f = x**2  # f(x) = x^2

# Calculate the indefinite integral
indef_integral = sp.integrate(f, x)
print("Indefinite Integral of x^2:", indef_integral)

# Calculate the definite integral from 0 to 3
def_integral = sp.integrate(f, (x, 0, 3))
print("Definite Integral of x^2 from 0 to 3:", def_integral)

# Plot the function and its area under the curve
x_vals = np.linspace(0, 3, 100)
y_vals = x_vals**2

plt.plot(x_vals, y_vals, label='f(x) = x^2', color='blue')
plt.fill_between(x_vals, y_vals, color='lightblue', alpha=0.5)
plt.title('Integral of f(x) = x^2 from 0 to 3')
plt.xlabel('x')
plt.ylabel('f(x)')
plt.legend()
plt.show()
