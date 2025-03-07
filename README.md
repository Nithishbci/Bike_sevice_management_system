# Bike Service Management

## FUNCTIONS

### Customer
1. Customer will signup and login into system.
2. Customer can make request for service of their vehicle by providing details (vehicle number, model, problem description, etc.).
3. After request is approved by admin, customer can check cost and status of service.
4. Customer can delete request (Enquiry) if they change their mind or if not approved by admin (ONLY PENDING REQUESTS CAN BE DELETED).
5. Customer can check status of request (Enquiry) that is Pending, Approved, Repairing, Repairing Done, Released.
6. Customer can check invoice details of repaired vehicles.
7. Customer can send feedback to admin.
8. Customer can see/edit their profile.

### Mechanic
1. Mechanic will apply for a job by providing details like skills, address, mobile, etc.
2. Admin will hire (approve) mechanic accounts based on skill.
3. After account approval, mechanic can login into the system.
4. Mechanic can see how many work (vehicles to repair) is assigned to them.
5. Mechanic can change status of service ('Repairing', 'Repairing Done') according to work progress.
6. Mechanic can see salary and how many vehicles they have repaired so far.
7. Mechanic can send feedback to admin.
8. Mechanic can see/edit their profile.

### Admin
1. First, admin will login (for username/password, run the following command in CMD):
   ```
   py manage.py createsuperuser
   ```
2. Provide username, email, and password to create an admin account.
3. After login, admin can see the number of customers, mechanics, and recent service orders on the dashboard.
4. Admin can see/add/update/delete customers.
5. Admin can see each customer invoice (if two requests are made by the same customer, it will show the total sum of both requests).
6. Admin can see/add/update/delete mechanics.
7. Admin can approve (hire) mechanics (requested by mechanic) based on their skills.
8. Admin can see/update mechanic salary.
9. Admin can see/update/delete request/enquiry for service sent by customer.
10. Admin can also make request for service (suppose customer directly reached to service center/office).
11. Admin can approve request for service made by customer and assign to mechanic for repairing, and will provide cost according to problem description.
12. Admin can see all service costs of requests (both approved and pending).
13. Admin can see feedback sent by customers/mechanics.

### Other Features
1. We can change the theme of website: Day (White) and Night (Black).
2. If a customer is deleted by admin, their request (Enquiry) will be deleted automatically.

## HOW TO RUN THIS PROJECT
1. Install Python (3.7.6) (Don't forget to tick **Add to Path** while installing Python).
2. Open Terminal and execute the following commands:
   ```
   pip install django==3.0.5
   pip install django-widget-tweaks
   ```
3. Download the project ZIP folder and extract it.
4. Move to the project folder in Terminal, then run the following commands:
   ```
   py manage.py makemigrations
   py manage.py migrate
   py manage.py runserver
   ```
5. Now enter the following URL in your browser:
   ```
   http://127.0.0.1:8000/
   ```

## DEPLOYMENT ON AWS
1. Select the 'Deployment' - an Ubuntu server EC2 instance.
2. Launch it.
3. Upload database files in `.db` to RDS.
4. Create an S3 bucket and upload the images and media files.
5. Connect to the Ubuntu server EC2 instance.
6. Run `sudo apt-get update`.
7. Run `git clone <repository-link>`.
8. Change directory: `cd Bike_Service_Management_System`.
9. Run `sudo apt install python3-pip -y`.
10. Run `sudo pip install --break-system-packages -r requirements.txt`.
11. Run `python3 manage.py makemigrations`.
12. Run `python3 manage.py migrate`.
13. Run `python3 manage.py runserver 0.0.0.0:8000`.
14. Set security rules to **Custom TCP port 8000** with **Any IPv4 (0.0.0.0/0)** in the AWS security group of the instance.
15. Open browser and enter the instance IP address (e.g., `52.55.15.88:8000`).
