# Ch06
```
# Clock converter 1

minutes_to_convert = 123
hours_decimal = minutes_to_convert/60
hours_part = int(hours_decimal)

minutes_decimal = hours_decimal-hours_part
minutes_part = round(minutes_decimal*60)
print("Hours")
print(hours_part)
print("Minutes")
print(minutes_part)
```


```
# Clock converter 2

minutes_to_convert = 123

hours_decimal = minutes_to_convert/60
hours_part = int(hours_decimal)      

minutes_part = minutes_to_convert%60   

print("Hours")
print(hours_part)
print("Minutes")
print(minutes_part)
```


# CH11
```
# Mashup Game

print("Welcome to the Mashup Game!")
name1 = input("Enter one full name (FIRST LAST): ")              
name2 = input("Enter another full name (FIRST LAST): ")          
space = name1.find(" ")                    
name1_first = name1[0:space]               
name1_last = name1[space+1:len(name1)]     
space = name2.find(" ")                    
name2_first = name2[0:space]               
name2_last = name2[space+1:len(name2)]     
len_name1_first = len(name1_first)                
len_name2_first = len(name2_first)                
len_name1_last = len(name1_last)                  
len_name2_last = len(name2_last)                  
index_name1_first = int(len_name1_first/2)                
index_name2_first = int(len_name2_first/2)                
index_name1_last = int(len_name1_last/2)                  
index_name2_last = int(len_name2_last/2)                  
lefthalf_name1_first = name1_first[0:index_name1_first]                  
righthalf_name1_first = name1_first[index_name1_first:len_name1_first]   
lefthalf_name2_first = name2_first[0:index_name2_first]
righthalf_name2_first = name2_first[index_name2_first:len_name2_first]
lefthalf_name1_last = name1_last[0:index_name1_last]
righthalf_name1_last = name1_last[index_name1_last:len_name1_last]
lefthalf_name2_last = name2_last[0:index_name2_last]
righthalf_name2_last = name2_last[index_name2_last:len_name2_last]
newname1_first = lefthalf_name1_first.capitalize() + righthalf_name1_first.lower()                 #B
newname1_last = lefthalf_name1_last.capitalize() + righthalf_name2_last.lower()
newname2_first = lefthalf_name2_first.capitalize() + righthalf_name1_first.lower()
newname2_last = lefthalf_name2_last.capitalize() + righthalf_name1_last.lower()
print("All done! Here are two possibilities, pick the one you like best!")
print(newname1_first, newname1_last)       
print(newname2_first, newname2_last)      
```
```
# Adventure Game

print("You are on a deserted island in a 2D world.")
print("Try to survive until rescue arrives!")
print("Available commands are in CAPITAL letters.") 
print("Any other command exits the program") 
print("First LOOK around...")
do = input(":: ")
if do == "LOOK":
    print("You are stuck in a sand ditch.")
    print("Crawl out LEFT or RIGHT.")
    do = input(":: ")
    if do == "LEFT":
        print("You see a STARFISH and a CRAB on the sand.")
        print("And you're hungry! Which do you eat?")
        do = input(":: ")
        if do == "STARFISH": 
            print("Oh no! You immediately don't feel well.")
            print("You do not survive :(")
        elif do == "CRAB":
            print("Raw crab should be fine, right? YES or NO.")
            do = input(":: ")
            if do == "YES": 
                print("Ok, You eat it raw. Fingers crossed.")
                print("Food in your belly helps you see a TREE.")
                do = input(":: ")
                if do == "TREE": 
                    print("It's a coconut tree! And you're thirsty!")
                    print("Do you drink the coconut water? YES or NO.")
                    do = input(":: ")
                    if do == "YES": 
                        print("Oh boy. Coconut water and rawcrab don't mix.")
                        print("You do not survive :(")
                    elif do == "NO": 
                        print("Good choice.")
                        print("Look! It's a rescue plane! You made it! \o/")
            elif do == "NO": 
                print("Well, there's nothing else left to eat.")
                print("You do not survive :(")
    elif do == "RIGHT": 
        print("No can do. That side is very slippery.")
        print("You fall very far into some weird cavern.")
        print("You do not survive :(")
else:
    print("You can only do actions shown in capital letters.")
    print("Try again!") 
```

# CH19
```
# Scrabble Game

words = """art
hue
ink
oil
pen
wax
clay
draw
film
form
kiln
line
tone
tube
wood
batik
brush
carve
chalk
color
craft
easel
erase
frame
gesso
glass
glaze
image
latex
liner
media
mixed
model
mural
paint
paper
photo
print
quill
quilt
ruler
scale
shade
stone
style
tools
video
wheel
artist
bridge
canvas
chisel
crayon
create
depict
design
enamel
eraser
fresco
hammer
marble
marker
medium
mobile
mosaic
museum
pastel
pencil
poster
pounce
roller
sculpt
sketch
vellum
visual
acrylic
artwork
cartoon
carving
casting
collage
compass
drawing
engrave
etching
exhibit
gallery
gilding
gouache
painter
palette
pigment
portray
pottery
primary
realism
solvent
stained
stencil
tempera
textile
tsquare
varnish
woodcut
abstract
airbrush
artistic
blending
ceramics
charcoal
contrast
critique
decorate
graffiti
graphite
hatching
maquette
marbling
painting
portrait
printing
quilting
sculptor
seascape
template
animation
cloisonne
decoupage
encaustic
engraving
landscape
porcelain
portfolio
sculpture
secondary
stippling
undertone
assemblage
brightness
creativity
decorative
exhibition
illustrate
lithograph
paintbrush
photograph
proportion
sketchbook
turpentine
watercolor
waterscape
calligraphy
composition
masterpiece
perspective
architecture
glassblowing
illustration
installation
stonecutting
crosshatching
"""
tiles = "hijklmnop" #可以隨意變更 title 變數內容，看看可以組出哪些單字

all_valid_words = ()       
start = 0                  
end = 0                    
found_words = ()           

for char in words:                                                 
    if char == "\n":                                               
        all_valid_words = all_valid_words + (words[start:end],)   
        start = end + 1                                           
        end = end +1                                               
    else:
        end = end + 1                                              

for word in all_valid_words:                                     
    tiles_left = tiles                                           
    for letter in word:                                          
        if letter not in tiles_left:                             
            break                                                
        else:
            index = tiles_left.find(letter)                      
            tiles_left = tiles_left[:index]+tiles_left[index+1:] 
    if len(word) == len(tiles)-len(tiles_left):                  
        found_words = found_words + (word,)                      
print(found_words)
```

# CH23
```
#analyze friends

def read_file(file):
    """
    file, a file object
    Starting from the first line, it reads every 2 lines
    and stores them in a tuple.
    Starting from the second line, it reads every 2 lines
    and stores them in a tuple.
    Returns a tuple of the two tuples.
    """
    first_every_2 = ()
    second_every_2 = ()
    line_count = 1
    for line in file:
        stripped_line = line.replace("\n", "")
        if line_count%2 == 1:
            first_every_2 += (stripped_line, )
        elif line_count%2 == 0:
            second_every_2 += (stripped_line, )
        line_count += 1
    return (first_every_2, second_every_2)
def sanitize(some_tuple):
    """
    phones, a tuple of strings
    Removes all spaces, dashes, and open/closed parentheses
    in each string
    Returns a tuple with cleaned up string elements
    """
    clean_string = ()
    for st in some_tuple:
        st = st.replace(" ", "")
        st = st.replace("-", "")
        st = st.replace("(", "")
        st = st.replace(")", "")
        clean_string += (st, )
    return clean_string
def analyze_friends(names, phones, all_areacodes, all_places):
    """
    names, a tuple of friend names
    phones, a tuple of phone numbers without special symbols
    all_areacodes, a tuple of strings for the area codes
    all_places, a tuple of strings for the US states
    Prints out how many friends you have and every unique
    state that is represented by their phone numbers.
    """

    def get_unique_area_codes():
        """
        Returns a tuple of all unique area codes in phones
        """
        area_codes = ()
        for ph in phones:
            if ph[0:3] not in area_codes:
                area_codes += (ph[0:3], )
        return area_codes
 
    def get_states(some_areacodes):
        """
        some_area_codes, a tuple of area codes
        Returns a tuple of the states associated with those area codes
        """
        states = ()
        for ac in some_areacodes:
            if ac not in all_areacodes:
                states += ("BAD AREACODE", )
            else:
                index = all_areacodes.index(ac)
                states += (all_places[index], )
        return states
 
    num_friends = len(names)
    unique_area_codes = get_unique_area_codes()
    unique_states = get_states(unique_area_codes)
    print("You have", num_friends, "friends!")
    print("They live in", unique_states)

friends_file = open('friends.txt')
(names, phones) = read_file(friends_file)
areacodes_file = open('map_areacodes_states.txt')
(areacodes, states) = read_file(areacodes_file)
clean_phones = sanitize(phones)
analyze_friends(names, clean_phones, areacodes, states)
friends_file.close()
areacodes_file.close()
```

# CH29
```
#docs comparer

def read_text(filename):
    """                                                   #A
    filename: string, name of file to read                #A
    returns: string, contains all file contents           #A
    """                                                   #A
    inFile = open(filename, 'r')                          #B
    line = inFile.read()                                  #C
    return line                                           #D

import string                                      #A

def find_words(text):
    """
    text: string
    returns: list of words from input text
    """
    text = text.replace("\n", " ")
    for char in string.punctuation:
        text = text.replace(char, "")

    words = text.split(" ") 
    return words 


def frequencies(words):
    """
    words: list of words
    returns: frequency dictionary for input words
    """
    freq_dict = {}          

    for word in words:                         
        if word in freq_dict:                   
            freq_dict[word] += 1               
        else:                                   
            freq_dict[word] = 1                
        return freq_dict                       


def calculate_similarity(dict1, dict2):
    """
    dict1: frequency dictionary for one text
    dict2: frequency dictionary for another text
    returns: float, representing how similar both texts are to each other
    """
    diff = 0
    total = 0

    for word in dict1.keys():                               
        if word in dict2.keys():                            
            diff += abs(dict1[word] - dict2[word])          
        else:                                               
            diff += dict1[word]                             

    for word in dict2.keys():                                
        if word not in dict1.keys():                         
            diff += dict2[word]                              

    total = sum(dict1.values()) + sum(dict2.values())        
    difference = diff / total                                
    similar = 1.0 - difference                               

    return round(similar, 2)                                 

text_1 = read_text("sonnet18.txt")
text_2 = read_text("sonnet19.txt")
words_1 = find_words(text_1)
words_2 = find_words(text_2)
freq_dict_1 = frequencies(words_1)
freq_dict_2 = frequencies(words_2) 
print(calculate_similarity(freq_dict_1, freq_dict_2))
```

# CH33
```
# card game

class Player:
    """ a player """
    def __init__(self, name):
        """ sets the name and an empty hand """
        self.hand = []                      
        self.name = name                    
    def get_name(self):                     
        """ Returns the name of the player """
        return self.name                    
    def add_card_to_hand(self, card):              
        """ card, a string 
            Adds valid card to the player's hand """
        if card != None:
            self.hand.append(card)                  
    def remove_card_from_hand(self, card):          
        """ card, a string 
            Remove card from the player's hand """
        self.hand.remove(card)                       
    def hand_size(self):                             
        """ Returns the number of cards in player's hand """
        return len(self.hand)                        


import random

class CardDeck:
    """ A deck of cards 2-9 of spades, hearts, diamons, clubs """
    def __init__(self):
        """ a deck of cards (strings e.g. "2C" for the 2 of clubs) 
            contains all cards possible """
        hearts = "2H,3H,4H,5H,6H,7H,8H,9H"
        diamonds = "2D,3D,4D,5D,6D,7D,8D,9D"
        spades = "2S,3S,4S,5S,6S,7S,8S,9S"
        clubs = "2C,3C,4C,5C,6C,7C,8C,9C"
        self.deck = hearts.split(',')+diamonds.split(',')        \
                    + spades.split(',')+clubs.split(',')
    def get_card(self):
        """ Returns one random card (string) and 
            returns None if there are no more cards """
        if len(self.deck) < 1:                    
            return None                           
        card = random.choice(self.deck)          
        self.deck.remove(card)                    
        return card                               
    def compare_cards(self, card1, card2):
        """ returns the larger card according to
            (1) the larger of the numbers or, if equal,
            (2) Spades > Hearts > Diamonds > Clubs """
        if card1[0] > card2[0]:                    
            return card1                           
        elif card1[0] < card2[0]:                  
            return card2                           
        elif card1[1] > card2[1]:                  
            return card1                           
        else:                                      
            return card2                           

name1 = input("What's your name? Player 1: ")
player1 = Player(name1)
name2 = input("What's your name? Player 2: ")
player2 = Player(name2)
deck = CardDeck()

while True:
    player1_card = deck.get_card()
    player2_card = deck.get_card()
    player1.add_card_to_hand(player1_card)
    player2.add_card_to_hand(player2_card)

    if player1_card == None or player2_card == None:          
        print("Game Over. No more cards in deck.")
        print(name1, " has ", player1.hand_size())
        print(name2, " has ", player2.hand_size())
        print("Who won?")
        if player1.hand_size() > player2.hand_size():          
            print(name2, " wins!")                             
        elif player1.hand_size() < player2.hand_size():        
            print(name1, " wins!")                             
        else:                                                  
            print("A Tie!")                                    
        break                                                  

    else:                                                      
        print(name1, ": ", player1_card)
        print(name2, ": ", player2_card)
        if deck.compare_cards(player1_card,player2_card)==player1_card:  
            player2.add_card_to_hand(player1_card)                       
            player1.remove_card_from_hand(player1_card)                  
        else:
            player1.add_card_to_hand(player2_card)
            player2.remove_card_from_hand(player2_card)
```

#CH36
```
# game of tag

import tkinter 
import random
class Player(object):
    def __init__(self, canvas, color):
        size = random.randint(1,100)
        x1 = random.randint(100,700)
        y1 = random.randint(100,700)
        x2 = x1+size
        y2 = y1+size
        self.color = color
        self.coords = [x1, y1, x2, y2]
        self.piece = canvas.create_rectangle(self.coords, tags=color)
        canvas.itemconfig(self.piece, fill=color)

    def move(self, direction):                           
        if direction == 'u':                             
            self.coords[1] -= 10                         
            self.coords[3] -= 10                         
            canvas.coords(self.piece, self.coords)       
        if direction == 'd':
            self.coords[1] += 10
            self.coords[3] += 10
            canvas.coords(self.piece, self.coords)
        if direction == 'l':
            self.coords[0] -= 10
            self.coords[2] -= 10
            canvas.coords(self.piece, self.coords)
        if direction == 'r':
            self.coords[0] += 10
            self.coords[2] += 10
            canvas.coords(self.piece, self.coords)
def handle_key(event):                    
    if event.char == 'w' :                
        player1.move("u")                 
    if event.char == 's' :
        player1.move("d")
    if event.char == 'a' :
        player1.move("l")
    if event.char == 'd' :
        player1.move("r")
    if event.char == 'i' :                 
        player2.move("u")                  
    if event.char == 'k' :
        player2.move("d")
    if event.char == 'j' :
        player2.move("l")
    if event.char == 'l' :
        player2.move("r")
    yellow_xy = canvas.bbox(1)                                          
    overlapping = canvas.find_overlapping(
                   yellow_xy[0],yellow_xy[1],yellow_xy[2],yellow_xy[3]) 
    if 2 in overlapping:                                                
        canvas.create_text(100,100,font=("Arial",20),text="Tag!")       

          
window = tkinter.Tk()
window.geometry("800x800")
window.title("Tag!")
canvas = tkinter.Canvas(window)
canvas.pack(expand=1, fill='both')
player1 = Player(canvas, "yellow")
player2 = Player(canvas, "blue")
canvas.bind_all('<Key>', handle_key)           
window.mainloop()
