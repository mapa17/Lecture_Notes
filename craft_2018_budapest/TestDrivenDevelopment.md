# Test Driven Development
by Llewellyn Falco, EPAM - Budapest 8 May 2018
https://twitter.com/llewellynfalco?lang=en
isidore@setgame.com

azeoke-szoke
y7QtTyyfY

# Writing scenarios
> Write the test like it happened yesterday; not tomorrow 

Meaning one has to be specific, and minimalistic

A scenario can be used to understand the system one tries to test.
Much better than rule based descriptions.

A scenario should be small but still contain some operation/move which, shows
the application of a rule.


# Test life cycle

Whiteboard -> English -> Code -> Results -> Whiteboard ....

**Whiteboard**: The idea is that you are *smarter* on the whiteboard than on pager or the editor. 
**English**: 
**Code**:
**Results**:

# Test first vs. Test after
The idea is that writing the test first will have the potential to safe time.




## Benefits of Unit Tests

1) Specifications (tries to understand what you want to build)
2) Feedback (do you actually )
3) Regression (does it continuously work? Verify operation)
4) Granularity (identify what is breaking a system; which version/feature breaks something)


## Performing vs Practice
Most performing skills/tasks are

Performing is not Practicing/Learning. Its a different mindset and setup.
One has to work on the practice routine.

Example: Typewriting (we perform for many years, but we dont practice/learn it)


# Example: Shopping recite

Einen leeren Einkaufs Zettel erstellen.
Fuelle Header und Footing hinzu
Erstelle einen Eintrag fuer: 1x Milch, 1 Liter um 1.0 Euro
Erstelle eine Rechnungs summe sammt Steuer Abgaben
    Dies enthaelt einen Bruto Steuer Betrag von 0.90 Euro + 10% 0.1
    Summe 1.0 Euro
Fuege Auftrags spezifische Information (Datum, Shop, Bearbeiter, ...) hinzu


```
// Create Receipt
// set shop name to be Grocery Store
// Set address to be 1146 budapest
// Set the tax number to  1143
// set tax percentage to 10%
// set milk price to 1
// set sugar price to 2 euros/kg
// buy 1 milk
// buy 1 kg sugar  
// checkout
// check total price = 3
// check receipt 


// Create Receipt
// set shop name to be Grocery Store
// Set address to be 1146 budapest
// Set the tax number to  1143
// set tax percentage to 10%
// set milk price to 1 per carton
// buy 1 milk
// set sugar price to 2.30 per kg
// buy 1 kg  sugar
// set discount 2 for 1
// set beer price per bottle 2.0
// buy 2 beer using discount (2for1)
// checkout
// check total price = 5.3
// check receipt 
```

## Example Mind Sweeper

```
Create a empty 5x6 board
Set a mine to 1/1
Set a mine to 2/2
check that field 2/1 == 2
check that field 1/1 == mine
check that game status == 'lost'
```

```
// generate minesweeper table 5x6
// place mine 1,0 
// place mine 2,1
// click on 2,0
// check 2,0 should display 2
// click 1,0
// check the game is lost
```

## Example 'Muele'
```
Create a empty 8x8 board
Set initial piece distribution (white 2/2, w 3/3, b 4/3, b 3/4)
Try setting b to 4/4
check status == valid
Try setting w to 0/4
check status == invalid
Try setting w to 1/2
check status == invalid
try w to 4/5
check status == valid
check cell 4/3 == w
```

## Example Battleship
```
Create empty playfield 6x7
Place submarine 1 on field 1/0 , 1/3
Place aircraft 2 on field 0/5 , 4/5
Bomb at 4/4
check hit == false
Bomb at 1/1
check hit == true
Bomb at 1/2
check hit == true
Bomb at 1/3
check hit == true
check ship 1 sank == true
```

```
//battle ship
//generate  Battleship table 5*7
// Place sub vertical on (1,1) 
// place aircraft  horizontal on (0,5)
//bomb (4,4)
// check msg “Miss”
// bomb (1,1)
// Check msg “Hit”
// bomb (1,2)
// Check msg “Hit”
// bomb (1,3)
// Check msg “Hit”
// Check sub is sink


// Place sub vertical on (1,1) 
board.place(Ship.SUB, Direction.Vertical, new Poin(1,1))

// Generate a sub
Sub sub = new Sub();
// Place it vertically at (1,1)
board.place(sub, Direction.Vertical, new Poin(1,1))

// place a sub vertically at 1,1 
board.place(new Sub(), Direction.Vertical, new Poin(1,1))
```

# Example: Checker board
```
Create empty 8x8 board
Set b (1, 2)
Set b (1, 4)
Set b (3, 2)
Set b (3, 6)
Set w (4, 3)
Set w turn
move w from (4, 3) to (2, 1)
eat (3, 2)
move w from (2, 1) to (0, 3)
eat (3, 2)
check if  piece_status at 0,3 is 'king'
move w from (0, 3) to (2, 1)
eat (3, 2)
move w from (4, 3) to (2, 1)
eat (3, 2)
```

# English to code
The translation of language to code is always depended on the translator and her knowledge. 
There are multiple possible realizations in code for the same english text.


Triangulation: Try to check a feature by multiple tests

# Tips on Test writing
Test things that you think will break; not things that will pass


# Mob programming
We have one activate navigator and one person at the keyboard + a bunch of people sitting in the second row. 
Every 5 minutes we are rotating one slot, so everyone goes through all positions.

## Observations
* Its difficult for programmers to be in the implementing position because they
have difficulties listening, and are used to implement their own thoughts.
* Quickly we get into a line of automatism that is driven first by the person defining the test (the mentor) and than by the IDE error messages. So I am missing the design/reflection step. It feels like the programmer is driven by the compiler, not the other way arround.


Mob dynamics: How big is the mob? Big enough to cover all expertise, but still everyone should contribute and learn. If one does not contribute or learn they might do something else.

In order to improve development time, try to bring down the costs for future mistakes.

by
* ??? ...  
* modular ... make things that are likely to break, easy to change
* Isolation ... my mistakes dont impact others

Once we had an insight on how the code should be, we change the code in a way that it appears that we new it all along.

## The 7 Stages of naming
missing -> nonsense -> honest -> honest&complete -> Does the right thing -> Intent -> Domain Abstraction

## Power of change
Power of slow change -> Its difficult to notice, but at the same tie you can change the whole world piece by piece wihtout hte approval of others.

## How much spend on learning vs working
Investing in learning if we can accumulate that learning benefits, will have
a huge benefit over time. So one can invest a lot of ones time in learning.
Spend **more** time learning at work

# Expressive Data
Rules
1) Objects print their data (mainly toString() )
2) Make the data easy to read (having a lot of data that one cannot read, is like having no data at all)


## Example: Bowling
Paul: [1: 9 (9,)] [2: 23 (7, s)] [3: 31 (4, 4)] [4: 49 (7, s)] [5: 57 (8, )] [6: 60 (3, )] [7: 68 (3, 5)] [8: 76 (8, )] [9: 83 (3, 4)] [10: 90 (7, ,)]

#Example of Legacy Code Testing
So we want to add testing to a existing code

1) The legacy code is the reference. All its behavior is valid! We want to first have a good description of its behavior. That is why we will add as much logging to it in order to trace its working.

2) Before doing refactoring of the code, use the test coverage until you created enough tests so that all the legacy code is executed.

3) Starting the refactoring, splitting up the code, using the code coverage as a guide on what to include where.

What you can do than is that you can start with the refactored code; which is split in smaller pieces, and can e