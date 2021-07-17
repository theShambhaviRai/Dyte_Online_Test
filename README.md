# Dyte_Online_Test
Design

    Create a microservice using molecular which have the following functions or actions

          1. register (creation of webhook microservice)
          
               . accept a single parameter = targetURL (where the response will be sent whenever any event will be triggering our created webhook)
               . generate uniqueID for new webhook and save the uniqueID and targetURL to the database
               . return uniqueID as a response
               
          2. update (update the targetURL of already existing webhook microservice)
          
               . accept uniqueID and newtargetURL as parameters
               . change the targetURL of webservice specified by uniqueID to the newtargetURL
               . return a success response on updation else return error response
               
          3. list (display all webhooks created)
          
               . no parameters
               . query all registered (created) webhook microservice from database and return as response
               
          4. trigger (trigger all webhooks at once)
          
               . accept a single parameter called ipAddress
               . list of targetURLs extracted from database
               . http POST request sent to all targetURLs in parallel
                 -> request body has
                   => JSON with the IP address
                   => UNIX timestamp of when the request sent

    Create backend using express with a database to store webhooks microservice created and with following routes

            1. set of routes accessible to admin (using actions defined in microservice ) returning appropriate response
            
                . create 
                . read
                . update
                . delete
                
            2. route ip for trigger action of microservice (The IP of the user who visits this route should be sent as ipAddress to the trigger action)
            
            3. database (mongoDB) will have the following collection with documents as 
            
                . targetURL
                . uniqueID

Installation

    1. This project is developed in kali linux
    2. Download the project and unzip it
    3. You should have node.js, Molecular and Express installed on your system
    4. Follow these steps to download necessary dependencies in chronological order
      a. Open your terminal or press Ctrl + Alt + T
      b. sudo apt install nodejs
      c. sudo apt install npm
      d. sudo apt-get update
      e. sudo apt-get upgrade
      f. sudo npm i -g moleculer-cli
      g. npm install
      h. cd webhooks-microservice-project 
      i. npm install express --save
      j. npm install mongodb --save  
      k. npm run dev 
    5. Now, in your browser go to http://localhost:3000/ URL 
    6. To end the demo, go to the terminal and press Ctrl+c twice
