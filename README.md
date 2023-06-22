# Linkedin-User-Notification

#### **Poblem Statement:** Send notification to User (recipient) in every 3 hours with the number of unread notification and unread messages from LinkedIn profile to the recipient Gmail Account
The email body should have:
1. Number of unread Messages
2. Number of unread Notification
3. Comparison between the current data with the previous occurrence data
___________________________________________________________________________________________________________________________________________________________

# Methodology
The methodology used in the above code follows these steps to automate sending notifications from LinkedIn to a recipient's Gmail account:

# 1. Importing Required Libraries:
   - The necessary libraries such as `time`, `openpyxl`, `selenium`, `smtplib`, and related modules are imported to enable various functionalities.

# 2. Defining Reusable Functions:
   Several functions are defined to handle specific tasks. These functions include:
   - `login_to_linkedin`: This function takes a username and password, launches a headless Chrome browser using Selenium, navigates to the LinkedIn login page, enters the credentials, and logs in.
   - `get_unread_messages`: This function navigates to the LinkedIn messaging page and retrieves the number of unread messages by scraping the page's HTML.
   - `get_unread_notifications`: This function navigates to the LinkedIn notifications page and retrieves the number of unread notifications by scraping the page's HTML.
   - `save_data_to_excel`: This function appends the number of unread messages and notifications to an Excel file for future reference.
   - `send_email_notification`: This function sends an email notification to a recipient's email address using SMTP. It constructs an email message with the number of unread messages and notifications in the body.

# 3. Main Script Execution:
   - Configuration: Relevant configurations such as LinkedIn credentials, recipient emails, Excel file name, SMTP server details, sender email, and sender password are defined.
   - Loop through LinkedIn Users: The script iterates over the LinkedIn user credentials provided, logs in to each LinkedIn account using the `login_to_linkedin` function, retrieves the number of unread messages and notifications using the respective functions, saves the data to Excel using `save_data_to_excel`, and then quits the browser session.
   - Loop through Recipient Emails: The script iterates over the recipient email addresses provided, calculates the sum of unread messages and notifications from all LinkedIn users using data from the Excel file, and sends an email notification to each recipient using `send_email_notification`.

___________________________________________________________________________________________________________________________________________________________

# The components used in the code are as follows:

- Python: The programming language used for scripting the automation tasks and integrating the different components.
- Selenium: A powerful web automation framework that interacts with the LinkedIn website, performs actions such as logging in, navigating to specific pages, and scraping data by inspecting HTML elements.
- Excel (openpyxl): The openpyxl library allows reading from and writing to Excel files. It is used to store and retrieve the number of unread messages and notifications for future reference.
- SMTP: The SMTP library is used to establish a connection with the SMTP server (e.g., Gmail) and send email notifications to recipients.
- HTML: The HTML language is used to construct the email body with an impressive layout, displaying the number of unread messages and notifications.
