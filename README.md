# London Housing Data Analysis using Pandas

## Project Overview

This project performs data analysis on the London Housing Dataset using Python and Pandas. The dataset contains information related to housing prices, crime rates, houses sold, area details, and dates.

The project focuses on:

* Data cleaning
* Date-time conversion
* Feature engineering
* Data filtering
* GroupBy operations
* Aggregation and analysis

---

# Technologies Used

* Python
* Pandas
* NumPy
* Jupyter Notebook

---

# Dataset Information

The dataset contains the following columns:

* date
* area
* average_price
* code
* houses_sold
* no_of_crimes

---

# Tasks Performed

## 1. Converted Date Column into Date-Time Format

```python
house.date = pd.to_datetime(house.date)
```

## 2. Added Year Column

```python
house['Year'] = house.date.dt.year
```

## 3. Added Month Column

```python
house.insert(1, 'month', house.date.dt.month)
```

## 4. Removed Columns

```python
house.drop(['Year', 'month'], axis=1, inplace=True)
```

## 5. Filtered Records where No. of Crimes is 0

```python
house[house.no_of_crimes == 0]
```

## 6. Found Maximum & Minimum Average Price per Year

```python
house[house.area == 'england'].groupby('Year')['average_price'].agg(['max', 'min'])
```

## 7. Found Maximum & Minimum Number of Crimes per Area

```python
house.groupby('area')['no_of_crimes'].agg(['max', 'min'])
```

## 8. Counted Records where Average Price is Less than 100000

```python
house[house.average_price < 100000].groupby('area').size()
```

---

# Key Learnings

* Data preprocessing using Pandas
* Working with Date-Time data
* Filtering data using conditions
* GroupBy and aggregation functions
* Handling DataFrame columns
* Data analysis techniques using Python

---

# Conclusion

This project helped in understanding practical data analysis operations using Pandas. It demonstrates how housing datasets can be analyzed efficiently using filtering, grouping, aggregation, and date-time operations.

---

