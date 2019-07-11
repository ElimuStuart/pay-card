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

#Challenge 2 of 4
Get The Bill
Write all Javascript strictly with ES6. This means use arrow functions instead of the function keyword. Declare variables and functions with const or let. Use const by default, and only use let if you are sure you need to re-assign values to the said variable. Use the Selector API instead of the getElementBy... or getElementsBy... APIs.

Install the JSON Viewer Chrome extension, open a new tab and go to this API endpoint. You will be making HTTP requests to the API, so spend some time looking at the structure of the response data.

Step 1
Create an appState variable and assign it an empty Object literal. This variable will hold data for the app.

Create a formatAsMoney function. It should take in an amount and a buyerCountry parameter. It will use these parameters to format the user's bill as a proper currency.

Create detectCardType, validateCardExpiryDate, and validateCardHolderName functions. Each should take in a parameter and use object de-structuring to obtain the target property of the parameter.

Create a uiCanInteract function. It will be called to setup the UI like adding event handlers to enable interactions with the app.

Create a displayCartTotal function. It should expect a parameter and should use object de-structuring to obtain results property of the parameter. This function will be called with the data from an API call and it will display the total payment bill.

Step 2
Create a fetchBill function. It should assign https://randomapi.com/api/006b08a801d82d0c9824dcfdfdfa3b3c to an api variable. It should then use the browser's fetch function to make a HTTP request to api. Using an arrow function in a .then call to the fetch function, return the response after converting it to JSON. Using another .then call to the first one, pass the JSON data to displayCartTotal. Make sure to handle errors that may occur, e.g by showing a warning message in the console.

Call the fetchBill function from inside startApp.

Step 3
In displayCartTotal, de-structure the first item in the results array into a data variable. Next, use object de-structuring to obtain the itemsInCart and buyerCountry properties of data.

Set appState.items to itemsInCart and set appState.country to buyerCountry

Use the Array .reduce function to calculate the total bill from itemsInCart Note that each item has a qty property indicating how many of that item the user bought. Assign the calculated bill to appState.bill

Go back to the formatAsMoney function. Use the .toLocaleString function on its amount and buyerCountry to format amount as a currency with the currency symbol of buyerCountry. The countries and their currency symbols are in the countries array you got in your starter code. If the buyerCountry is not in countries, then use United States and the country and format the currency accordingly.

back to where you left off in displayCartTotal, use the formatAsMoney function to set appState.billFormated to the formatted total bill. The already assigned appState.bill and appState.country should come be handy now!

Set the text content of the data-bill SPAN to the formatted bill set in appState.billFormated

Finally, call uiCanInteract to wrap up displayCartTotal

Run the app (click the play button) and see if the correct formatted bill is displayed in the UI. Next, we will allow input and interaction so that users can provide payment information.
