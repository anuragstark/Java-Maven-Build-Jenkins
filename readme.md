# Jenkins Java Maven Build Project

A simple Java application demonstrating CI/CD pipeline using Jenkins, Maven, and GitHub integration on CentOS.

## Project Overview

This project showcases a basic CI/CD workflow by building a Java "Hello World" application using Jenkins as the automation server, Maven for build management, and GitHub for source control management (SCM).

## Technology Stack

- **Operating System**: CentOS
- **CI/CD Platform**: Jenkins
- **Build Tool**: Maven 3.8.6
- **Source Control**: GitHub SCM
- **Programming Language**: Java
- **Project Type**: Maven-based Java application

## Project Structure

```
hello-java-maven/
├── src/
│   └── main/
│       └── java/
│           └── HelloWorld.java
├── pom.xml
├── screenshots
└── README.md
```

## Prerequisites

Before running this project, ensure you have the following installed on your CentOS system:

- **Java JDK 17**
- **Maven 3.8.6**
- **Jenkins** (latest LTS version)
- **Git** (for GitHub integration)

## Setup Instructions

### 1. Application Setup

The project contains a simple Java application:

**HelloWorld.java**
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}
```

**pom.xml** - Maven configuration file with compiler plugin setup for Java 17 compatibility.

### 2. Jenkins Configuration

#### Global Tool Configuration
1. Navigate to **Manage Jenkins** → **Global Tool Configuration**
2. Add **Maven 3.8.6** installation
3. Configure **JDK** if not already set up

#### Job Configuration
1. Create a new **Freestyle Project**
2. Configure **Source Code Management**:
   - Select **Git**
   - Add your GitHub repository URL
   - Configure credentials if repository is private
3. **Build Configuration**:
   - Add build step: **Invoke top-level Maven targets**
   - Set Maven Goals: `clean package`
4. Save the configuration

### 3. Build Execution

1. Click **Build Now** to trigger the build
2. Monitor the **Console Output** for build progress
3. Successful build will display: `BUILD SUCCESS`

## ✅ Expected Output

Upon successful execution, you should see:

```
Downloaded from central: https://repo.maven.apache.org/maven2/org/apache/commons/commons-compress/1.19/commons-compress-1.19.jar (615 kB at 146 kB/s)

[INFO] Building jar: /var/lib/jenkins/workspace/hello-java-maven/target/hello-1.0.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 21.118 s
[INFO] Finished at: 2025-08-15T21:46:56+05:30
[INFO] ------------------------------------------------------------------------
[hello-java-maven] $ /bin/sh -xe /tmp/jenkins13034981825531428764.sh
+ java -jar target/hello-1.0.jar
Hello, Jenkins + Maven by anurag
Finished: SUCCESS
```

**Key Output Details:**
- Maven successfully downloads dependencies (like commons-compress)
- JAR file built at: `/var/lib/jenkins/workspace/hello-java-maven/target/hello-1.0.jar`
- Build completed in **21.118 seconds**
- Application executed successfully displaying: `Hello, Jenkins + Maven by anurag`

## Learning Objectives Achieved

- ✅ Set up Jenkins on CentOS environment
- ✅ Configured Maven 3.8.6 for Java builds
- ✅ Integrated GitHub SCM with Jenkins
- ✅ Created and executed a Jenkins Freestyle job
- ✅ Successfully built a Java application using Maven
- ✅ Demonstrated basic CI/CD pipeline concepts

## 🔍 Key Features

- **Automated Build Process**: Jenkins automatically pulls code from GitHub and builds using Maven
- **Clean Build Environment**: Uses `clean package` goals to ensure fresh builds
- **Cross-platform Compatibility**: Java application can run on any system with JVM
- **Version Control Integration**: Seamless integration with GitHub for source code management



## Contributing

This is a learning project demonstrating basic Jenkins CI/CD concepts. Feel free to fork and experiment with additional features!

---
