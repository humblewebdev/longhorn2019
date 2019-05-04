# Alexa, Ask Me About PHP!

> Omni Adams

"I've spent most of my life talking to inanimate objects. Now, they're responding."

## Beer

"Yeast eat sugar, and pee out alcohol and fart out CO2. I know, tasty, right?"

*Explanation of brewing beer and measuring stuff.*

- A simple, but difficult to remember algorithm is required to determine the amount of sugar, based on it's type that is required for a certain volume of water.
- Alexa Skill created to calculate the amount of sugar required.

## Building the Skill

- Visit [developer.amazon.com](https://developer.amazon.com) and look up Alexa Skills Kit
- Choose the type that fits (e.g. Flash Briefing, Smart Home, Video, etc.). For this one, choose "Custom".
- A few templates exist (e.g. Fact Skill, Quiz Game Skill, High-Low Game skill). We choose "Start from Scratch".
- Different "things" a skill does are called "intents". For this one, we're calling the **intent** "calc".
- Interaction is handled with "utterances". Keywords the user will say. "brew calc"
    - "Alexa, ask brew calc how much DME to go from ten-sixty to ten-ninety"
    - template "how much {extract} should I add to raise {actual} to {expected}"
    - You specify the types of arguments, shown above, that are pulled out of the command
        - {extract} can be a list of items. We specify it can be either "DME" or "LME".
        - You can also specify multiple, slight variations on the phrase so that there can be some forgiveness if the user doesn't say it exactly right.
- Specify the region in which the AWS task will run.
- Save model, a manifest will save and it will start to build

## On your server

You specify where you want to send the requests too.

A JSON body is posted to you of the following:

```json
{
    "version": "1.0",
    "session": {}, // Used if you want interaction
    "context": {}, // Device used on
    "request": {}  // All the stuff
}
```

> Look in the docs for the expected shape of the request. Kind of complicated. You will also have to cast some values on the server side.

## Response format: There are lots of other stuff available to send; see the docs

```json
{
    "version": "1.0",
    "response": {
        "shouldEndSession": bool,  // If we want to continue interaction.
        "outputSpeech": {
            "type": "PlainText",
            "text": "..."
        }
    }
}
```

To publish things publicly, there is a certification / publication process. A human will verify the signatures match, and that the key words make sense. They will also smoke test and cover common questions.

Full analytics available on any skills you build.
