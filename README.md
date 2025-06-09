# 8pgr
FirstSelenium.java

package com.example;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class FirstSelenium {
     static WebDriver driver;

     public static void main(String[] args) {
          System.setProperty("web driver.chrome.driver","./Drivers/chromedriver.exe");
          driver =new ChromeDriver();
          driver.get("https://www.google.com");
          //driver.navigate().to("https://www.google.com");
          driver.quit();
     }

}



GetTitleAndUrl.java

package com.example;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;


public class GetTitleAndUrl {
    static WebDriver driver;

 public static void main(String[] args) {
        System.setProperty("web driver.chrome.driver", "./Drivers/chromedriver.exe");
        driver = new ChromeDriver();
        driver.get("https://www.google.com");
        driver.navigate().to("https://www.bietdvg.edu/");
        String url = driver.getCurrentUrl();
        String title = driver.getTitle();
        System.out.println("The url is: "   +url );
        System.out.println("The title is: " + title);
        driver.quit();
    }
}

BrowserInSelenium.java

package com.example;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class BrowserInSelenium {
    static WebDriver driver;

    public static void main(String[] args) throws InterruptedException {
        System.setProperty("web driver.chrome.driver", "./Drivers/chromedriver.exe");
        driver = new ChromeDriver();
        driver.navigate().to("https://www.google.com/");
        Thread.sleep(2000);// Hard wait not recommended
        driver.navigate().to("https://www.selenium.dev/");
        Thread.sleep(2000);
        driver.navigate().to("https://www.saucedemo.com/");
        Thread.sleep(2000);
        driver.navigate().back();
        Thread.sleep(2000);
        driver.navigate().forward();
        driver.findElement(By.name("user-name")).sendKeys("Usha");
        Thread.sleep(2000);
        driver.navigate().refresh();
        Thread.sleep(1000);
        driver.close();
    }
}

logintest.java

package com.example;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class logintest {
    public static void main(String[] args) throws InterruptedException {
        WebDriver driver = new ChromeDriver();
        driver.get("https://www.saucedemo.com/");
        driver.manage().window().maximize();
        Thread.sleep(2000);
        driver.findElement(By.id("user-name")).sendKeys("standard_user");
        Thread.sleep(2000);
        driver.findElement(By.id("password")).sendKeys("secret_sauce");
        Thread.sleep(2000);
        driver.findElement(By.id("login-button")).click();
        Thread.sleep(2000);
        driver.quit();
    }
}
