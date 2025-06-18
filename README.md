# Why Patients Don't Show-Up: A No-Show Appointment Analysis
![Picture of a doctor with a patient](hospital.jpg)
## 1. INTRODUCTION
This project analyzes a real-world dataset originating from Brazil, which contains records of over 110,000 individual medical appointments. The dataset is designed to examine patient attendance behavior, specifically focusing on identifying the factors that influence whether or not a patient honors their scheduled medical appointment. Each record corresponds to a single appointment and includes a range of attributes that could potentially affect attendance outcomes. These features span both categorical and numerical types, such as patient age, gender, neighborhood, and the presence of underlying health conditions like hypertension, diabetes, and alcoholism. Additionally, the data captures whether the patient received a reminder via SMS and if they are enrolled in a social welfare program (scholarship).
The primary variable of interest, labeled "No-show", serves as the target outcome. It indicates patient attendance status—where a value of "No" signifies that the patient was present for the appointment, and "Yes" indicates a missed appointment.
By exploring these variables, the project seeks to uncover actionable insights that can help healthcare providers reduce no-show rates, optimize resource allocation, and ultimately enhance the efficiency and reliability of healthcare delivery systems. Understanding what influences patient no-shows can help improve healthcare delivery and resource planning.

## 2. GOALS
By analyzing the patterns and relationships among these features, this project aims to uncover meaningful insights into what contributes to patient no-shows. These insights could help healthcare providers improve scheduling strategies, reduce missed appointments, and enhance overall patient care.

## 3. KEY QUESTIONS
- How many patients miss their appointments?
- Does age affect whether a patient shows up or not?
- Is there a difference in no-show rates between males and females?
- Do patients with health conditions like diabetes or high blood pressure miss more appointments?
- Does receiving financial help (Scholarship) affect attendance?
- Does the number of days between booking and the appointment matter?
- Do text message reminders help patients show up?

## 4. DATA COLLECTION AND PROCESSING
The data was sourced from Kaggle: **[Medical Appointment No Shows](https://www.kaggle.com/datasets/joniarroba/noshowappointments)**.

### Columns Overview:
- `PatientId`, `AppointmentID`: Unique identifiers.
- `Gender`: Patient's gender.
- `ScheduledDay`, `AppointmentDay`: Dates of scheduling and appointment.
- `Age`: Patient age.
- `Neighbourhood`: Location of the clinic.
- `Scholarship`: Indicates enrollment in welfare programs.
- `Hypertension`, `Diabetes`, `Alcoholism`, `Handcap`: Medical conditions.
- `SMS_received`: Whether a reminder SMS was sent.
- `No-show`: Whether the patient missed the appointment.

### Cleaning Steps:
- Handling missing values
- Removin duplicates
- Parsed date columns and calculated waiting days.
- Normalized column names (e.g., typo in `Handcap`).
- Converted "No-show" values to boolean (`Yes` → 1, `No` → 0).
- Removed invalid ages (e.g., negative values).

## 5. EXPLORATORY DATA ANALYSIS (EDA)
### Age Distribution of Patients

<img src="Age distribution.png" alt="Age distribution" width="875" height="600">

#### The histogram of age distribution shows that most patients are younger, with a 'radual decline in frequency as age increases. This suggests that younger individuals are more likely to seek medical appointments.

### Distribution of the 'No-show

<img src="N0 show distribution.png" alt="No show distribution" width="875" height="600">

#### Approximately 20% of patients did not show up for their appointments, indicating a significant no-show rate that could impact healthcare service efficiency.

### Relationship between Age and No-show

<img src="Age Vs No show.png" alt="Age Vs No show" width="875" height="600">

#### The plot below illustrates the distribution of ages for patients who did and did not show up for their appointments. 
#### The median age of patients who did not show up is slightly higher than those who did show up. There are some outliers in both categories, particularly among older patients who did not show up.

### No-show rates between males and females

<img src="No show by gender.png" alt="No show by gender" width="875" height="600">

#### The plot below illustrates the distribution of no-shows categorized by gender.
#### The majority of patients who showed up for their appointments are female, while a significant number of males also attended. Among those who did not show up, the proportion of females is slightly higher than that of males. The no-show rates are slightly higher for males compared to females, with around 20% of males and 19% of females not attending their appointments. ####

### 
- Analyzed distributions of age, gender, medical conditions, and SMS reminders.
- Plotted no-show rates by demographic and medical factors.
- Investigated temporal patterns (day of week, waiting time).
- Grouped neighborhoods by highest/lowest no-show rates.

## 6. KEY INSIGHTS
- **No-show rate** was approximately **20%**.
  
- **Shorter waiting time** between scheduling and appointment increased attendance.
- **Receiving an SMS** slightly improved show-up probability.
- Patients with **hypertension or diabetes** were **more likely** to show up.
- Some neighborhoods had significantly **higher no-show rates**, possibly due to socioeconomic differences.
- **Younger patients** and those without chronic illnesses had higher no-show rates.

## ⚠️ Limitations
- No data on reasons for missing appointments (e.g., emergencies, transportation).
- "No-show" column is labeled counter-intuitively (`No` = Showed up).
- The dataset is limited to one region in Brazil and may not generalize globally.
- Potential biases in data collection or unrecorded factors (e.g., weather, clinic capacity).

## ✅ Recommendations
- **Automated SMS reminders** should be expanded, especially for high-risk groups.
- Implement **confirmation systems** for long waiting times to reduce forgotten appointments.
- Prioritize **education campaigns** in high no-show neighborhoods.
- Consider **telemedicine or mobile health** options for patients with accessibility issues.

## 🧾 Conclusion
This analysis revealed several meaningful patterns in medical appointment behavior. It shows that factors such as SMS reminders, waiting time, age, and medical history can influence attendance. These findings can guide interventions to reduce no-shows and improve healthcare delivery.

## 🔄 Next Steps
- Build a **predictive model** to identify patients at high risk of missing appointments.
- Integrate external data (e.g., weather, public transport) for deeper analysis.
- Collaborate with healthcare providers to implement and test recommendations.

## 📎 Appendices
- **Data Source:** [Kaggle Medical Appointment No Shows](https://www.kaggle.com/datasets/joniarroba/noshowappointments)
- **Tools Used:** Python, Pandas, Matplotlib, Seaborn, Jupyter Notebook
- **File:** `KaggleV2-May-2016.csv`  
- **Notebook:** `medical_no_show_analysis.ipynb`
  
