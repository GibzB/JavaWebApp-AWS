# NextWork Web Application

This repository contains the source code for the NextWork web application, a Java-based project built using Maven.

## Project Overview

The NextWork web application is designed to [briefly describe the application's purpose, e.g., a simple web interface for managing tasks]. This project demonstrates a basic CI/CD pipeline setup, utilizing Git for version control and GitHub for remote repository management.

## Technologies Used

* **Java:** The primary programming language used for the web application's backend.
* **Maven:** A build automation tool used to manage project dependencies and build the application.
* **Git:** A distributed version control system for tracking changes to the source code.
* **GitHub:** A web-based platform for hosting and collaborating on Git repositories.
* **Amazon EC2:** A cloud computing service used to host the web application.
* **VSCode with Remote-SSH:** An IDE used for remote development and editing files on the EC2 instance.

## Getting Started

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/GibzB/JavaWebApp-AWS.git
    ```
2.  **Build the application using Maven:**
    ```bash
    mvn clean install
    ```
3.  ****Deploy the application:**
    * **Deploying to EC2:**
        * After building the application with Maven, the resulting `.war` file will be located in the `target/` directory.
        * Copy this `.war` file to your EC2 instance. You can use `scp` for this:
            ```bash
            scp target/nextwork-web-project.war ec2-user@[your-ec2-public-ip]:/home/ec2-user/
            ```
            (Replace `[your-ec2-public-ip]` with your EC2 instance's public IP address.)
        * On your EC2 instance, deploy the `.war` file to a web server like Apache Tomcat. If Tomcat is installed, place the `.war` file in the `webapps/` directory:
            ```bash
            sudo mv nextwork-web-project.war /var/lib/tomcat9/webapps/
            ```
            (Tomcat will automatically extract and deploy the application.)
        * Ensure your EC2 instance's security group allows inbound traffic on port 8080 (or the port Tomcat is configured to use).
4. **Access the application:**
    * Once the application is deployed, you can access it via your EC2 instance's public DNS or IP address, followed by the application's context path. For example:
        ```
        http://[your-ec2-public-dns]:8080/nextwork-web-project/
        ```
        (Replace `[your-ec2-public-dns]` with your EC2 instance's public DNS.)
    * if you have a load balancer, use the load balancers dns name, rather than the ec2 instance's public dns.
4. **Access the application:**
    * [Include access instructions, such as the URL to access the deployed application]

## Project Structure

* `src/`: Contains the source code for the web application.
    * `webapp/`: Holds the web application's files (HTML, JSP, etc.).
    * `resources/`: Contains configuration files.
* `pom.xml`: Maven project configuration file.

## Version Control

This project uses Git for version control. All changes are tracked and managed through Git commits and branches. The `master` branch contains the stable, production-ready code.

## Contributing

Contributions to this project are welcome. Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Commit your changes.
4.  Push your changes to your fork.
5.  Submit a pull request.

## License

