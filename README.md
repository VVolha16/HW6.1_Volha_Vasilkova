# How to start working with the collection in Postman for API testing purposes  

## Postman

To begin using the code from github you need to create `Team Workspace` for your Postman account (if not created): [Create a new workspace in Postman](https://learning.postman.com/docs/collaborating-in-postman/using-workspaces/creating-workspaces/#create-a-new-workspace).
Otherwise you won't be able to connect to GitHub from Postman.

Then follow the steps in Postman:
1. Log in to Postman
2. On the left sidebar click on `APIs` icon
```
   Note: if there is no 'APIs' icon - click on the last icon `Configure workspace sidebar` and turn on `APIs` element toggle
```
3. Create a new API (click on `+` "Create New API" or click on link `Create an API`), name it 
```
   Note: for the free Postman version there is a possibility to have only ONE connected repository.
   If you have previously created API - you need to delete it or disconnect* repository
      *To disconnect repository:
      - click on created API
      - click on `Source control` icon on the right sidebar
      - click on three dots
      - click on `Disconnect repository` - the collection will be deleted from previously created API
```
4. Being logged in GitHub on the main screen of Postman click on `GitHub`
   
![image](https://github.com/VVolha16/HW6.1_Volha_Vasilkova/assets/166701053/1956176c-44c8-45b5-985b-fe500aa7df42)
```
   Note: if you are going to connect to GitHub with existing API - select it and then click on `Connect repository` > select `Connect` 
```
5. Click on `Continue` on notifying page 

   ![image](https://github.com/VVolha16/HW6.1_Volha_Vasilkova/assets/166701053/297df014-b04b-4cff-abc0-36c9343bf649)


    You're authorized message will be displayed:

   ![image](https://github.com/VVolha16/HW6.1_Volha_Vasilkova/assets/166701053/9e837185-e990-41be-b817-8b8d48aac113)

   
 6. Fill in the fields about repository you want to connect  and click on `Connect` button
    
      ![image](https://github.com/VVolha16/HW6.1_Volha_Vasilkova/assets/166701053/2e0b317f-0039-44d2-bee2-72b3eb2b65f1)


      Now the Postman is synchronized with the GitHub and necessary collection should be displayed in Postman

 
  ## Sql Verifier collection description

  To start wotk with the collection make sure that all necessary tools are successfully installed.  Please see the detailed instructions here: https://github.com/IT-switcher/verifier/blob/main/README.md

  ### Before testing please read attentively [Sql_verifier_description](https://github.com/VVolha16/HW6.1_Volha_Vasilkova/blob/main/Sql_verifier_description.md)

  The API is available at http://localhost:8080,
  openAPI definition: http://localhost:8080/docs/docs
  
  For testing purposes there are Happy Path (HP) and Sad Path (SP) requests in the collection. 
  Sad path requests are used for error handling testing.

Happy Path requests:
  - HP: create a task with valid values
  - HP: create a task with long title

Sad Path requests:
  - SP: error when create a task with long text
  - SP: error when create a task with long answer

Please use the environment file [postman_environment_hw_6.1.](https://github.com/VVolha16/HW6.1_Volha_Vasilkova/blob/main/postman_environment_hw_6.1.json) or [test_data_hw_6.1](https://github.com/VVolha16/HW6.1_Volha_Vasilkova/blob/main/test_data_hw_6.1.csv) for necessary variables values.

Collection is ready for API testing

## Variables

- **Local Variables:**  scoped to a single request or script
- **Data Variables:**  used in conjunction with data files (like CSV or JSON) to run collections with different sets of data
- **Environment Variables:**  specific to a particular environment, used when dofferent collections can use the same environment
- **Collection Variables:** scoped to a specific collection, used when variable is specific only to current collection, and e.g. you don't need to specify environment 
- **Global Variables:** available across all collections and environments, used in case all collections and environments are related to the same base URL


## Priority in Usage
When multiple variables have the same name, Postman resolves the variable based on a specific priority order. The priority order from highest to lowest is:

- **Local Variables:** These are the highest priority because they are specific to a single request and defined in the request script or pre-request script.
- **Data Variables:** These come next and are used during collection runs with data files.
- **Environment Variables:** These have a higher priority than global and collection variables because they are specific to the environment being used.
- **Collection Variables:** These are scoped to the collection and override global variables.
- **Global Variables:** These have the lowest priority and are accessible across the entire Postman instance but are overridden by other types of variables if they exist


In current collection the following variables are specified:
- **{{baseUrl}}** - environment
- **{{adminUsername}}** - environment
- **{{adminPassword}}** - environment
- **{{rememberMe}}** - environment 
- **{{text}}** - environment and data
- **{{answer}}** - environment and data
- **{{title}}** - environment and data
- **{{happyPathTitle}}** - environment and data
- **{{sadPathText}}** - environment and data
- **{{sadPathAnswer}}** - environment and data
