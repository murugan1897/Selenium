# Selenium
package basicPrograms;

import java.awt.AWTException;
import java.awt.Robot;
import java.awt.event.KeyEvent;
import java.util.ArrayList;
import java.util.List;
import java.util.Set;

import org.asynchttpclient.netty.request.NettyRequestSender;
import org.junit.AfterClass;
import org.junit.BeforeClass;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptException;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;

public class amaz1 {
	WebDriver driver;
	@Test
  public void AopenBrowser() {
	  System.out.println("1st method");
		
	       driver=new ChromeDriver();
           driver.get("https://www.amazon.in/");
		   driver.manage().window().maximize();
		}
	@Test
		public void BSelection() throws InterruptedException {
	
			driver.findElement(By.id("twotabsearchtextbox")).sendKeys("watches men");
 		driver.findElement(By.id("nav-search-submit-button")).click();
		  Actions act = new Actions(driver);
			act.scrollByAmount(0, 70).perform();
			Thread.sleep(2000);
	

	}
	@Test
	public void CSelectQu() {
		driver.findElement(By.xpath("//span[@class='a-size-base-plus a-color-base a-text-normal']")).click();

		  
			Set<String> windowHandles = driver.getWindowHandles();
			
			List <String> ls = new ArrayList<String>(driver.getWindowHandles());
			System.out.println(windowHandles);
			
			driver.switchTo().window(ls.get(1));
		
		     Actions act1 = new Actions(driver);
		     act1.scrollByAmount(20, 100).perform();
//			
			WebElement ele=driver.findElement(By.xpath("//select[@id='quantity']"));
			   Select s1 = new Select(ele);
			     s1.selectByVisibleText("1");
			     driver.findElement(By.id("buy-now-button")).click();
	}
	
	@Test
	public void DsunUpPas() throws AWTException, InterruptedException {
		driver.findElement(By.id("ap_email")).sendKeys("murugan");
		}
	
	
		@Test
		
		public void Esin() throws AWTException {
		driver.findElement(By.id("continue")).click();
		Robot rb=new Robot();
		
		driver.findElement(By.id("ap_email")).sendKeys("Murugan181996john@gmail.com");
		
		driver.findElement(By.id("continue")).click();
		WebElement ele=driver.findElement(By.xpath("//span[text()='\r\n"
				+ "            We cannot find an account with that email address\r\n"
				+ "          '"));
		System.out.println(ele.getText());
	}
		@Test
		public void Fquit() {
			driver.quit();
		}

}

