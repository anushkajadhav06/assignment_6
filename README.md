# assignment_6
import pandas as pd

# Create sample data
data = {
    'Name': ['Aman', 'Riya', 'Karan', 'Riya', 'Neha'],
    'Marks': [85, 90, None, 90, 75],
    'City': ['Pune', 'Mumbai', 'Delhi', 'Mumbai', None]
}

df = pd.DataFrame(data)

print("Original Data:")
print(df)

# Display first five rows
print("\nFirst five rows:")
print(df.head())

# Display dataset information
print("\nDataset information:")
df.info()

# Display statistical summary
print("\nStatistical summary:")
print(df.describe())

# Check missing values
print("\nMissing values:")
print(df.isnull().sum())

# Fill missing Marks with mean
df['Marks'] = df['Marks'].fillna(df['Marks'].mean())

# Fill missing City
df['City'] = df['City'].fillna('Unknown')

print("\nAfter filling missing values:")
print(df)

# Identify duplicate rows
print("\nDuplicate rows:")
print(df.duplicated())

# Remove duplicate rows
df = df.drop_duplicates()

print("\nAfter removing duplicates:")
print(df)



# Select students scoring above 80
print("\nStudents scoring above 80:")
print(df.loc[df['Marks'] > 80])

# Save cleaned data to CSV
df.to_csv('cleaned_data.csv', index=False)

print("\nCleaned data saved successfully!")
