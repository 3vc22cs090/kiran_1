3
package com.example;
import com.google.gson.Gson;
public class Main
{
 public static void main(String args[])
 {
 Gson gson= new Gson();
 String json= gson.toJson(new Person("john",30) );
 System.out.println(json);
 }
}
class Person
{
 private String name;
 private int age;
 public Person(String name, int age)
 {
 this.name=name;
 this.age=age;
 }
} 

5A
/* WebsPageTest.java */
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;
import static org.testng.Assert.assertTrue;
public class WebPageTest
{
 private static WebDriver driver;
 @BeforeTest
 public void openBrowser() throws InterruptedException
 {
 driver = new ChromeDriver();
 driver.manage().window().maximize();
 Thread.sleep(2000);
 driver.get("https://sarvarbegum-coder.github.io/LAB_1/");
 }
 @Test
 public void titleValidationTest()
 {
 String actualTitle = driver.getTitle();
 String expectedTitle = "My simple website";
 Assert.assertEquals(actualTitle, expectedTitle);
 assertTrue(true, "Title should contain 'simple'");
 }
 @AfterTest
 public void closeBrowser() throws InterruptedException
 {
 Thread.sleep(1000);
 driver.quit();
 }
}
5B
<distributionManagement>
 <repository>
 <id>local-repo</id>
 <url>file:///D:/my-local-maven-repo</url>
 </repository>
</distributionManagement>

7
jar
{
 manifest
 {
 attributes('Main-Class': 'com.example.Main')
 }
} 
