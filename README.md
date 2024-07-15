# Work_projects
### Projects and reports done in Previous job 
## End-to-End Project Description for Java Full Stack Developer: Pavan Appani
# Project Overview
# End-to-End Project Description for Java Full Stack Developer: Pavan Appani

## Project Overview
Pavan Appani is a proficient Java full-stack developer with a background in Java development, SAP integration, and data science. This project demonstrates Pavan's expertise by showcasing a comprehensive application development process from front-end design to back-end integration. The application developed is a "Task Management System" that helps teams manage and track their tasks efficiently. This system includes user authentication, task assignment, status tracking, and reporting features.

## Technologies Used
- **Front-End:** HTML, CSS, JavaScript, Angular
- **Back-End:** Java, Spring Boot, REST APIs
- **Database:** MySQL
- **Tools & Libraries:** Maven, Hibernate, JUnit
- **Integration:** SAP, using JCo (Java Connector)
- **Data Visualization:** Tableau, Power BI

## Project Modules
### User Authentication Module
**Description:**  
The user authentication module handles user registration, login, and role-based access control.

### Task Management Module
**Description:**  
This module allows users to create, assign, and manage tasks. It includes features for setting deadlines, priority levels, and tracking task progress.

### Reporting Module
**Description:**  
The reporting module generates reports on task statuses, user activity, and overall project progress. It uses Tableau and Power BI for data visualization.

### SAP Integration Module
**Description:**  
This module integrates the task management system with SAP using the Java Connector (JCo). It facilitates seamless data exchange between the application and SAP systems.

## Project Setup
1. **Clone the Repository:**
   ```sh
   git clone https://github.com/yourusername/your-repo-name.git
   cd your-repo-name

Front-End Code (Angular)
HTML (login.component.html):
-------

### Backend Setup:

**Install Java and Maven.**
**Navigate to the backend directory.**

## Frontend Setup:

**Install Node.js and Angular CLI.**
**Navigate to the frontend directory.**

### Database Setup:

## Install MySQL.
**Description**
Create a database and configure the application.properties file in the backend with your database credentials.
Run database migrations (if any).
## Usage
- **Access the application at http://localhost:4200.**
- **Register a new user or log in with existing credentials.**
- **Use the task management features to create, assign, and track tasks.**
- **Generate reports through the reporting module.**
- **Utilize the SAP integration for enhanced data synchronization.**

2. **Set UP**
 ```sh
 <div class="login-container">
  <h2>Login</h2>
  <form (ngSubmit)="onSubmit()">
    <div class="form-group">
      <label for="username">Username:</label>
      <input type="text" id="username" [(ngModel)]="username" name="username" required>
    </div>
    <div class="form-group">
      <label for="password">Password:</label>
      <input type="password" id="password" [(ngModel)]="password" name="password" required>
    </div>
    <button type="submit">Login</button>
  </form>
</div>
------


## TypeScript (login.component.ts):

```sh
import { Component } from '@angular/core';
import { AuthService } from '../services/auth.service';

@Component({
  selector: 'app-login',
  templateUrl: './login.component.html'
})
export class LoginComponent {
  username: string;
  password: string;

  constructor(private authService: AuthService) {}

  onSubmit() {
    this.authService.login(this.username, this.password).subscribe(response => {
      console.log('User logged in:', response);
    });
  }
}
------

## Back-End Code (Spring Boot)
**Controller (AuthController.java):**
```sh
@RestController
@RequestMapping("/api/auth")
public class AuthController {

    @Autowired
    private AuthService authService;

    @PostMapping("/login")
    public ResponseEntity<?> login(@RequestBody LoginRequest loginRequest) {
        String token = authService.authenticateUser(loginRequest);
        return ResponseEntity.ok(new JwtResponse(token));
    }
}
------

## Service (AuthService.java):
```sh
@Service
public class AuthService {

    @Autowired
    private AuthenticationManager authenticationManager;

    @Autowired
    private JwtUtils jwtUtils;

    public String authenticateUser(LoginRequest loginRequest) {
        Authentication authentication = authenticationManager.authenticate(
            new UsernamePasswordAuthenticationToken(loginRequest.getUsername(), loginRequest.getPassword())
        );
        SecurityContextHolder.getContext().setAuthentication(authentication);
        return jwtUtils.generateJwtToken(authentication);
    }
}
-----
