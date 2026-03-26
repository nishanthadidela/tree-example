# Book Search System using AVL Tree

## Overview

This project implements a fast book search system using an AVL Tree (a self-balancing binary search tree) on a real-world Goodreads dataset containing more than 11,000 books.

The goal of this project is to demonstrate how tree-based search algorithms perform significantly better than linear search when working with large datasets.

The system allows users to enter a book title and instantly retrieve relevant metadata such as author name, publication year, number of pages, and rating.

---

## Example

Input:

A Little Princess

Output:

MATCH FOUND  
Title: A Little Princess  
Author: Frances Hodgson Burnett / Nancy Bond  
Year: 2002 | Pages: 242 | Rating: 4.2  

---

## Dataset

This project uses the Goodreads Books dataset which contains over 11,000 book records.

Each record includes multiple metadata fields such as:

- book title  
- author name  
- average rating  
- number of pages  
- publication date  

Since the dataset comes from real-world sources, it contains noisy data such as:

- column names with leading or trailing spaces  
- dates stored in string format (MM/DD/YYYY)  
- missing values in rating or page count fields  
- inconsistent formatting  

This satisfies the requirement of working with a large and imperfect real-world dataset.

---

## Algorithm Used

The main algorithm used in this project is an AVL Tree.

An AVL Tree is a self-balancing binary search tree. While inserting book records, the tree automatically maintains balance by performing rotations whenever one side becomes heavier than the other.

This ensures that search operations remain efficient even as the dataset grows.

When searching for a book title, the AVL Tree reduces the search space at every step instead of scanning the entire dataset.

Time Complexity:

- Insert operation: O(log N)  
- Search operation: O(log N)  

Compared to linear search which takes O(N), AVL Tree search performs much faster for large datasets.

For example, in a dataset with 11,000 books, linear search may require up to 11,000 comparisons, while AVL search typically finds the result within around 14 steps.

---

## Preprocessing

Before building the AVL Tree, the dataset is cleaned to handle real-world noise and inconsistencies.

Steps performed include:

- removing accidental spaces from column names  
- converting ratings and page counts to numeric values  
- extracting year from complex date strings  
- handling missing or invalid values  
- removing records without valid book titles  

This preprocessing ensures the tree can be built reliably and search results remain accurate.

---

## Features

- Fast title-based search using AVL Tree  
- Works on dataset with more than 11,000 records  
- Automatically maintains balance using tree rotations  
- Displays book metadata including author, year, rating, and pages  
- Includes performance comparison with linear search  

---

## Project Structure

book_search.py → main program (data cleaning, AVL construction, search loop)  
books.csv → raw Goodreads dataset  
cleaned_books.csv → processed dataset  
README.md → documentation  
MSML606_Project_Proposal.pdf → project proposal  

---

## How to Run

Install dependency:

pip install pandas

Run the program:

python book_search.py

---

## Key Learning Outcomes

- Implementation of a self-balancing binary search tree (AVL Tree)  
- Handling noisy real-world datasets  
- Understanding practical impact of algorithmic time complexity  
- Storing structured metadata objects inside tree nodes  
- Comparing performance of tree-based search vs linear search  

---

## Conclusion

This project demonstrates how AVL Trees can be effectively used to build scalable search systems for large structured datasets.

The results clearly show that balanced tree search methods provide significant performance advantages over simple linear search as dataset size increases.

---

## AI Usage Statement

AI tools were used only for guidance and clarification during development.

The core components of this project were manually implemented, including:

- AVL Tree data structure implementation  
- rotation logic and balancing mechanism  
- preprocessing pipeline for handling noisy data  
- search logic and metadata retrieval  

AI assistance was used only for:

- understanding interface design decisions  
- improving code readability  
- formatting documentation  

No AI-generated code was directly used for the core algorithm or preprocessing logic.

All implementation logic, algorithm design decisions, and testing were performed manually.