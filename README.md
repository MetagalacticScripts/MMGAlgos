# README: MyMedGlobal Dataset for Algorithm Development

## Overview

This dataset comprises eight interrelated CSV files designed to support the development and evaluation of algorithms for clinic search, ranking, personalization, and quality assurance. While some data entries are synthetically generated to facilitate testing during our database transition, they are structured to reflect real-world scenarios. This approach ensures that the algorithms can be effectively validated and prepared for deployment with actual data.

**Confidentiality Notice:** This dataset is confidential and intended solely for use by authorized personnel in accordance with the volunteer agreement.

**Managed by:** Audrey Gil (a.gilnetworking@gmail.com)  
**Owned by:** MyMedGlobal

---

## Dataset Structure

The dataset includes the following CSV files:

1. **clinics.csv**
2. **search_logs.csv**
3. **patients.csv**
4. **clinic_views.csv**
5. **questions.csv**
6. **answers.csv**
7. **clinic_reviews.csv**
8. **clinic_messages.csv**

Each file is detailed below with its purpose and schema.

---

### 1. clinics.csv

**Purpose:** Supports completeness scoring, search ranking, similarity analysis, responsiveness metrics, and identification of content gaps.

**Schema:**

- `clinic_id`: Unique identifier for the clinic.
- `clinic_name`: Name of the clinic.
- `country`: Country where the clinic is located.
- `city`: City where the clinic is located.
- `specialties`: Comma-separated list of services offered.
- `languages_spoken`: Languages available at the clinic.
- `is_verified`: 1 if the clinic is verified; 0 otherwise.
- `has_profile_photo`: 1 if a profile photo exists; 0 otherwise.
- `has_doctor_bio`: 1 if doctor bios are available; 0 otherwise.
- `has_services_listed`: 1 if services are listed; 0 otherwise.
- `has_prices_listed`: 1 if pricing information is available; 0 otherwise.
- `has_reviews`: 1 if there is at least one review; 0 otherwise.
- `completeness_score`: Calculated score indicating profile completeness (optional).
- `average_price`: Average price for common services.
- `average_review_rating`: Average rating (1–5 stars).
- `response_rate_percent`: Percentage of messages responded to.
- `average_response_time_hours`: Average time (in hours) to respond to inquiries.
- `last_updated_date`: Date when the profile was last updated.
- `total_clicks`: Total number of clicks from search results.
- `last_clicked_date`: Most recent date the clinic was clicked.
- `clinic_activity_score`: Score based on logins, edits, Q&A participation, etc.
- `inquiries_last_30_days`: Number of new inquiries in the last 30 days.
- `last_response_date`: Date when the clinic last responded to a message.

---

### 2. search_logs.csv

**Purpose:** Analyzes patient search behavior, identifies popular services, tracks trends, and enhances smart ranking algorithms.

**Schema:**

- `search_id`: Unique identifier for each search.
- `patient_id`: Identifier of the patient performing the search.
- `search_query`: Raw search terms entered by the patient.
- `filters_applied`: Comma-separated list of filters applied during the search.
- `treatment_clicked`: Treatment selected from the search results.
- `country_clicked`: Country associated with the selected treatment.
- `clicked_clinic_id`: Identifier of the clinic clicked.
- `time_on_search_page`: Time spent on the search page (in seconds).
- `timestamp`: Date and time when the search occurred.

---

### 3. patients.csv

**Purpose:** Facilitates "patients like you" logic and personalization features.

**Schema:**

- `patient_id`: Unique identifier for the patient.
- `age`: Age of the patient.
- `gender`: Gender of the patient (e.g., Male, Female, Other).
- `location`: City or country of the patient.
- `conditions`: Comma-separated list of health conditions.
- `interested_treatments`: Comma-separated list of treatments the patient is interested in.
- `clinics_viewed`: Comma-separated list of clinic IDs viewed by the patient.

---

### 4. clinic_views.csv

**Purpose:** Supports "Patients Also Viewed" features, identifies similar clinics, and tracks patient behavior.

**Schema:**

- `view_id`: Unique identifier for each view event.
- `patient_id`: Identifier of the patient who viewed the clinic.
- `clinic_id`: Identifier of the clinic that was viewed.
- `view_timestamp`: Date and time when the clinic was viewed.

---

Certainly! Here's the continuation of your README with detailed sections for the remaining CSV files:

---

### 5. questions.csv

**Purpose:** Supports identification of the most helpful and trending questions, enhances related question suggestions, and assists in spam detection.

**Schema:**

- `question_id`: Unique identifier for each question.
- `patient_id`: Identifier of the patient who asked the question.
- `clinic_id`: (Optional) Identifier of the related clinic.
- `question_text`: Full text of the question.
- `upvotes`: Number of upvotes received.
- `views`: Number of times the question was viewed.
- `answers_count`: Number of responses to the question.
- `time_on_page`: Average time (in seconds) spent reading the question.
- `created_at`: Timestamp when the question was created.

---

### 6. answers.csv

**Purpose:** Facilitates quality scoring of doctor responses and supports future features related to response evaluation.

**Schema:**

- `answer_id`: Unique identifier for each answer.
- `question_id`: Identifier of the question being answered.
- `provider_id`: Identifier of the doctor or clinic representative who answered.
- `answer_text`: Full text of the reply.
- `timestamp`: Date and time when the reply was posted.

---

### 7. clinic_reviews.csv

**Purpose:** Assists in detecting fake reviews, evaluating review quality, and building trust through authentic feedback.

**Schema:**

- `review_id`: Unique identifier for each review.
- `patient_id`: Identifier of the reviewer.
- `clinic_id`: Identifier of the reviewed clinic.
- `review_text`: Text content of the review.
- `rating`: Rating given, ranging from 1 to 5 stars.
- `timestamp`: Date and time when the review was posted.
- `ip_address`: IP address used to post the review.

---

### 8. clinic_messages.csv

**Purpose:** Supports calculation of clinic responsiveness scores and analysis of communication patterns.

**Schema:**

- `message_id`: Unique identifier for each message.
- `patient_id`: Identifier of the patient who sent the message.
- `clinic_id`: Identifier of the clinic receiving the message.
- `sent_time`: Timestamp when the patient sent the message.
- `replied_time`: Timestamp when the clinic responded (if any).
