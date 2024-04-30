# plot two csv files against each others

```python
#!/bin/env python3
import argparse
import matplotlib.pyplot as plt
import csv

def plot_csv(file1, file2):
    data1 = {'x': [], 'y': []}
    data2 = {'x': [], 'y': []}

    # Read data from the first CSV file
    with open(file1, 'r') as csv_file:
        csv_reader = csv.reader(csv_file)
        for row in csv_reader:
            data1['x'].append(int(row[0]))
            data1['y'].append(float(row[1]))

    # Read data from the second CSV file
    with open(file2, 'r') as csv_file:
        csv_reader = csv.reader(csv_file)
        for row in csv_reader:
            data2['x'].append(int(row[0]))
            data2['y'].append(float(row[1]))

    # Create and display the plot
    plt.plot(data1['x'], data1['y'], label='File 1')
    plt.plot(data2['x'], data2['y'], label='File 2')
    plt.xlabel('Line Number')
    plt.ylabel('Value')
    plt.legend()
    plt.show()

if __name__ == '__main__':
    parser = argparse.ArgumentParser(description='Plot two CSV files')
    parser.add_argument('file1', help='First CSV file')
    parser.add_argument('file2', help='Second CSV file')
    args = parser.parse_args()
    plot_csv(args.file1, args.file2)

```
