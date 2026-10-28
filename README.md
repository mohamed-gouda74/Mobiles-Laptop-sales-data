# 📱💻 Mobile & Laptop Sales Data Analysis (50,000 Records)

## 📌 Project Overview
This project presents a comprehensive Exploratory Data Analysis (EDA), data cleaning, and preprocessing pipeline on a large-scale dataset containing **50,000 records** of mobile phone and laptop sales[cite: 7]. The analysis extracts valuable business insights regarding sales performance, pricing trends, storage capacities, inventory holding duration (storage days), and regional distribution.

---

## 🛠️ Dataset Features & Schema
The dataset consists of the following **18 features** (including engineered columns)[cite: 7]:

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **Product** | Object | Product category (Mobile Phone / Laptop)[cite: 7] |
| **Brand** | Object | Manufacturer brand name[cite: 7] |
| **Product Code** | Object | Unique identifier code for the product[cite: 7] |
| **Product Specification** | Object | Textual product description/specification[cite: 7] |
| **Price** | Integer | Unit price of the item[cite: 7] |
| **Inward Date** | Datetime | Date the product entered the inventory/warehouse[cite: 7] |
| **Dispatch Date** | Datetime | Date the product was dispatched/sold[cite: 7] |
| **Quantity Sold** | Integer | Number of units sold in the transaction[cite: 7] |
| **Customer Name** | Object | Name of the buyer[cite: 7] |
| **Customer Location** | Object | City/Location of the customer[cite: 7] |
| **Region** | Object | Sales region (Central, South, East, North, West)[cite: 7] |
| **CPU** | Object | Core specification/processor family (Renamed from *Core Specification*)[cite: 7] |
| **Processor Specification** | Object | Detailed processor specification[cite: 7] |
| **RAM** | Object | RAM size (e.g., 4GB, 8GB, 16GB, etc.)[cite: 7] |
| **ROM** | Object | Internal storage / ROM size[cite: 7] |
| **SSD** | Object | Solid State Drive specification[cite: 7] |
| **Storage Days** | Integer | Engineered feature: Time elapsed between Inward and Dispatch dates |
| **Revenue** | Integer | Engineered feature: Total sales revenue (`Price` $\times$ `Quantity Sold`) |

---

## 🧹 Data Cleaning & Preprocessing Steps
1. **Datetime Conversion:** Transformed `Inward Date` and `Dispatch Date` from object/string types into native datetime objects for time-series calculations.
2. **Handling Missing Values:** 
   - Identified missing entries in hardware-specific columns (`Core Specification` / `SSD`) which naturally apply only to laptops or specific devices.
   - Imputed missing values cleanly with `'Not find'` to maintain dataset integrity without dropping critical rows[cite: 7].
3. **Duplicate Check:** Verified that no duplicate rows exist in the dataset (`0 duplicates found`)[cite: 7].
4. **Feature Engineering:**
   - **`Storage Days`**: Calculated as the difference between `Dispatch Date` and `Inward Date` to measure inventory turnover time.
   - **`Revenue`**: Computed by multiplying unit `Price` by `Quantity Sold`.
   - **Column Renaming:** Renamed `Core Specification` to `CPU` for cleaner representation.

---

## 📈 Key Insights & Exploratory Data Analysis (EDA)
* **Product Split:** The dataset is evenly split between Laptops (~25,017 records) and Mobile Phones (~24,983 records)[cite: 7].
* **Pricing Range:** Unit prices range from a minimum of **5,008** to a maximum of **199,999**, with a mean price of ~102,641[cite: 7].
* **Storage Duration:** The average inventory holding period (`Storage Days`) before dispatch is roughly **30.5 days** (ranging from 1 to 60 days)[cite: 7].
* **Regional Activity:** Sales distribution spans across 5 major regions, with the **West** region showing the highest volume of transactions[cite: 7].

---

## 🛠️ Tech Stack & Libraries
* **Python**[cite: 7]
* **Pandas & NumPy** (Data manipulation and numerical operations)
* **Matplotlib & Seaborn** (Data visualization and statistical plotting)
