### 📍Yelp Big Data analysis Project (ETL Pipeline)

In this project, I leveraged the ~5GB Yelp Open Dataset by integrating tools such as Python, AWS S3, Snowflake (SQL), and Tableau to extract actionable business insights through scalable data processing and interactive visualizations.

---

### 1️⃣ Project Abstract and Objective

This project aimed to build an end-to-end data pipeline by integrating **cloud services**, a **data warehouse**, and a **BI tool**. I engineered a scalable workflow by splitting Yelp’s large JSON dataset with **Python**, storing it in **AWS S3**, and querying it in **Snowflake** using **SQL** to extract key business insights such as review trends, ratings, and regional performance. Finally, I visualized the results in **Tableau** to support data-driven decision making by stakeholders.

---

### 2️⃣ Dataset Used

- Yelp's Open Source Data (https://business.yelp.com/data/resources/open-dataset/
- yelp_academic_dataset_review.json (5.34GB)
- yelp_academic_dataset_business.json (118.9MB)

### 🗂️ Yelp Review Table Schema (`yelp_academic_dataset_review`)

| Column Name   | Data Type        | Description                                                                 |
|---------------|------------------|-----------------------------------------------------------------------------|
| `BUSINESS_ID` | `VARCHAR`        | Unique identifier for the business                                          |
| `REVIEW_DATE` | `DATE`           | Date when a user posted a review                                            |
| `USER_ID`     | `VARCHAR`        | ID of users                                                                 |
| `REVIEW_STARS`| `NUMBER`         | Star rating given in the review (1.0 to 5.0)                                |
| `REVIEW_TXT`  | `VARCHAR`        | Review comments that a user created                                         |
| `SENTIMENTS`  | `VARCHAR`        | Sentiment of comments by users (Positive or Negative)                       |

### 🏢 Yelp Business Table Schema (`yelp_businesses`)

| Column Name    | Data Type        | Description                                                                  |
|----------------|------------------|------------------------------------------------------------------------------|
| `BUSINESS_ID`  | `VARCHAR`        | Unique identifier for each business                                          |
| `NAME`         | `VARCHAR`        | Name of the business (possible duplicate)                                    |
| `CITY`         | `VARCHAR`        | City where the business is located                                           |
| `STATE`        | `VARCHAR`        | State where the business is located                                          |
| `REVIEW_COUNT` | `VARCHAR`        | Total number of reviews the business has received                            |
| `STARS`        | `NUMBER`         | Average star rating the business has received                                |
| `CATEGORIES`   | `VARCHAR`        | Comma-separated list of business categories                                  |
| `OPEN`         | `NUMBER`         | Status whether business is open or permantely closed                         |


---

## 📦 3. Dataset Used

---

## 🛠️ 4. Tech Stack & Skills Used

- **SQL (Snowflake)**: 데이터 정제, 전처리, 다중 Join 및 View 생성
- **Tableau**: 대시보드 제작 및 시각화
- **Python (Pandas, JSON)**: 초기 데이터 가공
- **Git/GitHub**: 프로젝트 버전 관리
- **데이터 모델링**: 다대다 관계 정규화, Lateral Join 활용
- **데이터 시각화**: 필터 기반 탐색형 분석 대시보드

---

## 🏗️ 5. Architecture & Workflow

```text
[Yelp Raw JSON Data]
        ⬇️ (Python)
[Transformed CSV Files]
        ⬇️ (Snowflake Stage Upload)
[Snowflake Tables]
        ⬇️ (SQL Views with JOINs / Aggregation)
[Snowflake Views]
        ⬇️ (Live Connection)
[Tableau Dashboards]
