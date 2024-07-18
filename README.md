                                       ___                            _   
                                      / __\___  _ __ _ __ _   _ _ __ | |_ 
                                     / /  / _ \| '__| '__| | | | '_ \| __|
                                    / /__| (_) | |  | |  | |_| | |_) | |_ 
                                    \____/\___/|_|  |_|   \__,_| .__/ \__|
                                                               |_|        
# Python utilities to corrupt some input text

Script that takes some text as input and randomly modify words by using either
- Levenshtein edit operations

Corruptions can be used as a data augmentation technique, or to benchmark NLP models robustness to misspells and/or synonyms.
## Set up
Requirements: numpy, requests, joblib
```bash
$ pip install git+https://github.com/aylliote/corruption.git@master
```
## Exemple
```python
from corruption import Corrupter

corrupter = Corrupter()
sample = "Il fut attiré par cette belle couleur et décida d’y séjourner quelque temps"
corrupter.corrupt(sample, syn=1, typo=0)
>>> 'Il fut prédisposé par une charmante coloriant et décida d’y habiter pour période'

corrupter.corrupt(sample, syn=0, typo=3)
>>> 'Il mfut tatiré par cetet belle colueur et wécida d’y sgjourner quelque temzps'

corrupter.corrupt(sample, syn=2, typo=3)
>>> 'Il fut sujet pax la admirable tilnctorial et décidau d’y habiter auprès âge'
```
