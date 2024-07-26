# EMail-SMS-gateway

# SMS and Email Gateway Project

This project is designed to automate the process of sending SMS and email notifications to employees on their birthdays and retirement days. It uses Flask for the backend, React for the frontend, and Twilio for sending SMS.

## Features

- Add, view, and manage employee information including name, phone number, email, location, date of birth, and retirement date.
- Automatically send SMS and email notifications on the scheduled dates.
- User-friendly interface for managing employee data.
- Automated tasks using APScheduler.

## Prerequisites

- Python 3.x
- Node.js and npm
- SQLite

## Installation

### Backend

1. Clone the repository:

   ```sh
   git clone <repository-url>
   cd <repository-directory>
   ```

2. Create a virtual environment:

   ```sh
   python -m venv venv
   ```

3. Activate the virtual environment:

   - On Windows:
     ```sh
     venv\\Scripts\\activate
     ```
   - On macOS/Linux:
     ```sh
     source venv/bin/activate
     ```

4. Install the required dependencies:

   ```sh
   pip install -r requirements.txt
   ```

5. Initialize the SQLite database:

   ```sh
   python -c "from app import init_sqlite_db; init_sqlite_db()"
   ```

6. Run the Flask server:

   ```sh
   flask run
   ```

### Frontend

1. Navigate to the frontend directory:

   ```sh
   cd frontend
   ```

2. Install the required dependencies:

   ```sh
   npm install
   ```

3. Start the React development server:

   ```sh
   npm start
   ```

## Usage

1. Open your web browser and navigate to `http://localhost:3000` to access the frontend.
2. Use the provided forms to add new employees.
3. The backend will automatically send SMS and email notifications to employees on their birthdays and retirement days.

## API Endpoints

### `GET /employees`

Fetches all employees from the database.

### `POST /add_employee`

Adds a new employee to the database. Expects a JSON payload with the following structure:

```json
{
  "name": "John Doe",
  "phone": "1234567890",
  "email": "john.doe@example.com",
  "location": "Varanasi",
  "dob": "1990-01-01",
  "retirement": "2050-01-01"
}
```

### `GET /birthdays`

Fetches all employees whose birthdays are today.

### `GET /retirements`

Fetches all employees who are retiring today.

### `POST /send_sms`

Sends an SMS to the specified phone number. Expects a JSON payload with the following structure:

```json
{
  "phone": "+911234567890"
}
```

### `POST /send_birthday_email`

Sends a birthday email to the specified email address. Expects a JSON payload with the following structure:

```json
{
  "email": "john.doe@example.com",
  "name": "John Doe"
}
```

### `POST /send_retirement_email`

Sends a retirement email to the specified email address. Expects a JSON payload with the following structure:

```json
{
  "email": "john.doe@example.com",
  "name": "John Doe"
}
```

## Project Structure

```
.
├── backend
│   ├── app.py
│   ├── employee.db
│   ├── requirements.txt
│   └── ...
├── frontend
│   ├── public
│   ├── src
│   │   ├── components
│   │   │   ├── EmployeeForm.js
│   │   │   ├── ViewEmployees.js
│   │   │   ├── TodaysBirthdays.js
│   │   │   ├── TodaysRetirements.js
│   │   │   └── ...
│   │   ├── App.js
│   │   └── ...
│   ├── package.json
│   └── ...
└── README.md
```

## Dependencies

### Backend (Python/Flask)

- Flask
- Flask-Cors
- APScheduler
- Twilio
- SQLite

### Frontend (React)

- React
- React-Bootstrap

## Running Tests

To test the endpoints, you can use tools like Postman or curl. Example JSON payloads for testing are provided in the API Endpoints section.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

This README provides an overview of the SMS and Email Gateway Project, including installation instructions, usage, API endpoints, project structure, dependencies, and more. For detailed code implementation and additional information, refer to the source files and comments within the project.

---

Copy the above content and save it as a file named `README.md` in your project directory.
