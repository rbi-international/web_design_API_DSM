# IPL Web Application

This project integrates the **IPL API** from the previous project with a web interface to create an interactive and user-friendly application for viewing IPL statistics.

---

## **Integration Overview**

The previous project (IPL API) serves as the backend to fetch data, while this project adds a web interface using Flask and HTML templates for user interaction.

### **How it Works**
1. The backend (`http://127.0.0.1:5000`) provides API endpoints for IPL data:
   - `/api/teams` - Fetches a list of IPL teams.
   - `/api/teamvteam` - Fetches head-to-head statistics for two teams.
   
2. The frontend application (`http://127.0.0.1:8000`) uses these APIs to:
   - Display the list of IPL teams.
   - Allow users to select two teams and view their match records.

---

## **Setup and Usage**

### **Step 1: Run the IPL API Backend**
1. Clone the repository for the **IPL API** project.
2. Install the required dependencies:
   ```bash
   pip install flask pandas numpy
   ```
3. Start the backend server:
   ```bash
   python app.py
   ```
4. The backend will be available at `http://127.0.0.1:5000`

Step 2: Run the Web Application
1. Clone this repository.
2. Install the required dependencies:
   ```bash
   pip install flask requests
   ```
3. Start the frontend server:
   ```bash
   python app.py
   ```
The web application will be available at `http://127.0.0.1:8000`

# Frontend Application Details

## **Routes**
- `/`:
  - Displays a dropdown of IPL teams.
  - Allows users to select teams for comparison.

- `/teamvteam`:
  - Accepts user input for two teams.
  - Fetches head-to-head statistics using the backend API.
  - Displays the results.

---

## **Templates**
- `index.html`:
  - The main page where users can:
    - Select two teams from a dropdown menu.
    - View their head-to-head match record.

---

## **Integration Flow**
### **Frontend Calls Backend**
1. The `/` route:
   - Calls `http://127.0.0.1:5000/api/teams` to fetch the list of teams.
   - Populates the dropdown menus with the fetched data.
   
2. The `/teamvteam` route:
   - Calls `http://127.0.0.1:5000/api/teamvteam`.
   - Fetches match records between the selected teams.

### **Data Rendering**
- The fetched data is passed to the `index.html` template.
- Results are dynamically displayed based on user input.

---

## **Key Features**
- User-friendly dropdown menu for selecting teams.
- Integration of APIs with Flask for seamless data communication.
- Dynamic rendering of match records based on selected teams.

---

## **Example Usage**
1. **Launch the Web Application**:
   - Navigate to `http://127.0.0.1:8000` in your browser.

2. **Select Teams**:
   - Choose two teams from the dropdown menu.
   - Click "Find Track Record."

3. **View Results**:
   - Head-to-head statistics will be displayed below the form.

---

## **Requirements**
- Python 3.8+
- Flask
- Pandas, Numpy (for backend API)
- Requests (for frontend integration)

---

## **Future Enhancements**
1. Add more detailed statistics like batting and bowling records.
2. Enhance the UI with CSS frameworks like **Bootstrap** or **Tailwind CSS**.
3. Expand API integration to include more endpoints.


Folder Structure
```bash
├── app.py            # Frontend Flask app
├── templates
│   └── index.html    # Main HTML template
└── README.md         # Documentation file
```
