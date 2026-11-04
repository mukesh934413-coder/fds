# fds
lab


PROGRAM 1: NumPy Arrays - Arithmetic and Aggregates PROGRAM

import numpy as np

a = np.array([10, 20, 30, 40]) b = np.array([2, 4, 5, 10])

print("Addition:", a+b) print("Subtraction:", a-b) print("Multiplication:", a*b) print("Division:", a/b)

print("Sum:", np.sum(a)) print("Mean:", np.mean(a)) print("Minimum:", np.min(a)) print("Maximum:", np.max(a))

OUTPUT

Addition: [12 24 35 50]

Subtraction: [ 8 16 25 30]

Multiplication: 20 80 150 4001

Division: [5. 5. 6. 4.]

Sum: 100

Mean: 25.0

Minimum: 10

Maximum: 40




PROGRAM 2: Pandas DataFrame - Indexing, Slicing and Filtering

PROGRAM

import pandas as pd

'Name': ['Anu', 'Bala', 'Cathy', 'David'],

data = {

'Age': [18, 19, 18, 20],

'Mark': [85, 70, 95, 60]

}

df pd.DataFrame (data)

print(df)

print (df ['Name'])

print(df [0:2])

print (df [df [Mark']> 80])

OUTPUT

Name Age Mark

0

Anu 18

85

Bala 19

70

2 Cathy 18 3

95

David

20 60

0

Anu

Bala

2

Cathy

3

David

Name Age Mark

Anu 18

85

85

Bala 19 70

Name Age Mark

Anu 18 85

Cathy

PROGRAM 3: NumPy – Boolean Mask, Filtering and Broadcasting
PROGRAM
import numpy as np
a = np.array([10, 20, 30, 40, 50])
print("Boolean:", a > 25)
print("Filtered:", a[a > 25])
print("Broadcasting:", a + 5)
OUTPUT
Boolean: [False False True True True]
Filtered: [30 40 50]
Broadcasting: [15 25 35 45 55]

PROGRAM 4: Pandas – Reshaping, loc, iloc, melt, stack and pivot
PROGRAM
import pandas as pd
df = pd.DataFrame({
 'Name': ['Anu', 'Bala'],
 'Maths': [90, 80],
 'Science': [85, 75]
})
print("LOC:\n", df.loc[0])
print("ILOC:\n", df.iloc[1])
print("MELT:\n", pd.melt(df, id_vars=['Name']))
print("STACK:\n", df.set_index('Name').stack())
d = pd.DataFrame({
 'Name': ['Anu','Anu','Bala','Bala'],
 'Subject': ['Maths','Science','Maths','Science'],
 'Mark': [90,85,80,75]
})
print("PIVOT:\n", d.pivot(index='Name',
 columns='Subject', values='Mark'))
OUTPUT
LOC: Anu, Maths=90, Science=85
ILOC: Bala, Maths=80, Science=75
MELT:
 Name variable value
0 Anu Maths 90
1 Bala Maths 80
2 Anu Science 85
3 Bala Science 75
STACK: Anu-Maths 90, Anu-Science 85,
 Bala-Maths 80, Bala-Science 75
PIVOT:
Subject Maths Science
Name
Anu 90 85
Bala 80 75


PROGRAM 5: Iris Text File – Load and Explore with Pandas
PROGRAM
import pandas as pd
df = pd.read_csv('iris.txt', sep=',')
print(df.head())
print(df.info())
print("Shape:", df.shape)
OUTPUT
First five records:
 sepal_length sepal_width petal_length petal_width
0 5.1 3.5 1.4 0.2
1 4.9 3.0 1.4 0.2
2 4.7 3.2 1.3 0.2
3 4.6 3.1 1.5 0.2
4 5.0 3.6 1.4 0.2
Shape: (150, 4)
(Assumes a four-column Iris text file.)



PROGRAM 6: Excel Dataset – Import and Descriptive Statistics
PROGRAM
import pandas as pd
df = pd.read_excel('students.xlsx')
print(df.head())
print(df.describe())
OUTPUT
Example data:
 Name Maths Science
0 Anu 80 85
1 Bala 70 75
2 Cathy 90 95
3 David 60 65
 Maths Science
count 4.00 4.00
mean 75.00 80.00
std 12.91 12.91
min 60.00 65.00
max 90.00 95.00

PROGRAM 7: Iris Data from URL – First 10 Records
PROGRAM
import pandas as pd
url = "https://raw.githubusercontent.com/mwaskom/seaborn-data/master/iris.csv"
df = pd.read_csv(url)
print(df.head(10))
OUTPUT
 sepal_length sepal_width petal_length petal_width species
0 5.1 3.5 1.4 0.2 setosa
1 4.9 3.0 1.4 0.2 setosa
2 4.7 3.2 1.3 0.2 setosa
3 4.6 3.1 1.5 0.2 setosa
4 5.0 3.6 1.4 0.2 setosa
5 5.4 3.9 1.7 0.4 setosa
6 4.6 3.4 1.4 0.3 setosa
7 5.0 3.4 1.5 0.2 setosa
8 4.4 2.9 1.4 0.2 setosa
9 4.9 3.1 1.5 0.1 setosa



PROGRAM 8: Dataset Exploration – Shape, Dtypes, Missing Values and
Stats
PROGRAM
import pandas as pd
df = pd.DataFrame({
 'Name': ['Anu', 'Bala', 'Cathy', 'David'],
 'Age': [18, 19, None, 20],
 'Mark': [85, 70, 95, None]
})
print("Shape:", df.shape)
print("Data Types:\n", df.dtypes)
print("Missing Values:\n", df.isnull().sum())
print("Summary:\n", df.describe())
OUTPUT
Shape: (4, 3)
Data Types:
Name object
Age float64
Mark float64
Missing Values:
Name 0
Age 1
Mark 1
Summary:
 Age Mark
count 3.000000 3.000000
mean 19.000000 83.333333
min 18.000000 70.000000
max 20.000000 95.00000



PROGRAM 9: Student Records – Group By Department
PROGRAM
import pandas as pd
df = pd.DataFrame({
 'Name': ['Anu', 'Bala', 'Cathy', 'David'],
 'Dept': ['CSE', 'IT', 'CSE', 'IT'],
 'Mark': [80, 70, 90, 85]
})
g = df.groupby('Dept')['Mark']
print("Count:\n", g.count())
print("Average:\n", g.mean())
print("Maximum:\n", g.max())
OUTPUT
Count:
Dept
CSE 2
IT 2
Average:
Dept
CSE 85.0
IT 77.5
Maximum:
Dept
CSE 90
IT 85



PROGRAM 10: Grouped Data – Multiple Aggregations Using agg()
PROGRAM
import pandas as pd
df = pd.DataFrame({
 'Dept': ['CSE', 'CSE', 'IT', 'IT'],
 'Mark': [80, 90, 70, 85]
})
result = df.groupby('Dept')['Mark'].agg(
 ['count', 'mean', 'max', 'min']
)
print(result)
OUTPUT
 count mean max min
Dept
CSE 2 85.0 90 80
IT 2 77.5 85 70PROGRAM 11: Student Details and Exam Marks – Merge
PROGRAM
import pandas as pd
students = pd.DataFrame({
 'ID': [1, 2, 3],
 'Name': ['Anu', 'Bala', 'Cathy']
})
marks = pd.DataFrame({
 'ID': [1, 2, 3],
 'Mark': [85, 75, 95]
})
result = pd.merge(students, marks, on='ID')
print(result)
OUTPUT
 ID Name Mark
0 1 Anu 85
1 2 Bala 75
2 3 Cathy 95



PROGRAM 12: Hierarchical Index – Retrieve Records by Level
PROGRAM
import pandas as pd
data = {'Mark': [85, 90, 75, 80]}
index = [
 ['CSE', 'CSE', 'IT', 'IT'],
 ['Anu', 'Bala', 'Cathy', 'David']
]
mi = pd.MultiIndex.from_arrays(
 index, names=['Dept', 'Name'])
df = pd.DataFrame(data, index=mi)
print(df)
print("\nCSE Records:")
print(df.loc['CSE'])
OUTPUT
 Mark
Dept Name
CSE Anu 85
 Bala 90
IT Cathy 75
 David 80
CSE Records:
 Mark
Name
Anu 85
Bala 90




PROGRAM 13: Monthly Sales – Line Chart and Bar Chart
PROGRAM
import matplotlib.pyplot as plt
months = ['Jan', 'Feb', 'Mar', 'Apr']
sales = [100, 150, 120, 200]
plt.plot(months, sales, marker='o', label='Sales')
plt.title("Monthly Sales - Line Chart")
plt.xlabel("Months")
plt.ylabel("Sales")
plt.legend()
plt.show()
plt.bar(months, sales, label='Sales')
plt.title("Monthly Sales - Bar Chart")
plt.xlabel("Months")
plt.ylabel("Sales")
plt.legend()
plt.show()
OUTPUT
Output:
1. Line chart: Jan=100, Feb=150,
 Mar=120, Apr=200.
2. Bar chart: bars show the same
 four monthly sales values.
(Both charts appear in separate windows.)



PROGRAM 14: Dynamic Content – Responds to User Input
PROGRAM
name = input("Enter your name: ")
mark = int(input("Enter your mark: "))
print("Student Name:", name)
if mark >= 50:
 print("Result: PASS")
else:
 print("Result: FAIL")
OUTPUT
Enter your name: Anu
Enter your mark: 85

Student Name: Anu
Result: PASS




PROGRAM 15: Pie Chart and Histogram
PROGRAM
import matplotlib.pyplot as plt
dept = ['CSE', 'IT', 'ECE']
students = [40, 30, 30]
plt.pie(students, labels=dept, autopct='%1.1f%%')
plt.title("Department Students")
plt.show()
marks = [50, 60, 70, 75, 80, 85, 90, 95]
plt.hist(marks, bins=5, edgecolor='black')
plt.title("Marks Distribution")
plt.xlabel("Marks")
plt.ylabel("Frequency")
plt.show()
OUTPUT
Output:
1. Pie chart: CSE = 40%, IT = 30%,
 ECE = 30%.
2. Histogram: frequency bars for
 the marks grouped into 5 bins.
(Charts appear in separate windows.)



PROGRAM 16: Iris – 3D Scatter Plot of Three Attributes
PROGRAM
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris
iris = load_iris()
x = iris.data[:, 0]
y = iris.data[:, 1]
z = iris.data[:, 2]
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.scatter(x, y, z)
plt.show()
OUTPUT
Output:
A 3D scatter plot of Iris data:
X-axis: Sepal length
Y-axis: Sepal width
Z-axis: Petal length



PROGRAM 17: 3D Plot – Axis Labels, Title and Legend
PROGRAM
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris
iris = load_iris()
x = iris.data[:, 0]
y = iris.data[:, 1]
z = iris.data[:, 2]
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.scatter(x, y, z, label='Iris Data')
ax.set_xlabel('Sepal Length')
ax.set_ylabel('Sepal Width')
ax.set_zlabel('Petal Length')
ax.set_title('3D Iris Plot')
ax.legend()
plt.show()
OUTPUT
Output:
3D Iris scatter plot with:
X-axis: Sepal Length
Y-axis: Sepal Width
Z-axis: Petal Length
Title: 3D Iris Plot
Legend: Iris Data

PROGRAM 18: Basemap – World Map with Coastlines and Borders
PROGRAM
import matplotlib.pyplot as plt
from mpl_toolkits.basemap import Basemap
plt.figure()
m = Basemap(projection='cyl', resolution='c')
m.drawcoastlines()
m.drawcountries()
m.drawmapboundary()
plt.title("World Map")
plt.show()
OUTPUT
Output:
World map showing coastlines,
country borders and the map boundary.
(Requires the Basemap package.)


PROGRAM 19: Map – Plot Locations Using Latitude and Longitude
PROGRAM
import matplotlib.pyplot as plt
places = ['Chennai', 'Delhi', 'Mumbai']
lat = [13.08, 28.61, 19.07]
lon = [80.27, 77.20, 72.87]
plt.scatter(lon, lat)
for i in range(3):
 plt.text(lon[i], lat[i], places[i])
plt.xlabel("Longitude")
plt.ylabel("Latitude")
plt.title("Selected Locations")
plt.grid()
plt.show()
OUTPUT
Output:
Scatter plot with labelled points:
Chennai, Delhi and Mumbai.
X-axis: Longitude
Y-axis: Latitude



PROGRAM 20: Mean, Median, Mode, Variance and Standard Deviation
PROGRAM
import numpy as np
from statistics import mode
data = [10, 20, 20, 30, 40]
print("Mean:", np.mean(data))
print("Median:", np.median(data))
print("Mode:", mode(data))
print("Variance:", np.var(data))
print("Standard Deviation:", np.std(data))
OUTPUT
Mean: 24.0
Median: 20.0
Mode: 20
Variance: 104.0
Standard Deviation: 10.198039027185569

