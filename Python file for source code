import subprocess  # to get system subprocess details
import wolframalpha  # compute answers
import pyttsx3  # conversion of text to speech
import tkinter  # building gui
import json  # to read json file
import random
import operator
import speech_recognition as sr  # assistant recognizes voice
import datetime
import wikipedia  # search on wiki
import webbrowser  # websearch
import spotipy
import os
import winshell
import pyjokes  # python jokes
import feedparser  # to read rss feed - format for reguarly changing web congtent
import smtplib  # to send mail to internet machine with smtp
import ctypes  # c compatible data types
import time
import requests  # for making get and post requests
import shutil  # high level file operations
from twilio.rest import Client  # making calls and messages
from clint.textui import progress  # command line interface tools
from ecapture import ecapture as ec  # capturing images from camera
from bs4 import BeautifulSoup  # scrape info from webpages
import win32com.client as wincl  # windows api from python
from urllib.request import urlopen  # fetching urls

engine = pyttsx3.init('sapi5')
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[1].id)

username = 'Your_username'
clientID = 'Your_clientID'
clientSecret = 'Your_clientSecret'
redirectURI = 'http://google.com/callback/'

oauth_object = spotipy.SpotifyOAuth(clientID, clientSecret, redirectURI)
token_dict = oauth_object.get_access_token()
token = token_dict['access_token']
spotifyObject = spotipy.Spotify(auth=token)
user_name = spotifyObject.current_user()


def speak(audio):
    engine.say(audio)
    engine.runAndWait()


def wish():
    hour = int(datetime.datetime.now().hour)
    if (hour >= 0 and hour < 12):
        speak("Good Morning !")
    elif (hour >= 12 and hour < 18):
        speak("Good Afternoon !")
    else:
        speak("Good Evening !")
    assistant_name = ("Pippi")
    speak("Nice to meet you ! I am your assistant ")
    speak(assistant_name)


def uname():
    speak("What should I call you")
    uname = takeCommand()
    speak("Welcome")
    speak(uname)
    columns = shutil.get_terminal_size().columns

    print("#####################")
    print("Welcome ", uname)
    print("#####################")
    speak("How can I help you today")


def takeCommand():
    # obtain audio from the microphone
    r = sr.Recognizer()
    with sr.Microphone() as source:
        print("Listening")
        r.pause_threshold = 1
        audio = r.listen(source)

    # recognize speech using Google Speech Recognition
    try:
        print("Recognizing...")
        query = r.recognize_google(audio, language='en-in')
        print(f"User said : {query}\n")
    except Exception as e:
        print(e)
        print("Unable to Recognize your voice.")
        return "None"
    return query


if __name__ == '__main__':
    # def clear():
    #     lambda: os.system('cls')
    #
    #
    # clear()
    lambda: os.system('cls')
    wish()
    uname()

    while True:
        query = takeCommand().lower()

        if 'wikipedia' in query:
            speak('Searching Wikipedia...')
            query = query.replace("wikipedia", "")
            results = wikipedia.summary(query, sentences=3)
            speak("According to Wikipedia")
            print(results)
            speak(results)

        elif 'open google' in query:
            speak("Here you go to Google\n")
            webbrowser.open("google.com")

        elif 'open youtube' in query:
            speak("Here you go to Youtube\n")
            webbrowser.open("youtube.com")


        elif 'time' in query:
            current_time = time.strftime("%H:%M:%S")
            speak(f"The time is {current_time}")

        elif 'how are you' in query:
            speak("I am fine, Thank you")
            speak("How are you")

        elif 'fine' in query or "good" in query:
            speak("It's good to hear that you are fine")

        elif ("what's your name" in query or "What is your name" in query):
            speak("My friends call me Pippi")
            print("My friends call me Pippi")

        elif 'joke' in query:
            speak(pyjokes.get_joke())

        elif "calculate" in query:

            app_id = "Wolframalpha api id"
            client = wolframalpha.Client(app_id)
            indx = query.lower().split().index('calculate')
            query = query.split()[indx + 1:]
            res = client.query(' '.join(query))
            answer = next(res.results).text
            print("The answer is " + answer)
            speak("The answer is " + answer)

        elif 'shutdown system' in query:
            speak("Hold On a Sec ! Your system is on its way to shut down")
            subprocess.call('shutdown / p /f')

        elif "restart" in query:
            subprocess.call(["shutdown", "/r"])

        elif ('song' in query or 'play' in query):
            print(json.dumps(user_name, sort_keys=True, indent=4))

            while True:
                print("Welcome to the project, " + user_name['display_name'])
                print("0 - Exit the console")
                print("1 - Search for a Song")
                user_input = int(input("Enter Your Choice: "))
                if user_input == 1:
                    print ("Enter the song you want me to play: ")
                    # obtain audio from the microphone
                    r = sr.Recognizer()
                    with sr.Microphone() as source:
                        print("Listening")
                        r.pause_threshold = 1
                        audio = r.listen(source)
                    # recognize speech using Google Speech Recognition
                        try:
                            print("Recognizing...")
                            search_song = r.recognize_google(audio, language='en-in')
                            print(f"User said : {search_song}\n")
                        except Exception as e:
                            print(e)
                            print("Unable to Recognize your voice.")

                    results = spotifyObject.search(search_song, 1, 0, "track")
                    songs_dict = results['tracks']
                    song_items = songs_dict['items']
                    song = song_items[0]['external_urls']['spotify']
                    webbrowser.open(song)
                    print('Song has opened in your browser.')
                elif user_input == 0:
                    print("Good Bye, Have a great day!")
                    break
                else:
                    print("Please enter valid user-input.")

        elif 'exit' in query:
            speak("Thanks for giving me your time")
            exit()
