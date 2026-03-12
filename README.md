# Future Add On: Automatic Exam Correction Using Computer Vision

## Purpose

A future enhancement of the platform may include automatic result extraction and assisted grading from photos of solved exams using computer vision, OCR and local language models.

This feature is not required for the initial MVP and must be considered an optional extension to the system.

Its purpose is to reduce friction in the workflow by allowing students to photograph their solved exam pages instead of manually entering scores.

---

## High Level Workflow

1. The student solves a past exam on paper.
2. The student takes photos of the solved pages using a phone.
3. Images are uploaded to the platform.
4. The system processes the images using computer vision.
5. OCR extracts written answers.
6. The system identifies the corresponding exam questions.
7. The system evaluates answers using mathematical validation tools and language models.
8. A suggested score is produced.
9. The student confirms or adjusts the final score.

Important rule

Automatic grading must always be human confirmed.
The student must be able to edit any score before final submission.

---

## Processing Pipeline

Image Upload
↓
Image preprocessing using computer vision
↓
Perspective correction and cropping
↓
OCR extraction
↓
Answer parsing
↓
Mathematical validation
↓
Score estimation
↓
Student confirmation

---

## Image Preprocessing

Before performing OCR the system must improve image quality using computer vision techniques.

Recommended processing steps

1. Edge detection
2. Page detection
3. Perspective correction
4. Image deskewing
5. Contrast enhancement

Suggested tools

OpenCV

---

## OCR Engine

The OCR component extracts handwritten or printed text from the student's answers.

Possible technologies

1. PaddleOCR
2. Tesseract
3. TrOCR

Recommended option for handwriting support

PaddleOCR

The OCR system should extract

1. Numeric answers
2. Algebraic expressions
3. Short written explanations

---

## Question Identification

The system must determine which answer corresponds to which question.

### Structured Layout

If the exam layout is known questions can be mapped using predefined regions on the page.

Example

Top left region corresponds to Question 1
Middle region corresponds to Question 2
Bottom region corresponds to Question 3

### Layout Detection Models

For more advanced implementations document layout detection models may be used.

---

## Mathematical Validation

Automatic grading should not rely only on language models.

Instead the system should use mathematical libraries to verify answers.

Recommended approach

OCR output
↓
Mathematical expression parsing
↓
Symbolic validation
↓
Score estimation

Suggested tool

SymPy

Example

Expected answer: 2x
Student answer: x + x

SymPy can verify that both expressions are mathematically equivalent.

---

## Language Model Assistance

Local language models may assist with

1. Interpreting ambiguous answers
2. Explaining grading decisions
3. Generating feedback

Recommended setup

Ollama local inference

Possible models

1. Llama
2. Mistral
3. DeepSeek

Example prompt structure

You are grading a mathematics exam.

Question
Compute the derivative of f(x) = x²

Expected answer
2x

Student answer
2x

Return
score between 0 and 10
short explanation

The language model output must never directly determine the final score without validation.

---

## Infrastructure Requirements

Suggested architecture

Frontend
↓
Image upload service
↓
Computer vision preprocessing
↓
OCR service
↓
Math validation service
↓
Optional language model explanation
↓
Score suggestion

Suggested technologies

1. Python
2. FastAPI
3. OpenCV
4. PaddleOCR
5. SymPy
6. Ollama

---

## Student Confirmation Requirement

After automatic processing the system must display

1. Detected answers
2. Suggested score per question
3. Optional reasoning

The student must confirm the results before they are saved.

Students must be able to

1. Edit scores
2. Override suggested grading
3. Submit the final confirmed result

---

## Implementation Priority

This feature must only be implemented after the following core features are stable

1. Manual result entry
2. Exam structure database
3. Dashboard and analytics
4. Gamification system

Automatic correction should be developed in a later phase of the project.

---

## Long Term Potential

If successfully implemented this feature could enable

1. Automatic exam correction from photos
2. Rapid performance analysis
3. Near real time feedback for students
4. Large scale dataset collection for exam performance research
