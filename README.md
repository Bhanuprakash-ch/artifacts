# artifacts

We will be using git release assets to manage artifact drops. Where previously we relied on static URL’s we will now grab the necessary artifacts based on meta data provided by the git release api. This move will also increase the visibility of our build artifacts by putting them right next to our code. 

Every repo that wants to use git assets for artifact management should list their artifact types in artifacts.json. artifacts.json.sample shows the structure and data that should exist in the file.

###Sample artifacts.json
```
"ORG/REPO": [{
		"ARTIFACT_TYPE": {
			"name": "ARTIFACT name",
			"description": "ARTIFACT description"
		}
	}, {
		"ARTIFACT_TYPE": {
			"name": "ARTIFACT name",
			"description": "ARTIFACT description"
		}
	}]
```
The top level data structures will be ORG/REPO combination followed by a list of all the artifact types for that repository.
 * ARTIFACT_TYPE - any name of your choosing can't be changed 
 * name(mandatory) - human readable name for the artifact type, mandatory for initial merge 
 * description(mandatory) - description of the type, mandatory for initial merge 

####Rules/Regulations 
 * artifact types are immutable. When new artifact types are merged into master they become permanent after 24 hours. 
 * only a single artifacts.json file will ever exist
