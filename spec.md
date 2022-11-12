# The HNLP database specification
*Version 1.2.1*<br />
*Last updated November 11, 2022*

This document is a specification for Human Name Listing Project (HNLP) databases that use JSON.

## 1. Metadata
Every database that uses the HNLP database specification version 1.2.0 or later has a JSON object
with the key "metadata" inside the root element, containing information about the database.

### 1.1. Version number
The metadata includes the major and minor version number of the HNLP database specification
that the database is using. The version number is represented with the major version number,
followed by a period (.), then the minor version number. For example, a database that implements
the HNLP database specification version 1.2.0 would have the version number "1.2" in the metadata.

The version number is represented as a JSON string, with the key "version", inside the metadata
object as defined in Section 1.

## 2. The "names" object
Every database contains a JSON object, "names", that contains the list of names in
the database.

Every name is defined in an entry in the "names" object, whose key is the name and
the value is a JSON object defining the name.

## 3. Name definitions
A **name definition** is a JSON object that contains the definition of a name, its
details and a list of links sourcing the information in the definition.

### 3.1. Parameters
#### 3.1.1. meanings
An array of strings, listing the meanings of a name.

#### 3.1.2. gender
A string indicating the gender a name is typically associated with.
The possible values are "m" for male, "f" for female, and "x" for gender-neutral.

#### 3.1.3. origins
An array of strings listing the origins of a name.

#### 3.1.4. variations
An array of strings listing the variations of a name.

#### 3.1.5. nicknames
An array of strings listing the nicknames that are typically associated with a
name.

#### 3.1.6. popularityPercentage
A floating-point number, from 0 to 100, indicating the percentage of people who have
a specific name.

#### 3.1.7. popularityIndex
An integer indicating the popularity index of a name.

#### 3.1.8. sources
An array of strings listing the sources used for information on the name definition.

## 4. Example
This is an example of a simple database, with a name definition.

<pre>
{
	"metadata": {
		"version": "1.2"
	},
	"names": {
		"Michael": {
			"gender": "m",
			"meanings": [
				"Who is like God?"
			],
			"origins": [
				"biblical"
			],
			"nicknames": [
				"Mike",
				"Mikey"
			],
			"popularityIndex": 12,
			"sources": [
				"Campbell, M. Published September 25, 2021. Michael: Meaning, origin and history of the name Michael. Behind the Name. Retrieved from <https://www.behindthename.com/name/michael>.",
				"Plant, R. Published July 3, 2021. Michael Name Meaning. Verywell Family. Retrieved from <https://www.verywellfamily.com/michael-name-meaning-5115812>."
			]
		}
	}
}
</pre>
