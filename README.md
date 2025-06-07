Step 1: Creating a Maven Project

You can create a Maven project using the mvn command (or through your IDE, as mentioned earlier). But here, I’ll give you the essential pom.xml and Java code.
Let’s use the Apache Commons Lang library as a dependency (which provides utilities for working with strings, numbers, etc.). We will use this in a simple Java program to work with strings.
mvn archetype:generate -DgroupId=com.example -DartifactId=myapp -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
BCSL657D Program 2 CMD
Note: See in your terminal below the project folder path showing after executing the cmd manually navigate the path and see the project folder name called myapp.

Step 2: Open The pom.xml File

You can manually navigate the project folder named call myapp and open the file pom.xml and copy the below code and paste it then save it.
In case if you not getting project folder then type command in your cmd.
cd myapp – is use to navigate the project folder.
notepad pom.xml – is use to open pom file in notepad.
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>myapp</artifactId>
    <version>1.0-SNAPSHOT</version>

    <dependencies>
        <!-- JUnit Dependency for Testing -->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.13.2</version>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <!-- Maven Surefire Plugin for running tests -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-surefire-plugin</artifactId>
                <version>2.22.2</version>
                <configuration>
                    <redirectTestOutputToFile>false</redirectTestOutputToFile>
                    <useSystemOut>true</useSystemOut>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
Step 3: Open Java Code (App.java) File

Open a file App.java inside the src/main/java/com/example/ directory.
After opening the App.java copy the below code and paste it in that file then save it.
package com.example;

public class App {

    public int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        App app = new App();

        int result = app.add(2, 3);
        System.out.println("2 + 3 = " + result);

        System.out.println("Application executed successfully!");
    }
}
Step 4: Open Java Code (AppTest.java) File

Open a file AppTest.java inside the src/test/java/com/example/ directory.
After opening the AppTest.java copy the below code and paste it in that file then save it.
package com.example;

import org.junit.Assert;
import org.junit.Test;

public class AppTest {

    @Test
    public void testAdd() {
        App app = new App();
        int result = app.add(2, 3);

        System.out.println("Running test: 2 + 3 = " + result);

        Assert.assertEquals(5, result);
    }
}
Note: before building the project make sure you are in the project folder if not navigate the project folder type command in your command prompt cd myapp

Step 4: Building the Project

To build and run this project, follow these steps:

Compile the Project
mvn compile
,
mvn test
 ,
mvn package

,
java -cp target/myapp-1.0-SNAPSHOT.jar com.example.App
