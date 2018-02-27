# Robust-REST-ful-Web-Service

Robust REST ful Web Service
//Created by Mitesh Purohit under guidence by DAMS.
// Git Hub https://github.com/MiteshPurohit
//use sts tool reduce time for adding jar and etc.
// before creating this project open ur tomcat server to check ur server started or not type (localhost) in your browser.

#sts steps :
1)open Sts tool(spring tool suite)
2)select your workbech where you want to store.
3)open file >new >Import Spring Getting Started content >Rest Service >Finish
4)wait for the process complete first then follow below steps




//Step 1: Create Greeting.java (hello/Greeting.java) in hello package.

 #Greeting.java

package hello;

public class Greeting
 {
    private final long id;
    private final String content;

    public Greeting(long id, String content)
    {
        this.id = id;
        this.content = content;
    }

    public long getId()
    {
        return id;
    }

    public String getContent() 
    {
        return content;
    }
}


//Step 2: Create GreetingController.java (hello/Controller) in hello package.

 #GreetingController.java

package hello;



import java.util.concurrent.atomic.AtomicLong;
import org.springframework.web.bind.annotation.RequestMapping;

import org.springframework.web.bind.annotation.RequestParam;

import org.springframework.web.bind.annotation.RestController;



@RestController
public 

class GreetingController 
{

   
	 private static final String template = "Hello, %s!";
    
	 private final AtomicLong counter = new AtomicLong();

   
	
	 @RequestMapping("/greeting")
    

	public Greeting greeting(@RequestParam(value="name", defaultValue="World") String name) 
	
	{
        
		return new Greeting(counter.incrementAndGet(),
       
                String.format(template, name));
   
	}

}



//Step 3: Create Application.java (hello/Application) in hello package.

 #Application.java


package hello;



import org.springframework.boot.SpringApplication;

import org.springframework.boot.autoconfigure.SpringBootApplication;



@SpringBootApplication


public class Application

{

   
	 public static void main(String[] args) 
	{
        
		SpringApplication.run(Application.class, args);
    
	}

}



#How to run this project
1)click on gs rest service[boot] then right click
2)Run as  > spring boot app
3)open browser
4)type http://localhost:8080/greeting

#If you want your name
ex: http://localhost:8080/greeting?name=mitesh


                                                     
		
