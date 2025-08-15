Pydantic Patient Data Model
This project demonstrates the use of Pydantic for data validation and settings management using a Patient data model. It defines the structure for patient information, including type hints and validation rules.

🚀 Features
Strict Data Typing: Ensures that fields like name, email, age, and weight adhere to their defined types (e.g., str, EmailStr, int).

Value Constraints: Applies validation rules, such as max_length for strings and greater-than/less-than constraints for numbers.

Complex Types: Handles nested data structures like lists (allergies) and dictionaries (contact_details).

Optional Fields: Allows certain fields like married and allergies to be optional with default values.

Automatic Type Coercion: Pydantic intelligently converts compatible types, such as a string "30" into an integer 30 for the age field.

📋 The Patient Model
The Patient model is defined with the following fields:

Field

Type

Description

Constraints / Examples

name

str

The full name of the patient.

max_length=50, e.g., 'Nitish'

email

EmailStr

The patient's email address.

Must be a valid email format.

linkedin_url

AnyUrl

The patient's LinkedIn profile URL.

Must be a valid URL.

age

int

The patient's age in years.

Must be between 1 and 119 (gt=0, lt=120).

weight

float

The patient's weight in kilograms.

Must be a positive number (gt=0).

married

Optional[bool]

The marital status of the patient.

True, False, or None (default).

allergies

Optional[List[str]]

A list of known allergies.

Max 5 items (max_length=5), e.g., ['Pollen', 'Dust'].

contact_details

Dict[str, str]

A dictionary for contact information.

e.g., {'phone': '123-456-7890'}

⚙️ Installation
Before running the script, you need to install Pydantic.

pip install pydantic

▶️ How to Run
Save the code into a file named main.py.

Run the script from your terminal:

python main.py

Example Output
When you run the script, it will validate the patient_info dictionary, create a Patient instance, and print the following details:

Patient Name: Nitish Kumar
Patient Age: 30
Allergies: ['Pollen', 'Dust']
Marital Status: Not specified
Contact Details: {'phone': '+1-234-567-8901', 'address': '123 Health St, Wellness City'}

--- Patient Data Processed ---
