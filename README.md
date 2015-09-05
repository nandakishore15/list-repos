# This project takes the URL of a public github repository as a form input and displays the following: Total number 
of open issues, number of open issues that were opened in the last 24 hours, number of open issues that were opened 
more than 24 hours ago but less than 7 days ago and number of open issues that were opened more than 7 days ago.

The project is deployed at https://immense-reef-3975.herokuapp.com/

#Solution explained. 

jQuery and HTML were used to solve the challenge. The workflow is simple enough. 

1. The URL is taken as input and validated. If it's not a valid URL, an error is thrown. 
2. If it's a valid URL, the repo name and the owner name are obtained by splitting the URL string. 
3. Then, an asynchronous AJAX calls are made to the /repos/owner-name/repo-name endpoint. An error is thrown in case
the API return an error. On succes, this API call also return the total issues in open state.
4. Further, two more synchronous requests are made to the /repos/:ownername/:reponame/issues endpoint to get the no of issues 
created in the last 24 hours and the last 7 days (excluding the current day). 
5. Simple arithmetic is performed to compute the output. 

#What would I have done better if I was given more time for this challenege? 

1. Made the UI look at least a  little bit nicer to the eye. 
2. Try and implement caching so that API calls aren't made to the server all the time.
3. Implement github sign in for the app - the disadvantage of not logging in with gitbug is the limited no. of API calls,
one can make from a given IP address without signingin. 



