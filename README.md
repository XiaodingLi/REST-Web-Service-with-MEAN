The web application provides both REST web service consuming and building with Node JS.
The implementation exposes a service at the following entry point: GET/palindromes
The construct of the application is:
 

You can use "index.html" and "controller.js"  to test it, or directly send a get request "GET /palindromes?search=electricity&limit=3" 

The service accepts the following parameters:

Name	  Required    Default	                  Description
search	  yes	      -	                          patent search text
limit	  no	      1	                          number of patents considered (min:1, max:5)
	 		
Request example:
GET/ palindromes?search=electricity&limit = 3
The service should search the NASA patents for given text and retrieve up to given number of patents. For each extracted inventor, first and last name should be concatenated into a single string (e.g. "Graham" and "Bell" becomes "Graham Bell"). For each such name the service should calculate the number of palindromic strings that can be created using the name letters. Name should be treated as case-insensitive (i.e. b and B is the same letter) and all white-spaces should be ignored. A valid palindromic string is one that uses only the letters in the given name, and is the same length as the given name. Each letter can be used more than once, and not every letter must be used. For example, given the name "Graham Bell", "aaahhhhaaa" and "bellmmlleb" are valid, but "aaa" and "hhhsagtbbb" are not. Results should be returned in JSON format sorted by the count, highest to lowest.

Response example (with actual palindrome counts):
[
    { "name": "Nicola Tesla", "count": 531441 },
    { "name": "Max Planck", "count": 32768 },
    { "name": "Marie Curie", "count": 16807 },
    { "name": "Maria Mayer", "count": 7776 }
]
