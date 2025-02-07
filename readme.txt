Objective : To create a simple chatbot for customer query for a company product and enquiry

Data : I have created a json file which contain all the required intent, from the user 
It has all the necessay information to process when a question is posted to chatbot, 
Depending on it, chatbot provide repsonse.

Here, i have used pre-trained llm model from microsoft, microsoft/DialoGPT-medium for direct resposne 
for the user query

For this to work, i have followed simple approach, by creating a simple class for chatbot, which has all the necessary 
sub function to take care os user query, from greeting to quiting the bot application and generating the reposne from json using regex
for matching when usery query (it is matched with json)


The flow of information is kept simple, it can be higligted as follows.

[User Input]    Here, when the code runs a pop-up is seen where  we can put input
    ↓
 [Intent Matching (JSON)]  # Goes to json for repsonse 
     ↓ (Match Found) → [Predefined Response] # Gives the required match as per teh query from json
     ↓ (No Match)   # If no match is seen, then it goes for processing to transfomer model for reponse
 [Tokenization]
     ↓
 [Transformer Model (DialoGPT)] # here the query is checked
     ↓
 [Response Decoding]  # response is generated
     ↓
[Output to User] Finally we get the required output



To summarize: 
Input from User to chatbot : Here query is recibed form user.

JSON Matching Criteria:

The chatbot iterates it through the intents in JSON file.
regex used to Compare the query against reuired information in json.
Returns the corresponding predefined response if a match is seen therwise goes to transfomer model for response.

Transformer usage : If there is no match is found, the chatbot uses the DialoGPT-medium model to generate required response.