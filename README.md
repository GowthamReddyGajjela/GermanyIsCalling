# GermanyIsCalling
# Selenium Login Automation 
This project automates the testing of the login functionality for the **Germany is Calling** web application using Selenium WebDriver and TestNG,The test scripts cover both **successful** and **unsuccessful** login attempts

## Setup 

- **Eclipse** installed IDE(https://www.eclipse.org/downloads/)
- **Java** installed JDK  (https://www.oracle.com/in/java/technologies/downloads/)

- **Maven repository**  For dependency management Testng nd Selenium WebDriver libraries nd chromebrowser(https://mvnrepository.com/) (managed through Maven)

- Create a new Maven project in IDE ( Eclipse).

  **Maven pom.xml Dependencies**:
  
- Create a pom.xml file in the root of project to manage dependencies

- This project uses Maven to manage dependencies Adding the library in pom xml flie nd save 

- **Selenium**: A browser automation library.
- **TestNG**: A testing framework used to run the tests and generate reports.


   after dependencies adding to write a test script
 
### Automated Test script with TetsngMaveenproject

package TetsngMaveen.Testng;

import org.openqa.selenium.By;

import org.openqa.selenium.chrome.ChromeDriver;

import org.testng.annotations.Test;

import io.github.bonigarcia.wdm.WebDriverManager;

public class GermanyIsCalling {

	@Test
	public void UnsuccessfulLogin() throws Exception{
		WebDriverManager.chromedriver().setup();
		ChromeDriver driver = new ChromeDriver();
		driver.manage().window().maximize();
		driver.get("https://germanyiscalling.com/");
		driver.findElement(By.xpath("//button[@class='cmplz-btn cmplz-accept']")).click();
		driver.findElement(By.xpath("//a[normalize-space()='Login / SignUp']")).click();
		Thread.sleep(1000);
		driver.findElement(By.id("username")).sendKeys("germanycalling@gmail.com");
		driver.findElement(By.id("password")).sendKeys("germany798@");
		driver.findElement(By.xpath("//button[@type='submit']")).click();
		Thread.sleep(2000);
		driver.findElement(By.id("username")).sendKeys("");
		driver.findElement(By.id("password")).sendKeys("gowtham7647");
		driver.findElement(By.xpath("//button[@type='submit']")).click();
		Thread.sleep(3000);
		driver.findElement(By.id("username")).sendKeys("Gowtham798123@gmail.com");
		driver.findElement(By.id("password")).sendKeys("");
		driver.findElement(By.xpath("//button[@type='submit']")).click();
		driver.close();

	}
	@Test
	public void SuccessfulLogin() throws Exception{
		ChromeDriver driver = new ChromeDriver();
		driver.get("https://germanyiscalling.com/");
		driver.findElement(By.xpath("//button[@class='cmplz-btn cmplz-accept']")).click();
		driver.findElement(By.xpath("//a[normalize-space()='Login / SignUp']")).click();
		Thread.sleep(1000);
		driver.findElement(By.id("username")).sendKeys("gowthamrg757@gmail.com");
		driver.findElement(By.id("password")).sendKeys("Gowtham798123@");
		driver.findElement(By.xpath("//button[@type='submit']")).click();
	}
}


### TesNg Report 

file:///C:/Users/ggowt/eclipse-workspace/Testng/test-output/index.html#

 ### TestNg xml File 
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "https://testng.org/testng-1.0.dtd">
<suite name="Suite">
  <test thread-count="5" name="Test">
    <classes>
      <class name="TetsngMaveen.Testng.GermanyIsCalling"/>
    </classes>
  </test> <!-- Test -->
</suite> <!-- Suite -->

 
#### Test reports

The results of both the successful and unsuccessful login test cases is pass

##### Additional information 

Im not facing any issue in this application 

In this application showing userfriendly nd operting also good 

I Implement th additional test cases, such as testing the login page’s response to empty fields.
