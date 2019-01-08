package com.ridecell;



import java.util.concurrent.TimeUnit;



import org.openqa.selenium.By;

import org.openqa.selenium.WebDriver;

import org.openqa.selenium.WebDriver.Navigation;

import org.openqa.selenium.chrome.ChromeDriver;

import org.openqa.selenium.firefox.FirefoxDriver;



public class RideCellRequestTest {

private static WebDriver driver;

private static String baseUrl;



public static void main(String[] args) throws Exception {

String username = "qa+ridertest@ridecell.com";

String password = "123456qa";



//WebDriver driver = new FirefoxDriver();

WebDriver driver = new ChromeDriver();

String appUrl = "https://release.ridecell.com/request";





//driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);

//(driver) WebDriver driver.navigate())).GoToUrl("https://release.ridecell.com/request");

driver.get(appUrl);

//driver.get("https://release.ridecell.com/request");



driver.manage().window().maximize();



driver.findElement(By.id("username")).sendKeys(

"qa+ridertest@ridecell.com");



// driver.findElement(By.id("next")).click();



driver.findElement(By.id("password")).sendKeys("123456qa");

driver.findElement(By.id("loginButton")).click();


driver.findElement(By.id("menu-home")).click();






driver.manage().timeouts().implicitlyWait(60, TimeUnit.SECONDS);



driver.findElement(By.id("request-from")).sendKeys(

"514 Bryant St,San Francisco,CA 94107");



driver.findElement(By.id("request-to")).sendKeys(

"123 Townsend St, San Francisco, CA 94107");



driver.findElement(By.id("request-button")).click();



System.out

.println("RideCell Rider request sent Successfully,Searching for nearest ride available");



driver.close();

}





}
