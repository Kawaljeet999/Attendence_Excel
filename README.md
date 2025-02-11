# **Attendance_Excel**  

## **Introduction**  
The sole purpose of this project is to **automate student attendance** by processing an **image containing student College IDs (in numbers)** and storing the extracted data in an **Excel file**.  

### **How It Works**  
- The **frontend** allows the user to input:  
  ✅ **Class Date**  
  ✅ **Time**  
  ✅ **Year**  
  ✅ **Subject**  
  ✅ **Image File (PNG/JPG) containing Student College IDs**  
- Upon form submission, the **backend** processes the image using **OCR (pytesseract & easyocr)** and updates the corresponding **Excel file** (e.g., `A.xlsx`, `B.xlsx`).  

---

## **Requirements**  
⚠️ **Important Considerations**:  
1️⃣ **Image Placement**: The uploaded image file **must be in the same directory** as the project’s code. Otherwise, a `FileNotFoundError` will occur.  
2️⃣ **Image Quality**:  
   - The picture should be **clear** with all numbers **bold and legible**.  
   - The OCR will **ignore any unclear or handwritten numbers**.  
   - The image **must contain only numbers**, no extra text.  
3️⃣ **Excel File Location**: The predefined **Excel files (`A.xlsx`, `B.xlsx`, etc.)** must also be present in the **same directory** as the code. The system assigns data based on the selected section.  

---

## **Tech Stack**  
🔹 **Backend**: Django (Python)  
🔹 **Frontend**: HTML, CSS, JavaScript  
🔹 **OCR**: pytesseract, easyocr  
🔹 **Excel Handling**: openpyxl  

---

## **Installation & Setup**  
### **1️⃣ Prerequisites**  
Ensure you have the following installed:  
- Python (≥3.8)  
- MySQL Server  
- Tesseract-OCR (Added to system PATH)  
- Required Python packages  

### **2️⃣ Clone the Repository**  
```sh
git clone https://github.com/Kawaljeet999/Attendence_Excel
cd Attendance_Excel
```

### **3️⃣ Install Dependencies**  
```sh
pip install -r requirements.txt
```

### **4️⃣ Configure Database**  
- Update **MySQL credentials** in the project settings.  
- Run migrations:  
  ```sh
  python manage.py makemigrations
  python manage.py migrate
  ```

### **5️⃣ Run the Server**  
```sh
python manage.py runserver
```
Access the application at **`http://127.0.0.1:8000/`**.  

---

## **Usage Guide**  
### **🔹 User Authentication**  
1. **Signup** at `/signup/`  
2. **Login** at `/login/`  

### **🔹 Attendance Marking**  
1. Upload a **clear image** containing student roll numbers.  
2. OCR extracts roll numbers and **matches them with the database**.  
3. Attendance is **recorded in the corresponding Excel file**.  

### **🔹 Excel File Structure**  
- **Sheet Name**: `Attendance_sheet`  
- **Columns**:  
  - `SName` (Student Name)  
  - `CollegeID` (Roll Number)  
  - `Date-wise Attendance` (Marked as **Present/Absent**)  

---

## **Key Functions in `views.py`**  
| Function         | Purpose |
|-----------------|---------|
| `signup_view()` | Handles user registration |
| `login_view()` | Manages user login |
| `Excelwork()` | Processes attendance in Excel |
| `takeinputs()` | Gathers attendance input parameters |
| `thankyou()` | Displays final attendance summary |

---

## **Contributing**  
Feel free to fork this repository and submit pull requests. For major changes, please open an issue first to discuss improvements.  

---

## **License**  
This project is licensed under the **MIT License**.  
