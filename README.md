# MOVEINSYNC-CASE-STUDY
# Intelligent Floor Plan Management System

## Overview

This floor plan management system is designed to offer a robust solution for efficiently managing floor plans, encompassing meeting rooms along with their respective capacities. The system incorporates advanced features, including:

- **Admin Panel** : A sophisticated admin panel is implemented for seamless modification of floor plans, ensuring administrative control.
- **Conflict Resolution System** : The application boasts a conflict resolution system that intelligently considers timestamps and user roles, assigning the highest priority to the admin role for conflict resolution.
- **Version Control** : To track changes systematically, a version control mechanism is integrated. Each updated floor plan receives a unique version number, and the entire version history is managed on the server.

## Tech Stack Used

For the backend, the system leverages a powerful tech stack to ensure optimal performance and scalability. Key components include:

- **Java and Spring Boot**: Employed for backend development, providing a robust and scalable foundation.
- **H2 Database**: Act as a SQL database wrapper using Spring Boot, facilitating efficient storage.
<img width="560" alt="SPRING BOOT + H2 DATABASE" src="https://github.com/Ankit2002-code/MOVEINSYNC-CASE-STUDY/assets/91961466/8f381a0f-0ffb-4fa0-b260-b4a7a6c501fc">



On the frontend, a seamless communication process is facilitated through:

- **Python Wrapper**: Developed to communicate with the backend, enabling users to modify, retrieve, and display floor plans with ease.

## Various features

### Authentication

- **Static Authentication Setup**: The system employs a robust static authentication mechanism to control access to floor plan modifications. Specifically, only admin users are granted the authority to make changes, enhancing security and safeguarding the integrity of the floor plans ensuring only admin can update the table

<img width="866" alt="Untitled 1" src="https://github.com/Ankit2002-code/MOVEINSYNC-CASE-STUDY/assets/91961466/9c2f89d9-cd43-4526-94b1-449bb694167f">


                                         
### Cost Estimation

- **Space Complexity**: The GET operation involves reading from the database without additional space consumption. In contrast, the post operation for updating the floor plan utilizes a fixed amount of space based on the number of floors and rooms per floor.
- **Time Complexity**: The search operation for GET can take up to the number of existing versions, while the put operation, involving adding a column to the database, is executed in constant time.


![Screenshot (415)](https://github.com/Ankit2002-code/MOVEINSYNC-CASE-STUDY/assets/91961466/3761a3e9-8db8-4435-9df7-c362b32dde60)

### **Handling System Failure Cases**

- **Fault Tolerance**: Both backend and frontend are designed with high fault tolerance. Strict type checking in the UI and backend minimizes the risk of undesired input causing issues.
<img width="545" alt="Untitled 5" src="https://github.com/Ankit2002-code/MOVEINSYNC-CASE-STUDY/assets/91961466/6b247327-12c9-445d-8018-adb83e2287e9">


- **Database Consistency**: In the event of a system failure, the database remains constant. During system startup, the database can be seamlessly utilized, minimizing downtime to the system's rebooting time.

### **Object-Oriented Programming Language (OOPS)**

- **Abstraction and Encapsulation**: Robust OOPS principles are followed, with extensive abstraction in the backend. Multiple models are created to abstract and encapsulate data storage, enhancing system organization.

- **Polymorphism**: Implemented to ensure flexibility and adaptability within the codebase.
- 
- **Modularization**: The code is highly modularized, enabling easy addition of new functionality. Each feature is organized into its own class, simplifying debugging and maintenance.

- <img width="389" alt="Untitled 2" src="https://github.com/Ankit2002-code/MOVEINSYNC-CASE-STUDY/assets/91961466/11682967-62f2-4e95-95d7-59169410bb86">

### **Trade-offs in the System**

Since this was created in just less than a day there are bound to be some trade offs. 

- **UI Choice**: A CLI-style UI was chosen over a full-fledged browser UI due to the simplicity of operations.
- **Database Selection**: Opting for a simpler database solution (H2) over more advanced options like MySQL or AWS DynamoDB, considering the infrequent changes in floor plans.

  ![Screenshot (413)](https://github.com/Ankit2002-code/MOVEINSYNC-CASE-STUDY/assets/91961466/f550f934-f27e-4a2a-9c08-f8e887b4018b)


### **Error and Exception Handling**

- **Try-Catch Blocks**: Implemented at critical operations to handle potential issues. Handling parsing exceptions while serialisation and deserialisation.
- **Comprehensive Error Handling**: Covers parsing and various aspects to ensure robust application performance.

<img width="805" alt="Untitled 4" src="https://github.com/Ankit2002-code/MOVEINSYNC-CASE-STUDY/assets/91961466/afd223c9-986e-4851-be3c-f1e0ed7dbaf1">


                                              Handling backend responses in CLI

## ****Backend Installation****

### **Prerequisites**

- Java Development Kit (JDK) 11 or higher
- Maven

### **Steps**

1. **Clone the repository:**

```bash
git clone https://github.com/PreyankM/FloorPlanManagementSystem.git
cd FloorPlanManagementSystem
```

1. **Build and Run the Backend:**

```bash
cd backend
mvn clean install
mvn spring-boot:run
```

The backend will run on **`http://localhost:8080`**.

![Untitled](images/Untitled%206.png)

## ****Frontend Installation****

### **Prerequisites**

- Python 3.x

### **Steps**

1. **Install required Python packages:**

```bash
pip install requests tabulate colorama
```

1. **Run the CLI Frontend:**

```bash
cd frontend
python floor_plan_ui.py
```

Follow the prompts to interact with the Floor Plan Management System.

![Untitled](images/Untitled%207.png)

## Sample Output ScreenShots

- As admin user inputting version 1

![Untitled](images/Untitled%208.png)

- As admin user inputting version 2

![Untitled](images/Untitled%209.png)

- As user123 user inputting version 3

![Untitled](images/Untitled%2010.png)

- As admin user reading version 1

![Untitled](images/Untitled%2011.png)

- As admin user reading version 2

![Untitled](images/Untitled%2012.png)

- As admin user reading version 3(which was never added)

![Untitled](images/Untitled%2013.png)

- User reading version 1 and 2

![Untitled](images/Untitled14.png)

- Admin updating version 2(with initial and final view of the floor plan v2)

![Untitled](images/Untitled15.png)

- User unable to update floor plan

![Untitled](images/Untitled16.png)
