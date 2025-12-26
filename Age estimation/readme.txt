# Age Estimation Chat Workflow

## Overview
This project is a simple **age estimation chat workflow** built with **n8n** and **LangChain Chat nodes**.
The workflow receives a numeric age as user input and classifies it into predefined age groups.

The output is returned as a **Persian age category label** based on rule-based conditions.

---

## How It Works
1. The workflow starts when a **chat message is received**.
2. The user input is converted to a number.
3. A **Switch node** evaluates the age using conditional rules.
4. Based on the matched rule, the system responds with the corresponding age category.

---

## Age Classification Rules

| Age Range | Condition | Output (Persian) | Meaning (English) |
|----------|----------|------------------|------------------|
| Under 8 | `< 8` | خردسال | Child |
| 8 – 16 | `≤ 16` | نوجوان | Teenager |
| 17 – 39 | `< 40` | جوان | Young Adult |
| 40 – 59 | `< 60` | میانسال | Middle-aged |
| 60 and above | `≥ 60` | کهنسال | Elderly |

---

## Workflow Logic
- Input must be a **numeric value**
- Strict number validation is applied
- Only one age category is returned per input
- No additional user interaction is required

---

## Technologies Used
- n8n
- LangChain
- Rule-based switch logic

---

## Example


Input:25

Output:جوان


