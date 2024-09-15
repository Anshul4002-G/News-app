# News-app
this app helps you to read news of your choice  
# news app
import requests
import json
import pyttsx3
engine=pyttsx3.init()

query=input("enter news type")
url=f"https://newsapi.org/v2/everything?q={query}&from=2024-08-15&sortBy=publishedAt&apiKey=ff8398d9b2ab43bea5bae64ed35818c5"
r=requests.get(url)
news=json.loads(r.text)

for article in news['articles']:
    
    print(article["title"])
    engine.say(article["title"])
    print(article["description"])
    print("-------------------------------------------------------------")
    engine.runAndWait()


