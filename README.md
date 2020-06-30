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
9 . open aws lambda select the function you build with amplify(functionname-environment name) open it  
