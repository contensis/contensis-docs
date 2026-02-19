1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Brand Voice

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 20 October 2025

## Properties

Name

Type

Description

Example

**name**

string

Distinct name of a Brand Voice. The character limit of the name is 50 characters.

Contensis: Event

**id**

string

The id of a Brand Voice. The Id must be unique with no spaces. The id cannot use the reserved keyword of 'default'.

contensis-event

**description**

string

The description is used just to add some context to the Brand Voice. The description field has a character limit of 128 characters.

Contensis event brand voice to help keep it consistent

**training**

object

Training data to use for the Brand Voice.

**isDefaultProjectBrandVoice**

boolean

Can set a default Brand Voice to be used for a project so that you dont need to specify one each time.

**summary**

string

The summary of a Brand Voice to give context.

The brand voice is approachable yet knowledgeable, blending clarity with helpful authority to guide readers through complex content personalisation concepts in an encouraging and pragmatic way.

**tone**

string

Sets the general tone for the Brand Voice for when getting content back from an AI model. This can also be generated via an AI agent in the CMS UI.

conversational and informative

**personalityTraits**

string

Sets the personality for the Brand Voice for when getting content back from an AI model. This can also be generated via an AI agent in the CMS UI.

friendly, supportive, knowledgeable, practical

**languageComplexity**

string

Sets the language complexity for the Brand Voice for when getting content back from an AI model. This can also be generated via an AI agent in the CMS UI

simple to intermediate

**sentenceStructure**

string

Sets the sentence structure for the Brand Voice for when getting content back from an AI model. This can also be generated via an AI agent in the CMS UI.

short to medium-length, clear and direct

**vocabularyChoices**

string

Sets the vocabulary choice for the Brand Voice for when getting content back from an AI model. This can also be generated via an AI agent in the CMS UI.

industry terminology explained clearly, approachable phrasing

**useOfLiteraryDevices**

string

Sets the literary devices for the Brand Voice for when getting content back from an AI model. This can also be generated via an AI agent in the CMS UI.

occasional rhetorical questions, direct address (\\"you\\"), analogies, gentle reassurance

**uniqueCharacteristics**

string

Sets the unique characteristics for the Brand Voice for when getting content back from an AI model. This can also be generated via an AI agent in the CMS UI.

breaks down complex ideas into manageable steps; reassures and motivates the reader; uses inclusive language to demystify digital concepts

**detectedReadingEaseScore**

number

This is the detected reading score that is generated. This will give a score based on other fields in the Brand Voice. This can be generated via the CMS UI from and AI agent call.

**readingEaseOverride**

string

This is to override the generated reading score.

Difficult

**inclusivity**

object

Contains a set of properties to help define certain language to use or avoid in AI created content.

**termsToAvoid**

string

A comma seperated string of terms to avoid in AI generated content.

synergy

**version**

object

Version object for Brand Voice request

## Example

Example POST data with all properties assigned

JSON

```
{
    "name": "Contensis: Event",
    "id": "contensis-event",
    "description": "Contensis event brand voice to help keep it consistent",
    "training": {
        "text": "Text to train the model and generate a customized brand voice",
        "urls": [
            "https://www.contensis.com/community/blog/content-personalisation-101-what-it-is-why-it-matters-and-how-to-do-it-well"
        ]
    },
    "isDefaultProjectBrandVoice": false,
    "summary": "The brand voice is approachable yet knowledgeable, blending clarity with helpful authority to guide readers through complex content personalisation concepts in an encouraging and pragmatic way.",
    "tone": "conversational and informative",
    "personalityTraits": "friendly, supportive, knowledgeable, practical",
    "languageComplexity": "simple to intermediate",
    "sentenceStructure": "short to medium-length, clear and direct",
    "vocabularyChoices": "industry terminology explained clearly, approachable phrasing",
    "useOfLiteraryDevices": "occasional rhetorical questions, direct address (\"you\"), analogies, gentle reassurance",
    "uniqueCharacteristics": "breaks down complex ideas into manageable steps; reassures and motivates the reader; uses inclusive language to demystify digital concepts",
    "detectedReadingEaseScore": 38,
    "readingEaseOverride": "Difficult",
    "inclusivity": {
        "avoidCulturalOrReligiousReferences": true,
        "useGenderNeutralNounsAndPronouns": true,
        "avoidIdiomsSlangAndAcronyms": true
    },
    "termsToAvoid": "synergy",
    "version": {
        "versionNo": "0.1"
    }
}
```