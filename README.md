# Medical Data Sorting Program

## Overview

This is a simple Python command-line program that allows users to:

* Enter medical data for multiple patients
* Store the data in memory
* Sort the data by a selected field
* Display the sorted results

The program uses the **Selection Sort** algorithm to order the records.

---

## Features

* Manual input of patient data
* Date parsing using Python's built-in `datetime` module
* Sorting by:

  * `name`
  * `dob` (date of birth)
  * `height`
  * `weight`
* Ascending or descending order
* Formatted output display

---

## How It Works

### 1. Data Structure

Each patient is stored as a dictionary with the following structure:

```python
{
    "name": str,
    "dob": datetime,
    "height": float,
    "weight": float
}
```

All patients are stored inside a list.

---

### 2. Selection Sort Implementation

The `selection_sort(data, key, ascending=True)` function:

* Iterates through the list
* Finds the minimum (or maximum) element based on the selected key
* Swaps elements in place
* Returns the sorted list

It supports both ascending and descending order.

---

### 3. Date Parsing

The `parse_date(date_str)` function converts a string in the format:

```
YYYY-MM-DD
```

into a `datetime` object using:

```python
datetime.strptime(date_str, "%Y-%m-%d")
```

---

### 4. User Input

The `get_medical_data()` function:

* Prompts the user to enter patient information
* Stops when the user types `"done"` as the name
* Converts numeric inputs to `float`
* Converts the date string into a `datetime` object

---

### 5. Displaying Results

The `display_data(data)` function prints the sorted medical data in a readable format:

```
Name: John Doe, DOB: 1990-05-14, Height: 180.0 cm, Weight: 75.0 kg
```

---

## Program Flow

1. The program starts in `main()`
2. User enters patient data
3. User selects:

   * Field to sort by
   * Sorting order (ascending/descending)
4. Data is sorted using `selection_sort`
5. Sorted data is displayed

---

## Example Usage

```
Medical Data Sorting Program
Enter patient data. Type 'done' when finished.

Name: John Doe
Date of Birth (YYYY-MM-DD): 1990-05-14
Height (in cm): 180
Weight (in kg): 75

Name: Jane Smith
Date of Birth (YYYY-MM-DD): 1985-03-22
Height (in cm): 165
Weight (in kg): 60

Name: done

Fields to sort by: name, dob, height, weight
Enter field to sort by: height
Sort in ascending order? (y/n): y
```

---

## Requirements

* Python 3.x
* No external libraries required (uses only built-in `datetime`)

---

## Notes

* The sorting algorithm used (Selection Sort) has time complexity **O(n²)**.
* The program does not include input validation for incorrect formats (e.g., invalid date format).
* Data is not saved permanently; it exists only during program execution.

---

## Possible Improvements

* Add input validation and error handling
* Save data to a file (CSV or JSON)
* Use Python’s built-in `sorted()` function for better performance
* Add BMI calculation
* Create a graphical user interface (GUI)

---

## License

This project is free to use for educational purposes.
