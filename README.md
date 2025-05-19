# CITS4407 Assignment 2 — Board Game Dataset Shell Analysis

##  Author Information

- **Name:** Jagdish Singh  
- **Student ID:** 244102189  
- **Unit:** CITS4407  
- **Semester:** Semester 1, 2025  
 

---

##  Overview

This project demonstrates the use of Unix tools and Bash scripting to process and analyze a large board game dataset from BoardGameGeek. The work is structured across three main scripts:

1. `empty_cells` — identifies data quality issues by reporting missing values.
2. `preprocess` — cleans and standardizes the dataset for analysis.
3. `analysis` — computes frequency statistics and performs correlation analysis.


---

##  File Structure

```
CITS4407_Assignment_2/
├── empty_cells          # Bash script to count empty cells per column
├── preprocess           # Bash script to clean and normalize dataset
├── analysis             # Bash script to perform data analysis
├── README.md            # This documentation file
├── bgg_dataset.txt      # Raw dataset file
├── bgg_cleaned.tsv      # Output from preprocess
└── tiny_sample.tsv      # Sample dataset for testing
```

---

##  Script Descriptions & Usage

###  `empty_cells`

**Description:**  
Counts and reports the number of empty (missing) values in each column of a delimited input file.

**Key Features:**
- Handles malformed headers (e.g., `/ID`)
- Strips whitespace and non-ASCII characters before checking for emptiness
- Works with custom delimiters (e.g., `;`)

**Usage:**
```bash
./empty_cells.sh <filename> <separator>
```

---

###  `preprocess`

**Description:**  
Cleans the raw `bgg_dataset.txt` file to prepare it for analysis by:
- Converting `;` to tab (`\t`)
- Replacing decimal commas with dots
- Removing carriage returns and non-ASCII characters
- Filling in missing IDs with new unique values

**Usage:**
```bash
./preprocess <input_file> > <output_file>
```

**Example:**
```bash
./preprocess bgg_dataset.txt > bgg_cleaned.tsv
```

---

###  `Analysis`

**Description:**  
Analyzes the cleaned dataset to extract insights, including:
1. Identifying the most common game mechanics.
2. Identifying the most common game domain.
3. Computing correlations between year/complexity and average rating.

**Usage:**
```bash
./analysis <cleaned_tsv_file>
```

**Example:**
```bash
./analysis bgg_cleaned.tsv
```

---

##  Testing

All scripts have been tested using the UWA-provided Docker environment to ensure compatibility and correctness. Sample datasets (`tiny_sample.tsv`) are included for testing purposes.

---

