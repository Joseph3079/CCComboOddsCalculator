# Creating Elements
- 1-8 will create a "Cast X spell", with the 8 non-GFD spells. If you create an RA spell, it will also add a success and backfire below it. If you want the success/backfire on a different spell, you can select the spell and press either 'S' or 'B' to add both.
- 9 creates a GFD element. After selecting it, 1-8 will add that spell next to the GFD, and 9 will add the "Other" element that is used for spells that aren't there. This will also add a "Resolve" element. If you don't want all of the resolves that were created, you can delete the extra by selecting it and pressing backspace. If you want the spells to be listed on the other side, press 'F' to flip the GFD. You can also click a spell and press 'S' or 'B' for success/backfire.
- 'B' or 'S' will create a "Buy To" or "Sell To" element. To change the number on it, click the element and type the number you want. This also works for the "Start At" element.
- 'H' will create a "Halloween" element, and 'N' will create a "No Season" element. Both have the same function. 'E' will create an "Easter" element.
- 'G' or 'W' will create a "Click GC" or "Click WC" element. After selecting it, you can restrict it to a specific buff with the following keys:
  -A for blAb on a GC, or B for Blab on a WC.
  -B for BS
  -C for CF or Clot
  -D for storm Drop
  -E for EF
  -F for Frenzy or cursed Finger
  -L for Lucky
  -R for Ruin
  -S for Storm
  -W for sWeet on a GC, or S for Sweet on a WC.
  -O for all other effects that aren't listed.
- 'L' will create a "Lump" element, and 'C' will create a "Caramel lump" element.
- 'I' will create an "Invoke Module" element, and 'M' will create a "Module" element.
- 'Shift+2' will let you take a different route depending on whether you have a FtHoF GC onscreen or not. 'Shift+3' will let you take a different route depending on whether you have a ST backfire or not. 'Shift+8' will let you take a different route depending on whether you have a successful DI or not. 'Shift+F' will let you take a different route depending on whether you have a fortune GC onscreen or not.
- For most elements, selecting them and pressing 'M' will create a "Magic" element. Then, you can select that and type a number to take a different route based on your current magic. This also supports '>' or '<', to combine all routes less than or greater than a certain magic amount.

# Moving Elements
- Clicking and dragging the empty space between elements will let you move the screen around. The top right corner of the screen will show the current coordinates of the center of the screen, and a bit lower you can see the coordinates of your mouse cursor. Clicking the top coordinates will reset you to (0,0).
- Scrolling up or down will zoom the screen in or out. The top right corner of the screen will show your current zoom level. Clicking that will reset the zoom level to 100%.
- Dragging most elements will allow you to move them. If there are elements attached to it, they will also be moved.
- To connect elements, select the first element, then hold 'Control' and click the second element. This will only work if the first element is above the second element.
- If a GFD RA refunds, and you want to do the same thing again, you can connect a lower element with a higher element. The line connecting them will be red to indicate it is a loop.
- Once elements are connected, there will be some more information indicated on each element:
  - The top left corner shows the ID of the element, which starts at 0 and increases with each element created.
  - The top right corner shows how much magic you have at that point in the route. If there are multiple states with different magic amounts in the same element, it may show a range of magic amounts.
  - The bottom right corner shows the probability of reaching that element.
- Selecting an element and pressing 'Backspace' will remove that element.
- Holding 'Shift' when dragging will let you select multiple elements at once. Then, you can move one element and it will move all elements within the box.

# The Sidebar
- Under the "Settings" tab, you can export the current flowchart to a string, or import a string. There are some sample files in this repository that you can load if you want.
- The Settings tab will also let you set your current Cookies Baked All Time (CBAT), as well as your wizard tower level and average building special multiplier.
- Under the "Module Order" tab, you can change the order that the program will calculate the different modules. IMPORTANT: If one module calls another module inside itself, you need the first module to be listed above the second on this list.
- Also in this tab, you can edit the name, color, and hotkey for each of the modules. Once a hotkey is set for the module, selecting a "Invoke Module" element and pressing that hotkey will change that element to the given name and color.
- Under the "Element States" tab, you can select an element, and it will list the differences between each of the states within that element. 
- Under the "GC Click Order" tab, you can determine the order that the program will click golden cookies. The program will go down the list and perform the first action that meets the requirements you set, then after it successfully clicks a cookie it resets to the top of the list again. If you select "Click High BS Scry" or "Click High CF Scry", you should click the "+" button, and choose the minimum chance of this effect that you would be willing to click here. If you want to apply a different restriction, for example only clicking a nat if you don't have DF, you can also click the plus and change the dropdown to say "DF"=0. Each action also assumes you have the required cookie onscreen, and if you don't it will go to the next row.

# Calculations
- Under the "Overall Chances" tab, you can click the "Calculate Probabilities" button, which will take all the states in every element that doesn't have an attached element, spawn a natural cookie (or 2), and it will start clicking golden cookies according to the rules set in the "GC Click Order" tab. It will then output the chance of getting at least that combo or better. It will also output the average cookies and average prestige gained from this route, based on the CBAT and average BS mult values in "Settings" and a click speed that gives an average of 1 million seconds of raw CpS (CCCEM score of 1e6). If you go back to the "Settings" tab and change these values, it will recompute the average cookies and prestige.
- Once this calculation is performed, there will be a "Calculate All Node Values" button. When this is clicked, the program will then work through the flowchart backwards, and it will determine how likely each combo is at every point on the flowchart. Once this is done, it will also show the average prestige for every element on the flowchart in the bottom left corner of it. If you then click on the "Element States" tab, it will also show the average prestige for every state in that element.
- After both of these calculations are performed, there will also be a "Compare Routes" button added to the "Element States" tab. If you change the route that is attached to a given node, you can then select the lowest element that wasn't changed in that route and click that button. It will then calculate the average prestige of each state in that element again, using the new route instead, and it will list both the old and new prestige next to each other. Once this is done, the CBAT input will also show up, so you can move the slider around and see how having a different amount of cookies will change which route is correct. If the new route is better, you can click the "Overwrite Data" button, which will carry the new prestige values up the rest of the flowchart.
