# [Twitch Stream] Building a Meetup chatbot using Rasa Stack

In release 0.12, Rasa introduced a new TensorFlow-based pipeline for NLU models. This repository contains the code which was used during our Twitch live coding stream on 28/06/2018. During the stream we built a Meetup chatbot, capable of recommending meetups to attend, make RSVPs for the events and recommend public transport routes to get to the venue. The goal of building this chatbot is to demonstrate how we can use Rasa NLU TensorFlow pipeline to build intelligent chatbots which can understand multiple intents per input.


```text
User: Hello.
Bot: Hey, how can I help you?
User: I am new to London and I am looking form fitness meetups to attend. Any suggestions?
Bot: Sure. There is a 'Tennis in Central London' meetup happening in London. They are having an event 'Social Tennis' on 2018-07-05. Would you like to join the meetup?
User: Yes, please.
Bot: Done! You have joined the meetup. Would you like to attend their nearest event?
User: Yes. Can you also tell me how can I get to the venue from Baker Street?
Bot: All done. I have booked you a spot at 'Social Tennis' which is happening on 2018-07-05. Here are the directions for getting to the venue using a public transport: Walk to Baker Street Underground. Catch a Bakerloo line to Piccadilly Circus. Change to Piccadilly line to Knightsbridge. Walk to Hyde Park.
User: Thanks a lot! Goodbye.
Bot: You are very welcome!
Bot: Bye bye.

```

The chatbot includes live data APIs. In order to access the data yourself, you will need to get the API keys and store them as environmental variables. Below are instructions of how to do it:
* Meetup API:
	1. Get the API key [here](https://secure.meetup.com/meetup_api/key/)
	2. Copy the key, open your command line and execute:
		* Ubuntu and Mac OS:
			```
			export MEETUP_KEY=*your_key*
			``` 
		* Windows:		
			```
			set MEETUP_KEY=*your_key* 
			```

* Google Directions API:
	1. Get the API key by following the instructions written in a section [Activate the API and get an API key](https://developers.google.com/maps/documentation/directions/start)
	2. Copy the key and in your command line execute:
		* Ubuntu and Mac OS:
			```
			export GOOGLE_KEY="your_api_key" 
			```
		* Windows:
			```
			set GOOGLE_KEY="your_api_key"
			```

## Versions of the software used in this tutorial:

* Python 3.6  
* Rasa NLU 0.12.3  
* Rasa Core 0.9.6  

## How to use this repository:
1. Clone or download the repository and install Rasa NLU and Rasa Core:
```
pip install -r requirements.txt
```
2. Install a spacy language model:
```
python -m spacy download en
```
3. Watch the stream and implement a bot from scratch by using the code inside the directory called 'Stream_Code'.

4. You can load and chat with the bot at any time by executing the following command from the main directory of this repository (don't forget to set the API keys):
```
python -m rasa_core.run -d models/current/dialogue -u models/current/nlu_model
```


## Useful resources:
* [Rasa NLU installation](https://nlu.rasa.com/installation.html) - guidelines on how to install Rasa NLU.
* [Rasa Core installation](https://core.rasa.com/installation.html) - guidelines on how to install Rasa Core.
* [Supervised Word Vectors from Scratch in Rasa NLU](https://medium.com/rasa-blog/supervised-word-vectors-from-scratch-in-rasa-nlu-6daf794efcd8) - Rasa blog post on the new TensorFlow pipeline.
* [How to handle multiple intents per input using Rasa NLU TensorFlow pipeline](https://medium.com/rasa-blog/how-to-handle-multiple-intents-per-input-using-rasa-nlu-tensorflow-pipeline-75698b49c383) - A step-by-step tutorial on how to build chatbots using Rasa NLU TensorFlow pipeline.
* [Docs: Processing Pipeline](https://nlu.rasa.com/pipeline.html) - Official Rasa documentation on processing pipelines.
* [Rasa NLU Gitter](https://gitter.im/RasaHQ/rasa_nlu) and [Rasa Core Gitter](https://gitter.im/RasaHQ/rasa_core) - Places where Rasa community hangs out.

