import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.Test;
public class LoginAutomation {
@Test
public void login() {
System.setProperty("webdriver.chrome.driver", "path of driver");
WebDriver driver=new ChromeDriver();
driver.manage().window().maximize();
driver.get("https://www.awwwards.com/sites/trt-concept");
WebElement username=driver.findElement(By.xpath("//input[@name='_username']"));
WebElement password=driver.findElement(By.xpath("//input[@name='_password']"));
WebElement login=driver.findElement(By.xpth("//span[text()='Log in now']"));
username.sendKeys("abc@gmail.com");
password.sendKeys("abc@123");
login.click();
String actualUrl="https://www.awwwards.com/sites/trt-concept";
String expectedUrl= driver.getCurrentUrl();
Assert.assertEquals(expectedUrl,actualUrl);
}
}
