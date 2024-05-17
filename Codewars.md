# Check if the strings of the first argument matches with the strings of the second argument:

Example:
```python
solution('abc', 'bc') # returns true
solution('abc', 'd') # returns false
```

Your solution:
```python
def solution(text, ending):
    end=len(ending)
    if text[-end:]==ending: # turn `end` to negative to get the last indices `text` and compare it to `ending`
        return True
    # if not equal,
    return False
```

Solution (best practice):
```python
def func(start,end):
	return start.endswith(end)
  ```
# Sum of numbers between a and b from the min number to max.

Examples (with explanation): 
```python
(1, 0) --> 1 (1 + 0 = 1)
(1, 2) --> 3 (1 + 2 = 3)
(0, 1) --> 1 (0 + 1 = 1)
(1, 1) --> 1 (1 since both are same)
(-1, 0) --> -1 (-1 + 0 = -1)
(-1, 2) --> 2 (-1 + 0 + 1 + 2 = 2)
```

Your solution:
```python
def get_sum(a,b):
    #good luck!
    r=range(a,b+1) # +1 because we want the `limit` to be included
    if b<a:
        r=range(b,a+1) 
    return sum(i for i in r) if a!=b else a or b
```

Solution (best practice):
```python
def get_sum:
	return sum(range(min(a,b),max(a,b))
```

# Get middle character. If odd, print middle. If even, print 2 middle.

Examples:
```python
Kata.getMiddle("test") should return "es"

Kata.getMiddle("testing") should return "t"

Kata.getMiddle("middle") should return "dd"

Kata.getMiddle("A") should return "A"
```

Your solution:
```python
import math 
def get_middle(s):
    ls=len(s)
    if ls%2 == 0: # even
        return s[ls//2-1:ls//2+1]
    # odd 
    return s[math.floor(ls/2)]
```

Best practice:
```python
def get_middle(s):
    index, odd = divmod(len(s), 2)
    return s[index] if odd else s[index - 1:index + 1]
```

# Who likes it?

Example:
```python
[]                                -->  "no one likes this"
["Peter"]                         -->  "Peter likes this"
["Jacob", "Alex"]                 -->  "Jacob and Alex like this"
["Max", "John", "Mark"]           -->  "Max, John and Mark like this"
["Alex", "Jacob", "Mark", "Max"]  -->  "Alex, Jacob and 2 others like this"
```

Your solution:
```python
def likes(names):
    # your code here
    sentence=["no one likes this","{} likes this","{} and {} like this", "{}, {} and {} like this","{}, {} and {} others like this"]
    if len(names)<4:
        return sentence[len(names)].format(*names[:3])
    
    return sentence[4].format(*names[:2],len(names)-2
```

Best practice:
```python
def likes(names):
    # make a dictionary d of all the possible answers. Keys are the respective number
    # of people who liked it.
    
    # {} indicate placeholders. They do not need any numbers but are simply replaced/formatted
    # in the order the arguments in names are given to format
    # {others} can be replaced by its name; below the argument "others = length - 2"
    # is passed to str.format()
    d = {
        0: "no one likes this",
        1: "{} likes this",
        2: "{} and {} like this",
        3: "{}, {} and {} like this",
        4: "{}, {} and {others} others like this"
        }
    length = len(names)
    # d[min(4, length)] insures that the appropriate string is called from the dictionary
    # and subsequently returned. Min is necessary as len(names) may be > 4
    
    # The * in *names ensures that the list names is blown up and that format is called
    # as if each item in names was passed to format individually, i. e.
    # format(names[0], names[1], .... , names[n], others = length - 2
    return d[min(4, length)].format(*names, others = length - 2)
```


# Valid Braces

Example:
```python
"(){}[]"   =>  True
"([{}])"   =>  True
"(}"       =>  False
"[(])"     =>  False
"[({})](]" =>  False
```


Your solution:
```python
def valid_braces(string,iteration=0):
    # i dont know anymore :(
    
    # track whether or not to execute a recurse
    recurse=False 
    
    # checker for what a valid brace looks like
    full=('()','{}','[]') 
    
    # a copy of the thing we will iterate on (because we shouldn't modify an object 
    # while we iterate through it, so we will modify the `new` instead)
    new=list(string[:]) 
    
    # add new argument (iteration) so it has to recurse at least once to return True. 
    # This is also our exit condition if the string is valid.
    if iteration>0 and len(string) == 0: 
        return True
    
    # iterate through the given string but using its indices
    for i in range(len(string)): 
        curr=string[i]
        
        # only make a pair if the current index isn't the last
        if i != len(string)-1: 
            nex=string[i+1]
            pair=curr+nex
            
            # check if the pair matches any in `full`
            if pair in full: 
                # modify `new`
                new.remove(curr) 
                new.remove(nex)
                
                # recurse now possible because we want to stop iterating through the list
                # after finding a match in `full`
                recurse=True 
            
                break
    if recurse==True:     
        # turn the list `new` to a string so that `string` gets reassigned the new values of `new`
        new=''.join(i for i in new)
        string=new
        # call the function with the new string and increment its `iteration`
        return valid_braces(string,iteration+1)
    
    # This code only executes if it fails the first condition in the loop 
    # (ie the current index is the last meaning there is no possible pair for it to have
    # so it will always be an invalid brace)
    return False

# A valid brace should eventually have 0 length with more than 1 iteration because 
# the for loop should at least find 1 pair in `full`, causing the recursion and finding a new pair
# in the new string, eventually crossing out all the pairs.
```


Best practice:
```python
def valid_braces(string):
	# if string is empty
	if len(string)==0:
		return False
    braces = {"(": ")", "[": "]", "{": "}"}
    stack = []
    for character in string:
	    # if encountered an opening character
        if character in braces.keys():
	        # for every opening character must have a closing one. The goal is to clear the stack.
            stack.append(character)
            
        # if encountered a closing character
        else:
	        # 2 cases
	        # if there was no opening character or
	        # if the closing character does not match the dict value of the last opening character. One of these being true automatically results in invalid brace
	        # this deletes an element off `stack` but returns False if one of the condition is True, so the `len(stack)==0` cannot execute.
            if len(stack) == 0 or braces[stack.pop()] != character:
                return False
    return len(stack) == 0  
```


Best imo:
```python
def validBraces(s):
	if len(s)==0:
		return False
	while '{}' in s or '()' in s or '[]' in s:
	  s=s.replace('{}','')
	  s=s.replace('[]','')
	  s=s.replace('()','')
	return s==''
```

# Sort the odd

Example:
```python
[7, 1]  =>  [1, 7]
[5, 8, 6, 3, 4]  =>  [3, 8, 6, 5, 4]
[9, 8, 7, 6, 5, 4, 3, 2, 1, 0]  =>  [1, 8, 3, 6, 5, 4, 7, 2, 9, 0]
```


Your solution:
```python
def sort_array(source_array):
    # create a copy of the given list because we need to modify the list but not the one
    # we iterate through
    copy_array=source_array[:]
    # we will store 2 things: odd numbers and its index
    odd_num=[]
    indice=[]
    
    # iterate through the list but through its indices
    for i in range(len(source_array)):
        # if the number is odd,
        if source_array[i]%2:
            # add its index
            indice.append(i)
            # add the number
            odd_num.append(source_array[i])
            # remove the element in the copy
            copy_array.remove(source_array[i])
    # after going through all items, sort the found odd numbers (ascending by default)
    odd_num.sort()
    # insert the sorted odd numbers using the kept indices
    for i in range(len(odd_num)):
        copy_array.insert(indice[i],odd_num[i])
        
    return copy_array
```


Best practice:
```python
def sort_array(arr):
  odds = sorted((x for x in arr if x%2 != 0), reverse=True)
  return [x if x%2==0 else odds.pop() for x in arr]
```


# Simple Pig Latin

Example:
```python
pig_it('Pig latin is cool') # igPay atinlay siay oolcay
pig_it('Hello world !')     # elloHay orldway !
```

Your solution:
```python
import re
def pig_it(text):
    #your code here
    
    # Split the string upon encountering a whitespace 
    text_str=text.split(" ")
    
    # Loop through said list
    for substr in text_str:
        # Check if current item matches A-Z, a-z, 0-9, _
        # This is to filter out punctuations
        if re.match(r"\b\w+\b",substr):
            # Take the first item in the current item
            first_l=substr[0]
            # Reassign the item in the current index with the modifications
            text_str[text_str.index(substr)]= f"{substr[1:]+first_l+'ay'}"
    
    # Reassign the list with a joined string of all the items,
    # using a whitespace as a separator between the items
    text_str=" ".join(text_str)
    
    return text_str
```


Best practice:
```python
def pig_it(text):
    lst = text.split()
    return ' '.join( [word[1:] + word[:1] + 'ay' if word.isalpha() else word for word in lst])
```

# Directions Reduction

Example:
```python
["NORTH", "SOUTH", "SOUTH", "EAST", "WEST", "NORTH", "WEST"] -> ["WEST"]
["NORTH", "SOUTH", "EAST", "WEST"] -> []
["NORTH", "EAST", "WEST", "SOUTH", "WEST", "WEST"] -> ["WEST", "WEST"]
```

Your solution:
```python
def dir_reduc(arr):
    # Add a separator at the end of every element in the list.
    # Ideally, a whitespace since we will use `.split()`.
    for i in arr:
        arr[arr.index(i)]+=" "
    
    # Turn the argument's elements into an str.
    string="".join(arr)
    
    # Track the previous state of the str object.
    previous=""
    
    while string!=previous:
        previous=string

        # Replace string with the following combinations to an empty string. 
        # This essentially removes the strings if they match 1:1 with the combinations.
        string=string.replace("NORTH SOUTH ","")
        string=string.replace("SOUTH NORTH ","")
        string=string.replace("EAST WEST ","")
        string=string.replace("WEST EAST ","")
        
    # Once nothing can be replaced i.e. `previous == string`,
    # Exit the function and return the following:
    return string.split()
```

Best (imo):
```python
def dir_reduc(arr):
	string=" ".join(arr)
	string_new=string.replace("NORTH SOUTH ","").replace("SOUTH NORTH ","").replace("EAST WEST ","").replace("WEST EAST ","")
	return dir_reduc(string_new.split(" ")) if len(string_new)<len(string) else string_new
```

# Most common words (unsolved)


Your solution:
```python
def top_3_words(text):
    def has_letter(text):
        for i in text:
            if i.isalpha():
                return True
        return False
        
    # Notice how the apostrophe isn't here.
    non_words="~!@#$%^&*()-_=+[]\\{}|;:\",./<>?"
    
    # Clean out the non-alphabetic-and-apostrophe before we start counting unique words. Not a generator because I want to maintain the str object.
    for i in text:
        if i in non_words:
            text=text.replace(i,"")
    print(f"text:{text}")
    print(f"text.lower().etc: {text.lower().split()}")
    # Clean out the numbers and single apostrophes.
    words=[i for i in text.lower().split() if has_letter(i)]
    print(f"words: {words}")
    # Dict to store all the counts of unique words
    d={}
    
    # We'll loop using the set, counting each element that occurs in it.
    unique=set(words)
    print(f"unique: {unique}")
    for i in unique:
        print(i,"from unique")
        d[i]=words.count(i)
    
    print(f"d: {d}")
    # New d that is sorted in descending order.
    new_d=dict(sorted(d.items(),key=lambda item:item[1],reverse=True))
    print(f"new_d: {new_d}")
    # Clean the dict to only include up to 3 elements. If 2 or less, this won't run.
    while len(new_d)>3:
        new_d.popitem()
    
    # Return the value-pair of whatever's left in the "new_d".
    return [i for i in new_d.keys()]
        
print(top_3_words("iPriEvjAgqliEv iPriPrQzIwltQzIwlt  iPr ElmDVPrEuaiEv iPr 'MNwwxMYxGWKJS jAgqlQzIwlt  jAgqliPr jAgqloeJTiiEvQzIwltiPriEvElmDVPrEuaoeJTiiPraRCDe iEvQzIwltElmDVPrEua ElmDVPrEua aRCDexMYxGWKJSjAgqliPriEv xMYxGWKJS'MNwwaRCDe 'MNwwiPraRCDeiPrjAgql  ElmDVPrEuaiPrjAgqliPrnwKI iPr  oeJTiiEvoeJTijAgqliPrnwKI xMYxGWKJS QzIwltoeJTijAgql iPrElmDVPrEuajAgql'MNwwQzIwltiPrnwKIiEv nwKIiPrnwKI iPriPrnwKIiEviEviPrjAgqlnwKI iPrElmDVPrEuaxMYxGWKJS QzIwltiEvnwKI 'MNwwnwKI jAgqljAgqlQzIwltnwKIjAgqliPr iPrnwKInwKIiEvaRCDe"))
```

# Simple decrypt algo

Example:
```python
'$aaaa#bbb*cc^fff!z' gives '43200300000000000000000001'
   ^    ^   ^  ^  ^         ^^^  ^                   ^
  [4]  [3] [2][3][1]        abc  f                   z
  
'z$aaa#ccc%eee1234567890' gives '30303000000000000000000001'
 ^  ^   ^   ^                    ^ ^ ^                    ^
[1][3] [3] [3]                   a c e                    z
```

Your solution:
```python
def top_3_words(text):
    text=text.lower()
    # Notice how the apostrophe isn't here.
    non_words="~!@#$%^&*()-_=+[]\\{}|;:\",./<>?"
    
    # Clean out the non-alphabetic-and-apostrophe before we start counting unique words. Not a generator because I want to maintain the str object.
    for i in text:
        if i in non_words:
            text=text.replace(i,"")
            
    print(f"text:{text}")
    print(f"text.split(): {text.split()}")
    
    # Clean out single apostrophes.
    words=[i for i in text.split() if i!="'"*len(i)]
    print(f"words: {words}")
    # Dict to store all the counts of unique words
    d={}
    
    # We'll loop using the set, counting each element that occurs in it.
    unique=set(words)
    print(f"unique: {unique}")
    
    if len(text)>1000:
        for u_word in unique:
            d[u_word]=0
            for word in words:
                d[u_word]+=word.count(u_word)
    else:
        for u_word in unique:
            d[u_word]=words.count(u_word)
    print(f"counted: {d}")
    
    # New d that is sorted in descending order.
    new_d=dict(sorted(d.items(),key=lambda item:item[1],reverse=True))
    print(f"desc: {new_d}")
    
    # Clean the dict to only include up to 3 elements. If 2 or less, this won't run.
    while len(new_d)>3:
        new_d.popitem()
    
    # Return the value-pair of whatever's left in the "new_d".
    return [i for i in new_d.keys()]

```

Best practice:
```python
def decrypt(test_key):
	return "".join( str(test_key.count(i)) for i in "abcdefghijklmnopqrstuvwxyz" )
```

# Greed is good



Example:
```python
Throw       Score
 ---------   ------------------
 5 1 3 4 1   250:  50 (for the 5) + 2 * 100 (for the 1s)
 1 1 1 3 1   1100: 1000 (for three 1s) + 100 (for the other 1)
 2 4 4 5 4   450:  400 (for three 4s) + 50 (for the 5)
```

Your solution
```python
def score(dice):
    # Map out the possible values and their value.
    d={"111":1000,"222":200,"333":300,"444":400,"555":500,"666":600,"1":100,"5":50}
    
    # Change the dice into an str object, but the numbers from the argument (dice) are sorted in asc.
    str_dice="".join([str(i) for i in sorted(dice)])
    
    # Tracker to see changes. First state is always empty.
    prev=""
    
    # Tracker to see score. First state is always empty.
    points=[]
    
    # Loop. Only stop if there are no more changes.
    while str_dice!= prev:
        prev=str_dice
        for i in d.keys():
            if i in str_dice:
                # Replace only the FIRST occurrence. 
                str_dice=str_dice.replace(i,"",1)
                
                # Put the points into the tracker.
                points.append(d[i])
                
    # Return the sum of accumulated points.
    return sum(points)
```

Best practice:
```python
def score(dice):
    dice_counter=[0,0,0,0,0,0]
    triple=[1000,200,300,400,500,600]
    bonus=[100,0,0,0,50,0]
    points=0
    for i in dice:
    # Count the numbers using the argument as indices. 
        dice_counter[i-1]+=1
    # Take the index position, and its index-position value.
    for i,counted in enumerate(dice_counter):
    # Increment the "points" using the "triple" only if the count is 3 or more, else 0.
    # Increment the "points" using the "bonus" but the multiplier is based off of the remainder of "counted" being divided by 3. This is so that the multiplier doesn't reach 3, only 2 or 1.
        points+=(triple[i] if counted>=3 else 0) + bonus[i] * (counted%3)
    return points
```

