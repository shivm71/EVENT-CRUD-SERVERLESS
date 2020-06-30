# border-free-server-less
Border free assignment REACT+GOLANG Aws Serverless

Steps to make it running

FRONTEND

1. initiate basic setup of Amazon CLI and amplify (basic todo app setup on amplify docs)
2. add api with basic lambda function (go as base)
3. add auth
4. now open folder where you initiated basic app and replace src folder + package.json with this our files 
5. then open yourapp/src/constants/constants.js and replace api name and path  
6 . now amplify push to make changes on aws 

BACKEND

7 . install go and navigate to backend directory and run command -- go build -o main *.go -- this will make main file in same directory  
8 . now zip it using any zip tool and name it as desired file name
9 . open aws lambda select the function you build with amplify(functionname-environment name) open it  and under fuction code upload upload your zip 
10 . As Amplify not directly support Dynamo db so well create one so go to services anf search for dynamodb create a table with your desired name and then make a primary ket as "eventid" and hit same 
    As it is created by us manually so IAM role for this is not yet been setuped so open IAM role and search your "yourprojectname+your lambda name" under roles section and then add ploicies with dynamodb full access 


IMPORTANT CHECKs --
1. under lambda function scroll down and search for ENVIRONMENT VARIABLE add following if not there
    a REGION -- your region of aws
    b TABLE_NAME -- your table name 
2. Search for basic sessting and check for handler is "main"
      if hello make it main by edit button
3. test your function with AWSPROXY test under basic test of lamba 

and then go back to console of local project directoruy  and hit "amplify add hosting" select first option and then "amplify publish"


HUrray you are done with react + golang serverless 


error ----
    no access to dynamodb --- repeat the 10 th point ---- error can be viewed as log under amplify console and also under lambda basic test
    invalid path --- 2 poimt of important checks
    internal server error -- test go code locally with sdk or make it issue in issue section 
    CORS Policy Blocked -- add ["ACCESS_ALLOW_CONTROL_ORIGIN"] = "*"
      
      
