# Grid
You can create a grid using pixels, percentages, or 'fr'.
## Create a grid container
.container{
	display:grid;
 }

'inline-grid' items will only take as much space as their content. New elements still start below

'grid' items will stretch the main axis of x
## A grid track is a space between 2 adjacent lines on the grid. 

Like the squares in a chess board.

Tracks can be defined using any unit. Can use 'fr' to create equal sizes and shrinks and grows according to available space

math for 'fr': 
available space = (total width/ height) - absolute size

available space/total fr

fr distributed =  (available space/total fr) * fr given
## Mixing flex and absolute sizes
'grid-template-columns: 500px 1fr 2fr

math: 

((total height/ width) - absolute size)/total fr

fr distributed = quotient * fr given


## repeat() notation
grid-template-columns: 1fr 1fr 1fr;

can be written as:

grid-template-columns: repeat(3, 1fr);

## Implicit and explicit grids
cross axis of the 'grid-template-columns/rows'

eg. rows of 'grid-template-columns' and vice-versa

grid-auto-row/width:
rows are controlled by height
columns are coontrols by width
## minmax()
args: min size, max size

if minmax(100px, auto)

max size will stretch according to the biggest item in the column/row for the column/row only

## Grid Lines



