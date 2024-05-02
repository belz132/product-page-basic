# product-page-basic

This is a simple Vue project with Atomic Design approach.

Components

1. Atoms:
    * Button (Button.vue): a simple component re-usable in this project.

2. Molecules:
    * ProductItem (ProductItem.vue): represents a row in the product list table.
    * ShoppingCartItem (ShoppingCartItem.vue): represents a row in the shopping cart table.

3. Organisms:
    * ProductList (ProductList.vue): made up of multiple ProductItem molecules to make a complete product table.
    * ShoppingCart (ShoppingCart.vue): similar to ProductList, this is an organism that consists of multiple ShoppingCartItem to make a complete shopping cart table.

4. Templates:
    * MainTemplate (MainTemplate.vue): a layout that defines how the ProductList and ShoppingCart organisms are positioned on the page, essentially structuring the main page layout. Could be used for other pages next as well.

5. Pages:
    * HomePage (HomePage.vue): an instance of the MainTemplate with actual products and cart items populated.

Hierarchy

1. HomePage.vue
   * MainTemplate.vue
   * ProductList.vue
        - ProductItem.vue
            - Button.vue
   * ShoppingCart.vue
        - ShoppingCartItem.vue
            - Button.vue

Features/ Functionalities

* When "Add to cart" button is pressed, the product will be added into the shopping cart and the "Stock" quantity in Product list will be decrease accordingly. 
* Shopping Cart is empty in default. 
* There are buttons in Shopping Cart to increase and decrease the amount of product that is added. 
* When "Delete" button in Shopping Cart is pressed, product will be deleted from Shopping Cart and "Stock" quantity is restored accordingly.
* The "Total" row in Shopping Cart section is to display the total price of added products.
* When "Checkout" button is pressed, there will be an Alert message displaying the total price of products that customer have to pay.
* Stock quantities can't go below zero.
* Can't add more items to the cart than are available in stock.
* No checkout if total price is 0

