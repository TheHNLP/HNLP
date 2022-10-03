# The HNLP database specification
*Version 1.1.0*<br />
*Last updated October 2, 2022*

This document is a specification for Human Name Listing Project (HNLP) databases that use JSON.

## 1. The "names" object
Each database contains a JSON object, "names", that contains the list of names in
the database.

Each name is defined in an entry in the "names" object, whose key is the name and
the value is a JSON object defining the name.

## 2. Name definitions
A **name definition** is a JSON object that contains the definition of a name, its
details and a list of links sourcing the information in the definition.

### 2.1. Parameters
#### 2.1.1. meanings
An array of strings, listing the meanings of a name.

#### 2.1.2. gender
A string indicating the gender a name is typically associated with.
The possible values are "m" for male, "f" for female, and "x" for gender-neutral.

#### 2.1.3. origins
An array of strings listing the origins of a name.

#### 2.1.4. variations
An array of strings listing the variations of a name.

#### 2.1.5. nicknames
An array of strings listing the nicknames that are typically associated with a
name.

#### 2.1.6. popularityPercentage
A floating-point number, from 0 to 100, indicating the percentage of people who have
a specific name.

#### 2.1.7. popularityIndex
An integer indicating the popularity index of a name.

#### 2.1.8. sources
An array of strings listing the sources used for information on the name definition.

## 3. Example
This is an example of a simple database, with a name definition.

`
<pre>
{
	"names": {
		"Name1": {
			"gender": "m",
			"meaning": "Meaning1"
			"nicknames": [
				"Nickname1"
			],
			"popularityPercentage": 1,
			"popularityIndex": 100,
			"sources": [
				"https://example.com"
			]
		}
	}
}
</pre>
`
