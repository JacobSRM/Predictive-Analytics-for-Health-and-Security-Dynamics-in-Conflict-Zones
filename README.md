# Predictive-Analytics-for-Health-and-Security-Dynamics-in-Conflict-Zones
Predictive Analytics for Health and Security Dynamics in Conflict Zones

How to set-up

1. Open VSCode.
   
2. Setting up Virtual Environment.
Create Virtual Environment with Python v7
Check link for detailed steps: 
https://saturncloud.io/blog/how-to-create-a-conda-environment-with-a-specific-python-version/

conda create --name myenv python=3.7
conda activate myenv
python --version

Ensure VSCode is running in Virtul Environment with "pip list" command. It should close to 0 modules.

Then install requirements.txt and then run "pip list" again. If there's a problem, install requirements one by one instead.

3. Running the program.
After all requirements are installed run app.py
Wait for a few seconds based on your PC's speed and you'll see
Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)

Open http://127.0.0.1:5000/ and interact with the chatbot there.

4. AWS Deployment
To deploy on AWS, check out this video by Krish Naik: 
https://youtu.be/oOqqwYI60FI
Use appcloud.py for AWS instead of app.py



Understanding the Chatbot

Injuries Assistance
intents.json has various questions with answers/responses used to train the chatbot. Each question is assigned a class. 
train_chatbot uses intents.json to train the chatbot and saves trained model as chatbotmodel2.h5
chat.py gets the input question from the user and uses trained model chatbotmodel2.h5 to predict the class of the question. Once the class is identified, it gives the answer/response of that particular class
You can modify intents.json to add more types of injuries with more questions and appropriate responses.

Hospital Database
Hosptial.csv contains a list of hospitals in Palestine and have a variable to denote if it's operational or not. It is loaded in app.py to find out which area of Palestine the user is in and will give the list of operational hospitals nearby. 
You can modify the file to add more hospitals from different countries.


Disease Prediction
KNN Model is saved as pickle file knn.pkl
In app.py, we get two symptoms from the user. Then it uses knn.pkl and to predict the possible diseases it might be and asks questions if the user is facing other symptoms. Once enough symptoms are identifies, we get a prediction. 

app.py is the Flask Front End
It uses session variable s to get input from the user in front end and passes it to the backend. 
app.py contains the code for disease prediction and calls the functions in chat.py for Injury Assistance.
