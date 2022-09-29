# CMPG-323-Overview---34687602

## Project 1
    Outline of the CMPG 323 Module throughout the semester

### Project 2
    Repository name == Web API
    In this project a restful web API will be made which serve as the communicator with the database, server and the frontend. The API will also be used as an interaction with the data source/devices

    Requirements == The API should contain at least one get, post, patch and delete method per
                    resource
                    I will use HTTP endpoints for my API to update my database
    
    How my project works == The following methods are methods contained in the models folder and how they work
	                       1. Zone.cs
	                          - GET method that retrieves all Zone entries from the database
	                          - GET method that will retrieve one Zone from the database based on the ID parsed through
	                          - Create a POST method that will create a new Zone entry on the database
	                          - Create a PATCH method that will update an existing Zone entry on the database
	                          - DELETE method that will delete an existing Zone entry on the database
	                          - Private method in the API that checks if a Zone exists (based on the ID parsed through) before editing or deleting an item
	                          - GET method that retrieves all devices within a specific zone (based on the zone ID that is parsed through)


	                      2. Category
	                         - GET method that retrieves all Category entries from the database
	                         - GET method that will retrieve one Category from the database based on the ID parsed through
	                         - POST method that will create a new Category entry on the database
	                         - PATCH method that will update an existing Category entry on the database
	                         - DELETE method that will delete an existing Category entry on the database
	                         - private method in the API that checks if a Category exists (based on the ID parsed through) before editing or deleting an item
	                         - GET method that retrieves all devices within a specific category (based on the category ID that is parsed through)
	                         - GET method that will return the number of zones that are associated to a specific category (use the device entity to join the data)

	                     3. Device
	                        - GET method that retrieves all Device entries from the database
	                        - GET method that will retrieve one Device from the database based on the ID parsed through
	                        - POST method that will create a new Device entry on the database
	                        - PATCH method that will update an existing Device entry on the database
	                        - DELETE method that will delete an existing Device entry on the database
	                        - private method in the API that checks if a Device exists (based on the ID parsed through) before editing or deleting an item

                        When connecting to my database and you get an error, please go to the firewall settings and configure them by add a client IP address

    Problems I have faced == During the completion of this project, I faced several problems such as:
                             1. I didnt follow the the guidance documentation provided nor did I watch the videos provided with my full attention, which led me to                                       redoing this project multiple times
                             2. I used .NET CORE  version 6 instead of version 3, even after I was advised not to use because not a lot of materials regarding it is                                   not available yet. Which led to encounting a lot of errors which I havent seen before and couldnt understand and also making some parts                                 of the guidance documentation document provided to us by the lectures irrelevent.
                             3. Time Management. Regarding time, I used to wrok under the assumption that I still got time which was not true and backfired on me                                       because I ended up gettting a 500 server error at the last minute resulting in my import link not being valid thus I coulnt host my API                                 on Azure
                             4. The other thing is that I included my Reference list in my README file only instead of creating a document to add my reference list and                                 I realised this late when I was about to submit since I had to upload the document of GOOGLE FORMS along with my submission. By the                                     time I was done with the document the deadline had passed resulting in failure to mee the deedline.
                             5. My Authorization was not working properly and Creating an APP SERVICE resource group took longer than I thought.
     
     What I have Learned and How to move forward == Well first thing first I learned that I need to follow the instructions precisly given to me, read the instructions                                                     carefully because I i understand the instructions then I can succesfully finish my project and submit it, and also                                                     use the exact requirements of the project as the ones recommended. Secondly I need to learn to manage my time more                                                     efficiently to avoid submitting at last minute and also to be able to spare enough time for anything that could go                                                     wrong. Another thing is that I should normalise reading the project brief before I start with my project and the                                                       project rubric after I'm done with the project to check if I did everything asked of me.
     
     Reference
        https://www.youtube.com/watch?v=SR_JEdhxWx0

        https://stackoverflow.com

        https://docs.microsoft.com/en-us/aspnet/core/security/authentication/?view=aspnetcore-6.0

        https://www.dropbox.com/sh/p8fiokfpiqv4gud/AAC5X8SdanTnduTWYzVq4kQ7a?dl=0
        
        https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-web-api?view=aspnetcore-6.0&tabs=visual-studio
        
        https://learn.microsoft.com/en-us/training/modules/build-web-api-aspnet-core/
        
        https://learn.microsoft.com/en-us/aspnet/core/tutorials/web-api-help-pages-using-swagger?view=aspnetcore-3.1
        
        https://learn.microsoft.com/en-us/training/paths/create-microservices-with-dotnet/
        
        https://procodeguide.com/programming/entity-framework-core-in-asp-net-core/
        
        https://jd-bots.com/2022/01/24/join-two-entities-in-net-core-using-lambda-and-entity-framework-core/
        
        https://learn.microsoft.com/en-us/aspnet/core/tutorials/publish-to-azure-api-management-using-vs?view=aspnetcore-6.0
        
        https://thejpanda.com/2020/08/10/python-automating-asp-net-core-web-api-creation-that-communicates-with-your-database-in-60-seconds-or-less/

#### Project 3
    Repositort name == MVC Web Application

    Requirements == understand architectural patterns as well as pay specific attention to implementing coding principle design patterns
    
    Repository patterns Implementation

## How my project works
    For this project I implemented Tier 2 which is the advanced level of the Repository patterns. I started by creating Repositories folder which contains my Generic,
    Category, Device and Zone repository classes and interfaces
    
    ### Repository Folder
    
          1. CategoryRepository class == contain all data access operations relating to Categories
          2. DeviceRepository class == contain all data access operations relating to Devices 
          3. ZoneRepository class == contain all data access operations relating to Zones
          4. GenericRepository class == contains all methods used to manipulate data in your tables
    
          In my interfaces(IZone, IDevice and ICategory) I will add any additional methods I created and they will be inherited by my Repository classes		  CategoryRepository, DeviceRepository and ZoneRepository will inherit the GenericRepository so that I can be able to acces the methods.
          
    
    ### Controllers
    
          In my controller folder I have 4 controller classes namely 
            1. DevicesContorller == Contains data access operations for the Device table
            2. CategoriesController == Contains data access operations for the Category table
            3. ZonesController == Contains data access operations for the Zone table
            4. HomeController == Contains data access operations to all the available tables (Category, Device, Zone tables)
            
	So what I did was I transfered all data access operations from DeviceRepository to the DevicesController, from the CategoryRepository to the 			CategoriesController class, and from the ZoneRepository to the ZonesController class so that when I wanna edit my methods I only edit from one file which the 	      GenericRepository class. I implemented the use of the DeviceRepository class in the DevicesController. Then I implemented the use of the ZoneRepository class 	    in the ZonesController. And I also implemented the use of the CategoryRepository class in the CategoriesController.
	
    
    Problems I have faced == I didnt read the instructions well which in turn resulted in me working in the wrong branch. I only realised that later sp I had to 			      restart the project, create a new branch the implement Tier 2.
    
    What I have learned == It is important to read instruction before doing the project because it gives you an idea of what you have to do and allows you not to miss
    			   important details

    How to solve the problem == Give myself enough time to go through the project brief, make notes on what I need to do for the project and create an execution plan 				      for my project
    
    
    ### Reference List
    
    		Anon., 2017. Stake Overflow. [Online] 
		Available at: https://stackoverflow.com/questions/45119343/c-mvc-confirmation-delete-dialog
		[Accessed 14 September 2022].
		
		
		Ignite, M., 2022. Microsoft. [Online] 
		Available at: https://learn.microsoft.com/en-us/training/paths/aspnet-core-web-app/
		[Accessed 12 September 2022].
		
		
		Ignite, M., 2022. Microsoft. [Online] 
		Available at: https://learn.microsoft.com/en-us/aspnet/mvc/overview/older-versions-1/overview/asp-net-mvc-overview
		[Accessed 12 September 2022].
		
		
		Ignite, M., 2022. Microsoft. [Online] 
		Available at: https://learn.microsoft.com/en-us/aspnet/mvc/overview/older-versions-1/overview/asp-net-mvc-overview
		[Accessed 13 September 2022].
		
		
		Ignite, M., 2022. Microsoft. [Online] 
		Available at: https://learn.microsoft.com/en-us/training/modules/secure-aspnet-core-identity/
		[Accessed 14 September 2022].
		
		
		Jacqui Muller, M. C., 2022. Dropbox. [Online] 
		Available at: https://www.dropbox.com/sh/p8fiokfpiqv4gud/AAC5X8SdanTnduTWYzVq4kQ7a?dl=0
		[Accessed 18 September 2022].
		
		
		Microsoft, 2022. Microsoft Training. [Online] 
		Available at: https://learn.microsoft.com/en-us/training/modules/secure-aspnet-core-identity/
		[Accessed 13 September 2022].
		
		
		//Repository patterns implentation document provided to us
		Muller, J., 2022. Efundi. [Online] 
		[Accessed 16 September 2022].
		
		
		Naik, K., 2022. C# Conner. [Online] 
		Available at: https://www.c-sharpcorner.com/UploadFile/bd5be5/design-patterns-in-net/
		[Accessed 13 September 2022].
		
		
		Velayutham, M., 2022. C# Conner. [Online] 
		Available at: https://www.c-sharpcorner.com/uploadfile/babu_2082/architectural-patterns-in-net/
		[Accessed 13 September 2022].


##### Project 4
    Repository name == Robotic Process Automation

    Requirements == Knowledge on testing in this project will crucial
                    UiPath Automation Cloud account
                    UiPath Studio Community Edition
                    Access to the application i will be automating

###### Project 5
    Repository name == Power BI

    Requirements == Power BI

###### Branching Strategy
    I chose to use the github flow because it is easier for me to understand, it is easier to manage since i will be working to on my own in this projects and not in a team. Also because each feature will have its own branch thus reducing the chances of my whole system breaking

## Purpose of .gitignore
    The .gitignore file commands instruct git which files to ignore. It is used to prevent committing temporary files from your working directory

# Storage of credentials and sensitive information
    The use of authorisation authentication to access the database will be used and sesitive will be encrypted to prevent the information being seen by the wrong people
