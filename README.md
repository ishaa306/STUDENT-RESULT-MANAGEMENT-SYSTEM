# Student Result Management System

A comprehensive desktop application built with Python and Tkinter that allows educational institutions to manage student results, verify certificates, and maintain student records efficiently.

## Features

### For Teachers/Administrators:
- **Secure Authentication**: Role-based login system for teachers and students
- **Dashboard Interface**: Intuitive tabbed interface for easy navigation
- **Results Management**: 
  - Upload student results via CSV files
  - View all student results in a tabular format
  - Insert sample data for testing purposes
- **Certificate Verification**: Verify student certificates for authenticity
- **Profile Management**: 
  - View and edit personal information
  - Change password with secure validation

### For Students:
- **Results Viewing**: Students can view their academic results
- **Profile Management**: Update personal information and change passwords
- **Certificate Access**: Access and download certificates

## Installation

### Prerequisites
- Python 3.6 or higher
- MySQL database

### Setup Steps
1. Clone the repository or download the source code
   ```
   git clone <repository-url>
   ```

2. Install required dependencies
   ```
   pip install -r requirements.txt
   ```

3. Set up the MySQL database
   ```
   # Create the database
   mysql -u root -p < database.sql
   
   # Or manually create using the SQL commands in database.py
   ```

4. Run the application
   ```
   python login.py
   ```

## Database Structure

The system uses MySQL database with the following tables:

1. **Users**: Stores user information including credentials and roles
   - UserID (Primary Key)
   - Username
   - Name
   - Password
   - Role (Student/Teacher)

2. **Results**: Stores student academic results
   - id (Primary Key)
   - student_id (Foreign Key to Users)
   - semester
   - exam_type
   - subject
   - marks

3. **Certificates**: Stores information about student certificates
   - id (Primary Key)
   - student_id (Foreign Key to Users)
   - certificate_name
   - verified (Boolean)
   - issue_date

## Usage Guide

### For Teachers

1. **Login**:
   - Username: teacher1
   - Password: teacher123

2. **Add Results**:
   - Upload a CSV file with columns: student_id, semester, exam_type, subject, marks
   - Use the "Insert Sample Data" button for testing purposes

3. **View Results**:
   - Click on "View Results" tab to see all student results
   - Click "Load Results" to refresh the data

4. **Verify Certificates**:
   - Select a certificate from the list
   - Click "Verify Certificate" to mark it as verified

5. **Profile Management**:
   - View and edit your profile information
   - Change your password securely

### For Students

1. **Login**:
   - Username: student1
   - Password: student123

2. **View Results**:
   - See your academic results in the dashboard
   - Filter results by semester or subject

3. **Profile Management**:
   - Update your personal information
   - Change your password

## CSV Format for Results Upload

The CSV file for uploading results should have the following columns:
- **student_id**: The ID of the student (must exist in the Users table)
- **semester**: The semester (e.g., 'Fall 2023')
- **exam_type**: The type of exam (e.g., 'Midterm', 'Final')
- **subject**: The subject name
- **marks**: The marks obtained (numeric value)

Example CSV content:
```
student_id,semester,exam_type,subject,marks
1,Fall 2023,Midterm,Mathematics,85
1,Fall 2023,Midterm,Physics,78
```

## Troubleshooting

### Database Connection Issues
- Ensure MySQL service is running
- Check database credentials in the code
- Verify that the database name is 'StudentResultDB'

### Tables Not Found
- The application attempts to create required tables automatically
- You can manually create tables using the SQL commands in the code

## Technologies Used

- **Python**: Core programming language
- **Tkinter**: GUI framework
- **MySQL**: Database management
- **Pandas**: Data handling for CSV imports
- **ttk**: Enhanced Tkinter widgets

## Future Improvements

- Data visualization for student performance trends
- Email notification system for new results
- Mobile application version
- PDF export for results and certificates
- Enhanced security features

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details. 
