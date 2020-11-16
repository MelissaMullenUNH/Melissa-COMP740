# READ ME

## Data Dictionary:
- **sex:** Sex of the patient, where male = 0 and female = 1.
- **patient_type:**	The type of care received by a patient, where inpatient = 0 (patient was admitted to the hospital) and outpatient = 1 (patient was sent home).
- **intubed:** Whether the patient required intubation, where no = 0 and yes = 1.
- **pneumonia:** Whether the patient was diagnosed with pneumonia, where no = 0 and yes = 1.
- **age:** The age of the patient (integer).
- **pregnancy:** Whether the patient was pregnant, where no = 0 and yes = 1.
- **diabetes:** Whether the patient was diagnosed with diabetes, where no = 0 and yes = 1.
- **copd:** Whether the patient was diagnosed with COPD, where no = 0 and yes = 1.
- **asthma:** Whether the patient was diagnosed with asthma, where no = 0 and yes = 1.
- **inmsupr:** Whether the patient is immunocompromised, where no = 0 and yes = 1.
- **hypertension:** Whether the patient was diagnosed with hypertension, where no = 0 and yes = 1.
- **other_disease:** Whether the patient has been diagnosed with other diseases, where no = 0 and yes = 1.
- **cardiovascular:** Whether the patient has been diagnosed with cardiovascular disease, where no = 0 and yes = 1.
- **obesity:** Whether the patient has been diagnosed with obesity, where no = 0 and yes = 1.
- **renal_chronic:** Whether the patient has been diagnosed with chronic kidney disease, where no = 0 and yes = 1.
- **tobacco:** Whether the patient uses tobacco, where no = 0 and yes = 1.
- **contact_other_covid:** Whether the patient had contact with anybody diagnosed with COVID-19, where no = 0 and yes = 1.
- **covid_res**: Results of COVID-19 test, where 0 is negative and 1 is positive.
- **icu:** Whether the patient required admission in the ICU, where no = 0 and yes = 1.

## Project Overview:

This dataset was released by the Mexican government on November 15th, 2020, meaning the data dictionary was originally in Spanish. After some translation, I was able to figure out what the data actually means, which I outlined above in the data dictionary. This project began with initial data cleaning, which took place in the **clean_data notebook**. After dropping irrelevant columns, I had to deal with the sloppy format of the data. Rather than having the traditional binary 0 1 format, with missing values listed as NaN, this dataset had a binary 1 2, and missing values were listed as either 97 98 or 99. In the columns where the missing values weren't important, I simply dropped all rows containing values other than 1 or 2. However, I had to be careful because in the pregnancy column males were listed as 97, so I had to manually change every 97 to 2. This same problem happened with intubed and icu columns, where patients hospitalized were listed as 97, so I changed these values to null (I have no idea whether they received intubation or were admitted to the ICU). After all this, I manually changed every 2 to 0 to fix the binary format, and loaded this new dataset to **clean_covid.csv**.

I then moved to the **project notebook**, and loaded this new dataset. 