# trie-cli-global

A CLI that allows a user to update or see a data structure that is hosted globally.

(IMPORTANT: PYTHON 3.9.6 MUST BE INSTALLED!!)

Please Note: 
- The README in the Github will be different from the one in PYPI. This is because the company that is requesting this project will most likely ask me to make the repo       private to keep others from looking at the code as well as development procedure. This is the full README. The one in PYPI simply shows commands and how to use. 
- ```pyproject.toml``` and ```setup.cfg``` were used initially. However, the main source of deployment is from ```setup.py```. Some sources claim that one is better than the other. I have decided to go with ```setup.py``` for simplicity. I have left the other two files up there to be viewed. 
    
Tools Used and How: 
- AWS was used to store the Trie Data Structure. Using AWS' boto3, a pickle file is stored in an s3 bucket. 
    
- A Flask REST API was used to handle client requests and interactions. It is hosted on Heroku and the web URL is https://global-trie-     cli.herokuapp.com/updatetrie/COMMAND/OPTIONAL_WORD. (Word is optional depending on the command. See the usage instructions below). 
    
- Click was used to create the CLI. When given the correct commands, it will send a GET request via the REQUESTS Library. The returned value is printed afterwards. 
    
- The project was hosted on PYPI. Link is Here (https://pypi.org/project/trie-cli-global/). Install the project via ```pip install trie-cli-global```. 
    
## Installation

Use [pip](https://pip.pypa.io/en/stable/) to install trie-cli-global.

```bash
pip install trie-cli-global
```

## Usage

# To List Trie:
```
trie-cli-global list
```

# To add word to Trie:
```
trie-cli-global add YOUR_WORD
```

# To remove word from Trie:
```
trie-cli-global remove YOUR_WORD
```

# To check if word is from Trie:
```
trie-cli-global check YOUR_WORD
```

# To get recommendations from a prefix:

```
trie-cli-global recommend YOUR_PREFIX
```

__________________________________________________________________________________________________________



## Test with Curl

# To Get Words in Trie:
```curl -X GET "https://global-trie-cli.herokuapp.com/updatetrie/list"```

# To add word to Trie:
```curl -X GET https://global-trie-cli.herokuapp.com/updatetrie/add/[WORD]"```

# To check word to Trie:
```curl -X GET "https://global-trie-cli.herokuapp.com/updatetrie/check/[WORD]"```

# To Remove Word from Trie:
```curl -X GET https://global-trie-cli.herokuapp.com/updatetrie/remove/[WORD]"```

# To Get Recommendations from Prefix:
```curl -X GET https://global-trie-cli.herokuapp.com/updatetrie/recommend/[PREFIX]"```
