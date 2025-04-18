# Play what you hear training

**Goal: Learn to express what you hear in your head out to your instrument instantaneously by practicing playing common major and minor melodies in various keys.**

Structure practice around playing a random combo of a tune and key. Taking no more than 20 mins / session. Do less if you're not up to it though. The main focus is on matching the melody in your head - technique, tempo, all else are secondary.

The goal is to speak fluently over the range of your instrument. So start in different octaves. For guitar, try starting on different strings and different fingers (like 3rd and 4th string, fingers 1-4)

## Major melodies
Happy Birthday

Brahm's Lullaby "cradle song" (go to sleep, go to sleep, go to sleep little baby)

## Minor melodies
Autumn leaves melody (first 4 bars - the falling leaves, drift by the window, the autumn leaves, of red and gold)

Summertime

## Keys
According to https://www.hooktheory.com/cheat-sheet/key-popularity, these are the top 4 most common major and minor keys used across all the 30,000 songs in their database.

#### Keys for guitar

Concert pitch
C Major (16%)
D Major (12%)
G Major (12%)
A Major (10%)

A Minor (12%)
E Minor (12%)
C Minor (11%)
D Minor (11%)


#### Keys for Sax

Bb transposing key (move whole step above concert pitch, bc your instrument's C is a whole step below concert pitch)
D Major
E Major
A Major
B Major


B Minor
F# Minor
D Minor
E Minor

Once you're doing this consistently, try improvving.


## Anki card structure
Front
```
<h4>Key</h4><span id="key">&lt;key&gt;</span><h4>Melody</h4><span id="melody">&lt;melody&gt;</span><br><h4>
Starting Finger</h4><span id="starting_finger">&lt;starting_finger&gt;</span><br><h4>
Starting String</h4><span id="starting_string">&lt;starting_string&gt;<br><br><br><br>__<br><br><br>(to edit script, select deck, click "Browse" to browse cards in deck, select this card, click "Cards..." item above this card, and you'll see the script tag driving the selections here)</span>
```

Front Template details w/ script tag (reach by clicking "Cards..." option after selecting individual card in browse view)
```
{{Front}}

<script>
/*
 ____  _        _ __   __ __        ___  _____ 
|  _ \| |      / \\ \ / / \ \      / / \|_   _|
| |_) | |     / _ \\ V /   \ \ /\ / / _ \ | |  
|  __/| |___ / ___ \| |     \ V  V / ___ \| |  
|_|   |_____/_/   \_\_|      \_/\_/_/   \_\_|  
                                               
 _   _   _   _ _____    _    ____  
| | | | | | | | ____|  / \  |  _ \ 
| | | | | |_| |  _|   / _ \ | |_) |
| |_| | |  _  | |___ / ___ \|  _ < 
 \___/  |_| |_|_____/_/   \_\_| \_\

*/
function getRandomListItem(array) {
  if (array.length === 0) {
    return undefined; // Return undefined for empty arrays
  }
  const randomIndex = Math.floor(Math.random() * array.length);
  return array[randomIndex];
}

function keyIsMinor(keyStr) {
  if (keyStr.endsWith('min')) {
    return true
  }
}


// Choose random key and display it on the card
const keys = ['Cmaj', 'Dmaj', 'Gmaj', 'Amaj', 'Amin', 'Emin', 'Cmin', 'Dmin']

const chosenKey = getRandomListItem(keys)

const keyElement = document.getElementById("key");
if (keyElement) {
  keyElement.innerText = chosenKey;
}

// Choose random melody (based on the chosen key) and display it on the card
const major_melodies = ["Happy Birthday", "Brahm's Lullaby aka cradle song (go to sleep, go to sleep, go to sleep little baby)"]

const minor_melodies = ["Autumn Leaves  (the falling leaves, drift by the window, the autumn leaves, of red and gold)", "Summertime"]

const chosenMelody = keyIsMinor(chosenKey) ? getRandomListItem(minor_melodies): getRandomListItem(major_melodies)

const melodyElement = document.getElementById("melody");
if (melodyElement) {
  melodyElement.innerText = chosenMelody;
}


// Choose starting finger and display it on the card
const startingFingers = [1, 2, 3, 4]

const chosenFinger = getRandomListItem(startingFingers)

const startingFingerElement = document.getElementById("starting_finger");
if (startingFingerElement) {
  startingFingerElement.innerText = chosenFinger;
}

// Choose starting string and display it on the card
const startingStrings = [3, 4, 5]

const chosenString = getRandomListItem(startingStrings)

const startingStringElement = document.getElementById("starting_string");
if (startingStringElement) {
  startingStringElement.innerText = chosenString;
}

</script>
```

