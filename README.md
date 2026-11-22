# Experiment 4: Yearly Revenue Growth Visualization Using Matplotlib

## Aim

To visualize the yearly trend of company revenue and expenses from 2017 to 2023 using Matplotlib by plotting multi-line charts with customized markers, labels, legends, gridlines, and point annotations.

## Algorithm

1. **Start** the program.
2. **Import Libraries**: Import `matplotlib.pyplot` as `plt` for plotting and `numpy` as `np` for numeric array generation and index lookup.
3. **Initialize Dataset**:
   * Generate an array `years` spanning `2017` to `2023` using `np.arange(2017, 2024)`.
   * Define lists `revenue` and `expenses` representing annual amounts in Lakhs.
4. **Configure Figure & Plot Lines**:
   * Initialize a figure canvas of size 8 × 5 inches using `plt.figure(figsize=(8, 5))`.
   * Plot `revenue` against `years` as a solid green line with circular markers (`marker='o'`).
   * Plot `expenses` against `years` as a dashed red line (`linestyle='--'`) with square markers (`marker='s'`).
5. **Format Chart Aesthetics**:
   * Add a bold chart title (`plt.title()`) and axis labels (`plt.xlabel()`, `plt.ylabel()`).
   * Enable dashed semi-transparent gridlines (`plt.grid()`) and place the legend in the upper-left corner (`plt.legend(loc='upper left')`).
6. **Annotate Peak Values**:
   * Find the indices of maximum revenue and maximum expenses using `np.argmax()`.
   * Highlight both peak data points on the chart with directional arrows and text callouts using `plt.annotate()`.
7. **Adjust Layout & Display**:
   * Prevent label clipping via `plt.tight_layout()` and render the final plot with `plt.show()`.
8. **Stop** the program.

## Functions and Methods Used

| Category | Function / Method | Purpose / Description |
| :--- | :--- | :--- |
| **Numerical Operations** | `np.arange()` | Generates evenly spaced integer years (`2017` through `2023`) |
| | `np.argmax()` | Returns the array index of the maximum revenue and expense values |
| **Line Plotting** | `plt.figure()` | Initializes a new figure window with custom dimensions |
| | `plt.plot()` | Draws line plots with customized markers, colors, line styles, and widths |
| **Chart Formatting** | `plt.title()`, `plt.xlabel()`, `plt.ylabel()` | Adds descriptive title and axis labels with custom font sizes |
| | `plt.grid()`, `plt.legend()` | Adds background gridlines and displays series labels in the upper left |
| **Annotations & Display** | `plt.annotate()` | Places text labels with arrows pointing to peak revenue and expense points |
| | `plt.tight_layout()`, `plt.show()` | Optimizes spacing to avoid overlapping elements and renders the figure |

## Program / Code

```python
# Company Revenue and Expense Visualization using Matplotlib
import matplotlib.pyplot as plt
import numpy as np

# Step 1: Create dataset (amounts in Lakhs)
years = np.arange(2017, 2024)
revenue = [120, 135, 150, 142, 170, 195, 220]
expenses = [90, 98, 110, 115, 125, 140, 155]

# Step 2: Plot Revenue and Expenses
plt.figure(figsize=(8, 5))
plt.plot(years, revenue, color='green', marker='o', linewidth=2, label='Revenue')
plt.plot(years, expenses, color='red', linestyle='--', marker='s', linewidth=2, label='Expenses')

# Step 3: Add titles, labels, and grid
plt.title('Yearly Revenue vs Expenses (2017-2023)', fontsize=14, fontweight='bold')
plt.xlabel('Year', fontsize=12)
plt.ylabel('Amount (in Lakhs)', fontsize=12)
plt.grid(True, linestyle='--', alpha=0.5)

# Step 4: Add legend
plt.legend(loc='upper left')

# Step 5: Annotate highest revenue and expense
max_rev_idx = np.argmax(revenue)
max_exp_idx = np.argmax(expenses)

plt.annotate(f'Peak Revenue: {revenue[max_rev_idx]}L',
             xy=(years[max_rev_idx], revenue[max_rev_idx]),
             xytext=(years[max_rev_idx] - 1.9, revenue[max_rev_idx] - 4),
             arrowprops=dict(arrowstyle='->', color='green'),
             fontsize=10, color='green')

plt.annotate(f'Peak Expenses: {expenses[max_exp_idx]}L',
             xy=(years[max_exp_idx], expenses[max_exp_idx]),
             xytext=(years[max_exp_idx] - 1.4, expenses[max_exp_idx] - 40),
             arrowprops=dict(arrowstyle='->', color='red'),
             fontsize=10, color='red')

# Step 6: Adjust layout and show plot
plt.tight_layout()
plt.savefig('output.png', dpi=150)   # saves the chart for the README
plt.show()
```

## Output

![Yearly Revenue vs Expenses (2017-2023)](<img width="1200" height="750" alt="output" src="https://github.com/user-attachments/assets/458b4c5b-70ca-4fec-88dd-c69fe59b8f32" />
)

## Result

The program successfully creates datasets for yearly company revenue and expenses and renders an annotated multi-line comparison chart using Matplotlib.
