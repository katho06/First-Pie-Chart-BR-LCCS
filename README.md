# First-Pie-Chart-BR-LCCS
EXAM NUMBER - 205626
import pandas as pd
import matplotlib.pyplot as plt

# Read CSV file into a pandas DataFrame
file_path = 'projectdata2.csv'
df = pd.read_csv(file_path)

# Calculate the total count of 'happy' and 'sad' occurrences
above_count = df['above'].sum()
below_count = df['below'].sum()
total_count = len(df)

# Calculate the percentage of happy and sad occurrences
above_percentage = round(((above_count / total_count) * 100), 2)
below_percentage = round(((below_count / total_count) * 100) , 2)


#BR3 This pie chart shows the amount of students who study above national average and below from the microbit data
print(f"Number of students out of 20, who study above the national average is: {above_percentage}")
print(f"Number of students out of 20, who study above the national average is: {below_percentage}")

if above_percentage > below_percentage:
    print("More students study above the average")
else:
    print("More students study below the average")

# Create a pie chart
labels = ['above', 'below']
sizes = [above_percentage, below_percentage]
colors = ['lightgreen', 'lightcoral']
explode = (0.1, 0)  # explode the slice for emphasis

plt.pie(sizes, explode=explode, labels=labels, colors=colors, autopct='%1.1f%%', shadow=True, startangle=140)
plt.axis('equal')  # Equal aspect ratio ensures that the pie chart is circular.

# Display the pie chart
plt.title('Number of students out of 20, who study above and below the national average')
plt.show()
