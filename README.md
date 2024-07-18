```
  ___            _             _____        _      ___                       _           
 | _ \_  _ _____(_)__ _ _ _   |_   _|____ _| |_   / __|___ _ _ _ _ _  _ _ __| |_ ___ _ _ 
 |   / || (_-<_-< / _` | ' \    | |/ -_) \ /  _| | (__/ _ \ '_| '_| || | '_ \  _/ -_) '_|
 |_|_\\_,_/__/__/_\__,_|_||_|   |_|\___/_\_\\__|  \___\___/_| |_|  \_,_| .__/\__\___|_|  
                                                                       |_|               
```

# Python Library Ru Text Corrupter

Script that takes some text as input and randomly modifies given strings, either single strings or a list of strings, by using Levenshtein edit operations, i.e. delete, transpose, replace, insert.

This is the fork of the repo by [el-cornetillo](https://github.com/el-cornetillo/corruption)

This repo first of all adapts the repo to the Russian language, gets rid of the synonym replacement option.
In addition, the current repo fixes the bug of the original repo when the returned strings separates the puctuation symbols.

## How to Set up
Requirements: numpy, requests, joblib
```bash 
$ pip install git+https://github.com/eistakovskii/ru_text_corrupter.git
```
## Example
```python
from corruption import Corrupter

corrupter = Corrupter()
sample = "Я люблю яблоки"
corrupter.corrupt(sample, typo=1)
>>> 'Я любюл яблоки'

corrupter.corrupt(sample, typo=2)
>>> 'Я лблю яблокиц'
```
