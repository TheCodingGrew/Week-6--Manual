# Week-6--Manual

1. Create an ASP.NET core MVC Web app
2. Scaffold the desired database using the scaffold command unto the Models folder
3. Now right-click on the Controller folder and choose Add > New Scaffolded Item
  - Choose MVC Controller with views, using Entity Framework
  - In Model class dropdown, choose one of your Model classes
  - In the DbContext class dropdown, choose the name of the generated DBContext class. If your database name is Music, then the DbContext class name would be MusicContext
  - You can leave the controller name as it is and click Ok.
  - You will be able to find a new Controller file in the Controllers directory and a new folder under Views with files such as Index, Edit, Details, Delete, Create.cshtml
4. Run the code and if you encounter errors - do the following steps:
  - in appsettings.json, add a connection string as the last entry
  ```
   "ConnectionStrings": { "MusicConnection": "server=localhost;uid=root;database=music" }
  ```
 
 You change the connection string name and username, password,database name according to your machine and exercise. 
    
- In program.cs, add the following code
    
    ```
    var connectionString = builder.Configuration.GetConnectionString("MusicConnection");
    builder.Services.AddDbContext<MusicContext>(options=>options.UseMySQL(connectionString));
    
    ```
    
 Make sure that, you modify the connection string name and change the DBContext name mentioned above according to your exercise/machine.
    
  5. You should now be able to succcessful run the application and perform CRUD operations
    
