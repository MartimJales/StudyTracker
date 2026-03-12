# StudyTracker Platform

## 1. Project Overview

This platform aims to help secondary school students prepare for national exams by allowing them to record the results they obtain when solving past national exams and analyze their performance through dashboards and detailed statistics.

The system does **not generate new exercises** and does **not provide new problem sets**.

Instead, it provides a structured environment where students can:

- record their results when solving past exams
- track their progress over time
- identify weaknesses by topic
- analyze their preparation through data visualizations
- stay motivated through gamified progress tracking

The platform acts as a **study tracker and analytics system for exam preparation**.

---

# 2. Core Principles

## 2.1 No New Exercises

The platform **must not create exercises**.

All study content comes from:

- official past exams
- the structure of those exams

The system only stores:

- exam structure
- question metadata
- scoring information
- topic classification
- student results

---

## 2.2 Platform Role

The platform functions as:

- a study journal
- a performance analysis tool
- a motivational progress system

It **does not replace textbooks or tutoring**.

---

# 3. User Roles

The system supports two roles.

## 3.1 Student

Students can:

- create an account
- log in
- select an exam they solved
- input the score obtained on each question
- view dashboards and statistics
- track improvement over time

## 3.2 Administrator

Administrators can:

- create exams
- define questions for each exam
- assign topics to questions
- correct structural data if necessary

Administrators **cannot modify student results**.

---

# 4. Data Model

## 4.1 Users

Table: `users`

Fields
