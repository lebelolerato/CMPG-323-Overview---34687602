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
    Repository name == CMPG-323-Project-4---34687602

    Requirements == Knowledge on testing in this project will crucial
                    UiPath Automation Cloud account
                    UiPath Studio Community Edition
                    Access to the application i will be automating


	In this project we are automating the process of logging in, registering into a web page and also inputing data. The we test each data input from the excel 	    file if its valid or not as we input it.

	## This is what is happening in my Automation project:
	So firstly I am using the UiPath community app and instead of using the modern design experience, I used the classic design experience.

	  ### Steps
	      1. We read the data in each spreadsheet
	      2. Create DataTables for Zone, Category, and Device
	      3. Create the appropriate column names or attributes for each DataTable 
	      4. We type Each row in each spread sheet into the specifc DataTable
	      5. Save the data in the each DataTable in a variable for refence later

	  ### Steps for logging in

	      2. Click the login button on the menu or left panel
	      3. Type your email into the the "Email" TextBox
	      4. Type your Password into the "Password" Textbox
	      5. Click the log in button at the bottom

	 ### Steps for Intserting

	      1. Click Zones or Categories or Devices on the left side
	      2. Click the + icon next to the name on the Table on your right corner
	      3. Type into the specific fields reading from the specific DataTables
	      4. Click "create" button

	      For inserting the Device I added an If statement for when the IsActive == True then the UiPath automation should automatically check the active checkbox 		     and if not then click the "create" button

	 ### Steps for Delete

	      1. Click Zones or Categories or Devices on the left side
	      2. Click the dusbin icon nexg to the item you want to delete
	      3. Click the delete button.

	 ### Steps for Update

	      1. Click Zones or Categories or Devices on the left side
	      2. Click the Pen icon next to the item you wanna edit 
	      3. Read the Text thats already present 
	      4. Save it in a variable
	      5. Edit the text by adding the word "EDITED" next to the existing text which is store in a variable
	      6. Click the "Save" button
	      7. Click the "Back to list" url

	  ### Reference list

		https://academy.uipath.com/courses/build-your-first-process-with-studio

		https://academy.uipath.com/courses/meet-the-uipath-platform

		https://academy.uipath.com/courses/datatables-and-excel-automation-with-studio-

		https://academy.uipath.com/courses/rpa-testing-with-studio

		https://academy.uipath.com/courses/working-with-orchestrator-resources

		https://academy.uipath.com/courses/debugging-in-studio-

		https://academy.uipath.com/courses/ui-automation-with-studio-

		https://academy.uipath.com/courses/variables-and-arguments-in-studio

		https://academy.uipath.com/courses/control-flow-in-studio

		https://academy.uipath.com/courses/introduction-to-rpa-and-automation

		https://docs.uipath.com/studio/docs/ui-automation

		https://www.uipath.com/learning/video-tutorials/excel-datatables-automation

		https://www.youtube.com/watch?v=BAYmmUuB2Zo

		https://www.youtube.com/watch?v=TT3cgpWutD4

		https://www.dropbox.com/sh/p8fiokfpiqv4gud/AAC5X8SdanTnduTWYzVq4kQ7a?dl=0&preview=10+CMPG322++-+Project+4+20+Oct.mp4
		
		
	### Problems I faced
	    It was a little hard for me to grasp and undersdand the RPA concents and also to get used to using the UiPath studio
	    
	### What I learned
	    I learned new ways which are very effective when it comes to learning new technologies and concepts
	    
	### How to solve the Problem
	    I need to stop paicking and overthinking that way everything will go smootlhy 


###### Project 5
    Repository name == Power BI

    Requirements == Power BI
    
   ## How my project works

   ### Live Connection
        So for my live connection I imported my data from the web by opening the dataset using my desktop excel application. And copying the path then connect. 
  
   ### High-Level Metrics
        In these page I decided to show the number of devices installed per year whereby the counted number for each year is shown on the card that is that is on the           top right. To see which year a certain device was installed you can filter using the spice card next to the graph. I added another slicer which             	    alternates/filters the data using date installed 

   ### Device Monitoring
       In these page I used two graphs, one to show the number of devices in a each category of which the exact number will be showed in the count card at the top     	      right and another to show the number of devices in a each zone of which the exact number will also be shown on the count card at the bottom right. The status    	      card will show you whether that device is active or not as you navigate through the different zones and categories. If use the splices next to each graph to see 	      a device in each category or zone the splices will also automatically show you which zone and category does the device belong to.

   ### Device Registration
       In this scenario I assumed that a device is only registered if it is active. To get to this decision I used the DSTV scenario whereby you can purchase your 	  decoder and the satellite dish but as long as it is not installed and the DSTV offices were not notified about the purchased decoder, your TV will not work. I 	used a bar chat to show the number of devices per category mainly because it clearly shows the statistics of the data and it allows you to nfilter the date 	        using both the category Id's and the Device names. 

       I used a line chart to show the number of device installed at a specific date because it's much more clearer than the others and it also shows the trend. Then I        decided to use a bar chart and a line chart to show the number of Zone Id's per status (active or Inactive) mainly because the graph shows the trend over a   	    period of time while the bar chart show us clearly the difference between the active devices and Inactive devices

       Again as you manipulate the date according to what you want to see the count will be shown on the card in the middle and the status card will change as you pick        different cattegories and zones.

   ### Filtering 
        For filtering I used the purple navigator on the right of every page under "filters on every page" since the requirement was to do an all page simulteneouse   	      filtering. Under "filters on every page" you'll be able to filter according to category Id's, Date installed and Zone Id's. Under the above categories that I          mentioned above you can choose to filter according to a specific category Id, date installed or zone Id which will be projected in every single page.

###### Branching Strategy
    I chose to use the github flow because it is easier for me to understand, it is easier to manage since i will be working to on my own in this projects and not in a team. Also because each feature will have its own branch thus reducing the chances of my whole system breaking

## Purpose of .gitignore
    The .gitignore file commands instruct git which files to ignore. It is used to prevent committing temporary files from your working directory

# Storage of credentials and sensitive information
    The use of authorisation authentication to access the database will be used and sesitive will be encrypted to prevent the information being seen by the wrong people
