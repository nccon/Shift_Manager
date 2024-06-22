Shift Planner Application - Quick Start Guide
Welcome to the Shift Planner application! Follow this guide to get started and manage shifts effectively.

Prerequisites
Ensure you have the following installed on your system:

Python 3.9+
Flask
Flask-SQLAlchemy
Flask-Login
Flask-WTF
FullCalendar (via CDN)
Configuration
Config File: Create a config.py file in the root directory with the following content:


########################################################################################################################################
import os

class Config:
    SECRET_KEY = os.environ.get('SECRET_KEY') or 'your_secret_key'
    SQLALCHEMY_DATABASE_URI = 'sqlite:///your_database.db'
    SQLALCHEMY_TRACK_MODIFICATIONS = False
    REMEMBER_COOKIE_DURATION = timedelta(days=7)
    
IP Address and Port: The application is set to run on IP address 192.168.10.43 and port 5000. You can modify this in the app.py file:

########################################################################################################################################

if __name__ == '__main__':
    with app.app_context():
        db.create_all()
    app.run(host='192.168.10.43', port=5000)

########################################################################################################################################
    
Setting Up
Install Dependencies:
Install the required Python packages by running:

pip install flask flask_sqlalchemy flask_login flask_wtf

Initialize Database:
Database will be created as soon as the app.py start:

########################################################################################################################################

Create Admin User:
Start the server and navigate to http://192.168.10.43:5000/create_admin to create an initial admin user.

########################################################################################################################################

Running the Application
Start the Server:
Run the Flask server by executing:

python app.py
Access the application at http://192.168.10.43:5000.
Using the Application
Login:

########################################################################################################################################

Navigate to the login page.
Use the admin credentials created earlier to log in.

Manage Shifts:
Access the "Manage Shifts" page from the navigation bar.
Add, edit, or delete shifts using the provided form and buttons.
Click the "Export Shifts" button to open a modal for exporting shifts based on date range, users, and specific conditions like weekends or bank holidays.

Manage Users:
Access the "Manage Users" page from the navigation bar.
Add new users, delete existing users, toggle admin status, update phone numbers, or reset passwords.

Shift Calendar:
View all scheduled shifts and bank holidays on the calendar.

Manage Shift Change Requests:
Admins can view and manage pending shift change requests.

Logs:
Admins can view request logs and export them.

Additional Information
Bank Holidays: Admins can add bank holidays through the "Manage Shifts" page. These will be displayed in the calendar.
Mobile Friendly: The application is designed to be mobile-friendly, ensuring ease of use across different devices.

Server and Notifications
The server is running on a Raspberry Pi that has serial communication with a GSM module. This module is used to notify users regarding their scheduled shifts via SMS, ensuring they are always informed about their upcoming duties.

By following this guide, you should be able to set up and start using the Shift Planner application efficiently. Enjoy managing your shifts seamlessly!
