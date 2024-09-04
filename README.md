# House Price Prediction

This project guides you through the entire process of creating a real estate price prediction website. We begin by developing a predictive model using scikit-learn and linear regression, utilizing the Bangalore House price dataset. The project involves creating a Python Flask server that will host the model and handle HTTP requests. Finally, we'll build a website using HTML, CSS, and JavaScript, where users can input details such as square footage and number of bedrooms. The website will then interact with the Flask server to retrieve the predicted price.

Throughout the model-building phase, we will explore a wide range of data science concepts, including data loading and cleaning, detecting and removing outliers, feature engineering, dimensionality reduction, hyperparameter tuning with GridSearchCV, and k-fold cross-validation.

Tools & Techniques used:
  `i)Front End - HTML, CSS, JS`
  `ii)Back End - Flask`
  `iii)Machine Learning - Regression Analysis `

### Deployment Details

- **Amazon EC2 Instance**:
  - The Flask application for house price prediction is hosted on an Amazon EC2 instance.
  - The EC2 instance was selected to ensure scalability and availability of the application.
  - **Instance Type:** (Specify the instance type, e.g., t2.micro)
  - **Region:** (Specify the AWS region, e.g., eu-north-1)
  
- **Nginx**:
  - Nginx is used as a reverse proxy to forward requests from the public internet to the Flask application running on the EC2 instance.
  - Nginx handles static file serving and provides additional security and performance optimizations.
  - The Nginx configuration ensures that the application is accessible via HTTP/HTTPS.

### Project Setup

1. **AWS EC2 Setup**:
   - Launch an EC2 instance with the desired operating system.
   - Configure security groups to allow inbound traffic on necessary ports (e.g., 80 for HTTP, 443 for HTTPS).
   - SSH into the EC2 instance to set up the environment.

2. **Nginx Configuration**:
   - Install Nginx on the EC2 instance.
   - Configure Nginx to serve as a reverse proxy for the Flask application.
   - Sample Nginx configuration:
     ```nginx
     server {
         listen 80;
         server_name your-domain.com;

         location / {
             proxy_pass http://127.0.0.1:5000;
             proxy_set_header Host $host;
             proxy_set_header X-Real-IP $remote_addr;
             proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
             proxy_set_header X-Forwarded-Proto $scheme;
         }
     }
     ```

3. **Running the Flask Application**:
   - Run the Flask application on the EC2 instance:
     ```bash
     python3 server.py
     ```
   - The application will be accessible at `http://your-ec2-public-ip` or the configured domain name.

### Usage

Visit the deployed application at [http://your-ec2-public-ip](http://your-ec2-public-ip) to interact with the house price prediction model.


  


