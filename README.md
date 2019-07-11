# pay-card
Notes on my pay card application for ALC4


#PayCard 
##Challenge 1 of 4
Build & Style The UI
Step 1
Style the BODY element with a white background color

Create a DIV and give it a data-cart-info attribute. Inside the DIV, create a HEADING with mdc-typography--headline4" as its CSS class

The HEADING should have 2 SPAN elements. The First displays a shopping cart by setting its class to material-icons and setting its content to shopping_cart. The second SPAN has an attribute of data-bill and will be used to display the total figure the user is trying to pay on the app

After the data-cart-info DIV, create another DIV, give it an attribute of data-credit-card and set its class to mdc-card and mdc-card--outlined Within the data-credit-card DIV, create a new DIV with a class of mdc-card__primary-action These elements will be styled with the look and feel of an actual credit card!

Within the .mdc-card__primary-action DIV, create an IMAGE with an attribute of data-card-type and set its SRC to http://placehold.it/120x60.png?text=Card. This IMAGE will be used to display the credit card type, based on the series of numbers entered by the user

Right after the IMAGE, create a DIV with an attribute of data-cc-digits. It should contain four INPUT text fields, each with a size of 4 and a placeholder of ---- (4 dashes). These fields will be used to collect the credit numbers

Create a DIV with an attribute of data-cc-info as a sibling to the data-cc-digits DIV. This new DIV should have two INPUT text fields, one for entering the card holder's name while the other will be for the card's expiry date. The first field should have a size of 20 and a placeholder of Name Surname. The expiry date field should have a size of 6 and a placeholder of MM/YY - indicating the expiry date format.

We are now done with the structure of the credit card component. Let's make a button to allow the user make payment with the card details

Create a BUTTON as a sibling to the data-credit-card DIV. Set the BUTTON's class to mdc-button and give it a data-pay-btn attribute. It should have Pay & Checkout Now as its display text. After the user enters details of the card and clicks on this button, the app will strike-though the card numbers to indicate that they are in-valid.
Step 2
While we might have the right structure in place, the app visually tells a different story. Time to make the app look good and usable.

SPAN elements within the data-cart-info DIV should be displayed as inline block elements, and vertical-align set to middle. The .material-icons SPAN should have a 150 pixels size of font.

Give the data-credit-card DIV 435px width, 240px minimum height, 10px rounded borders, and a #5d6874 background colour.

Display the data-card-type IMAGE as a block element. Give it a 120px width and a 60px height.

The data-cc-digits DIV should have a 2em top margin.

INPUT elements in the data-cc-digits DIV should have a white color, 2em font size and line height, no border or background, and a right margin of 0.5em;

The data-cc-info DIV should have a 1em top margin.

INPUT elements in the data-cc-info DIV should have a white color, 1.2em font size, no border and no background. The second input should also have a right padding of 10px and be floated to the right of the viewport.

The data-pay-btn BUTTON should have a fixed position, 90% width, solid border of 1px and positioned 20px from the bottom of the viewport.

Your app should look functional at this point.
