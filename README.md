experiment-1
search for selenium and testng scripts or add
 <dependencies>
 <dependency>
 <groupId>org.seleniumhq.selenium</groupId>
 <artifactId>selenium-java</artifactId>
 <version>3.141.59</version>
 </dependency>
 <dependency>
 <groupId>org.testng</groupId>
 <artifactId>testng</artifactId>
 <version>7.4.0</version>
 <scope>test</scope>
 <dependencies> section.
 </dependency>
  </dependencies>
  
  copy three files into resourse
  
  index.html
  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Simple Website</title>
    <link rel="stylesheet" href="style.css">
 </head>
<body>
<header>
    <img src="logo.png" alt="Logo">
</header>
<h1>Welcome to My Simple Website</h1>
</body>
</html>

stle.css
body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: white;
    padding: 20px;
}

.logo {
    width: 100px;
    height: auto;
}

main {
    margin: 20px;
    padding: 20px;
    background-color: white;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}

footer {
    background-color: #333;
    color: white;
    padding: 10px;
    position: fixed;
    width: 100%;
    bottom: 0;
}
command:
git init
git add .
git status
git commit -m"added index,styles,logo files for the website"
git remote add origin "paste the url"(new repo)

add plugins
<build>
 <plugins>
 <plugin>
 <groupId>org.apache.maven.plugins</groupId>
 <artifactId>maven-resources-plugin</artifactId>
 <version>3.2.0</version>
 <executions>
 <execution>
 <phase>prepare-package</phase> <!-- Before packaging -->
 <goals>
 <goal>copy-resources</goal>
 </goals>
 <configuration>
 /docs folder -->
 src/main/resources -->
 <outputDirectory>${project.basedir}/docs</outputDirectory> <!-- Deploy to
 <resources>
 <resource>
 <directory>src/main/resources</directory>
 <includes>
 <include>**/*</include> <!-- Copy all files in
 </includes>
 </plugin>paste here maven jar 
 </plugins>
  </build>
 </resource>
 </resources>
 </configuration>
 </execution>
 </executions>
 command:mvn clean install
 git status,git add .,git remote show origin
 git commit -m"added the docs folder for deployment"
 git push -u origin master

 Go to your GitHub repository.
 Navigate to Settings > Pages (on the left sidebar).
 Under the Source section, select the 
main branch and 
Click Save.

selenium test
package org.test;
 import org.openqa.selenium.WebDriver;
 import org.openqa.selenium.chrome.ChromeDriver;
 import org.testng.Assert;
 import org.testng.annotations.AfterTest;
 import org.testng.annotations.BeforeTest;
 import org.testng.annotations.Test;
 import static org.testng.Assert.assertTrue;
 public class WebpageTest {
 private static WebDriver driver;
 }
 @BeforeTest
 public void openBrowser() throws InterruptedException {
 driver = new ChromeDriver();
 driver.manage().window().maximize();
 }
 @Test
 public void titleValidationTest(){
 }
 Thread.sleep(2000);
 driver.get("https://sauravsarkar-codersarcade.github.io/CA-MVN/"); // "Note: You should
 use your GITHUB-URL here...!!!"
 String actualTitle = driver.getTitle();
 String expectedTitle = "Tripillar Solutions";
 Assert.assertEquals(actualTitle, expectedTitle);
 assertTrue(true, "Title should contain 'Tripillar'");
 @AfterTest
 public void closeBrowser() throws InterruptedException {
 Thread.sleep(1000);
 driver.quit();
 }

 In IntelliJ, right-click the WebPageTest class and select Run 'WebPageTest'

 mven jar plugin to pom.xml
  <build>
 <plugins>
 <!-- Maven JAR Plugin -->
 <plugin>
 <groupId>org.apache.maven.plugins</groupId>
 <artifactId>maven-jar-plugin</artifactId>
 <version>3.2.0</version>
 <configuration>
 <!-- Specify the main class to be executed -->
 <archive>
 <manifestEntries>
 class path -->
 </archive>
 </configuration>
 <Main-Class>com.example.MainClass</Main-Class> <!-- Replace with your main
 </manifestEntries>
 </plugin>paste here site script
 </plugins>
  </build>
  command: mvn clean package
   java -jar target/your-project-name.jar

   add site 
    <build>
 <plugins>
 <plugin>
 <groupId>org.apache.maven.plugins</groupId>
 <artifactId>maven-site-plugin</artifactId>
 </plugins>
  </build>
 <build> section of your 
<version>3.12.1</version> <!-- Use latest version -->
 </plugin>
command:mvn site

exp-3
create a project
in build gradle paste the script
 plugins {
 id 'application'
  }
 repositories {
 mavenCentral()
 }
 dependencies {
 testImplementation 'org.junit.jupiter:junit-jupiter:5.8.1'
  }
  application {
  }
 mainClass = 'com.example.Main'
command:gradle run
paste 3 files to dcs
create a new repo
command:git init
git add .
git commit -m"added the docs folder with html,style,logo for deplo"
git status
git remote add origin"paste the url"(repo)
git push -u origin master
go to sett->pages->website
add selenium and testng inside dependencies
new package(org.test)->new class(webpagetest)->paste the package
package org.test;
 import org.openqa.selenium.WebDriver;
 import org.openqa.selenium.chrome.ChromeDriver;
 import org.testng.Assert;
 import org.testng.annotations.AfterTest;
 import org.testng.annotations.BeforeTest;
 import org.testng.annotations.Test;
 import static org.testng.Assert.assertTrue;
  public class WebpageTest {
 private static WebDriver driver;
 }
 @BeforeTest
 public void openBrowser() throws InterruptedException {
 driver = new ChromeDriver();
 driver.manage().window().maximize();
 Thread.sleep(2000);
 driver.get("https://sauravsarkar-codersarcade.github.io/CA-GRADLE/");
 }
 @Test
 public void titleValidationTest(){
 String actualTitle = driver.getTitle();
 String expectedTitle = "Tripillar Solutions";
 }
 }
 Assert.assertEquals(actualTitle, expectedTitle);
 assertTrue(true, "Title should contain 'Tripillar'");
 @AfterTest
 public void closeBrowser() throws InterruptedException {
 Thread.sleep(1000);
 driver.quit();
 comm:gradle test/task ->verifin->test
modify build.gradle
 plugins {
 id 'java'
 id 'application'
 }
 application {
 mainClass = 'com.example.Main'
  }
 jar {
 manifest {
 attributes 'Main-Class': 'com.example.Main'  
}
}
com:gradle jar
java -jar build/libs/<my-gradle-project>.jar
update build,gradle


exp-4
open intel->new project->maven->create
add plugins inside project tag in pom.xml
<build>
 <plugins>
 <!-- Compiler Plugin -->
 <plugin>
 <groupId>org.apache.maven.plugins</groupId>
 <artifactId>maven-compiler-plugin</artifactId>
 <version>3.8.1</version>
 <configuration>
 <source>1.8</source>
  <target>1.8</target>
 </configuration>
 </plugin>
 <!-- Jar Plugin -->
 <plugin>
 <groupId>org.apache.maven.plugins</groupId>
 <artifactId>maven-jar-plugin</artifactId>
 <version>3.2.0</version>
 <configuration>
 <archive>
 <manifest>
 <mainClass>com.example.App</mainClass>
 </manifest>
  </archive>
 </configuration>
  </plugin>
 </plugins>
 </build>
 -com:mvn clean compile
  mvn package
  -to run the jar file
  java -jar target\MVNGRDLDEMO-1.0-SNAPSHOT.jar
  gradle init --type pom
  update build.gradle
   plugins {
 id 'java'
 }
 group = 'com.example'
 version = '1.0-SNAPSHOT'
 repositories {
 mavenCentral()
  }
  dependencies {
 testImplementation 'junit:junit:4.13.2'
 }
 jar {
 manifest {
 attributes(
 'Main-Class': 'com.example.App
 )
 }
 }
 com:gradle clean build
  java -jar build/libs/MVNGRDLDEMO-1.0-SNAPSHOT.jar
