## Lab Instructions

**Estimated time needed:** 110 minutes

## Introduction

In this final project, you will create a shopping cart application for an online plant shop which offers a variety of house plants.

The *Paradise Nursery* shopping cart features will include:
- A Landing page with a button linking to the product listing page
- A navigation bar with links to the landing, product listing, and shopping cart pages
- A card for each plant that showcases the different plants along with their images, name, description, cost and an **Add to cart** button.
- A minimum of two sections describing the plants in that section. For example, \&quot;Aromatic Plants\&quot; and \&quot;Medicinal Plants\&quot;.
- A cart page which displays the products in the cart.
- The cart should have a card for each type of plant in the cart. Each card should have the thumbnail, the unit cost, the cost for all of the plants of that type and buttons to increase and decrease the quantity along with **Delete** button.
- A **Continue Shopping** and **Checkout** buttons

You will implement the knowledge and skills you gained from working on the practice project to handle dynamic functionalities, like the show cart quantity in the icon on the navbar and updating the cost of all of the items in the cart when the user updates the number of items.

## Project Submission
To submit your application for grading, you will need to deploy it. You will need to provide the URL as part of the peer review project. You can use GitHub Pages to host. You can find the instructions from the *Setting Up the GitHub Environment* lab earlier in this module.

You may choose to host it elsewhere and provide that link instead. Just make sure your peers can access the application easily using the URL you provide.

When you deploy, be sure to make a note of the application&#x27;s URL.


## Learning objectives
After completing this lab, you will be able to:

- React Components: Create functional React components using component composition and nesting.
- State Management with Hooks: Implement React Hooks, specifically the useState and useEffect hooks. You will manage component-level state using hooks to control the visibility of elements.
- Redux Integration: Integrate Redux within an application using Redux concepts like actions, reducers, and the store.
- Rendering Dynamic Data: Dynamically render data fetched from an array of objects into the UI. You will map over arrays to generate lists of components.
- Handling Events and Conditional Rendering: Handle user events such as button selection and trigger corresponding actions.

## Prerequisites

- Basic knowledge GitHub and your own GitHub account
- Understanding of React function components, props, hooks and React Redux Toolkit
- Web browser with a console (such as Chrome DevTools or Firefox Console)

::page{title&#x3D;&quot;Important notice about this lab environment&quot;}

Skills Network Cloud IDE (based on Theia and Docker) is an open-source IDE (Integrated Development Environment) that provides an environment for hands-on labs in course and project-related labs.

Please be aware that sessions for this lab environment are not persistent. Every time you connect to this lab, a new environment is created for you. You will lose data if you exit the environment without saving to GitHub or another external source. Plan to complete these labs in a single session to avoid losing your data.

::page{title&#x3D;&quot;Setting up your environment in GitHub&quot;}

1. Fork the repository

You need to fork the GitHub repository for React your application. The GitHub repository with the skeleton code for this project is here:
- https://github.com/ibm-developer-skills-network/e-plantShopping.git

- After following the link above, click on the fork button.

![fork the repository](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/zZMZUZ0Q4zl7koVz2OhbPQ/e-plantshoprepository.png &quot;fork the repository&quot;)

2. This repository contains the basic layout of the React application for this project.

3. You will use this forked repository to push your latest code to keep a record of the work you do. Periodically save all your files. Your files must be saved to perform git commands.

4. Perform &#x60;git add&#x60;, &#x60;git commit&#x60;, and &#x60;git push&#x60; commands to update changes from your application folder to your GitHub repository for proper code management.

5. As part of the peer review project, you will need to deploy your app with GitHub pages so your peers can review the UI. You can review [these instructions](https://cf-courses-data.static.labs.skills.network/IBMSkillsNetwork-CD0210EN-Coursera/labs/v2/m1/Setting_up_the_environment.md.html) for assistance with GitHub and for deployment instructions of react application.


If you\&#x27;ve logged out and want to resume work on the project, clone the forked repository where you previously pushed the code. After cloning, you can use &#x60;git push origin&#x60; without the need to execute &#x60;git remote add...&#x60; to push your changes directly.

::page{title&#x3D;&quot;Create your React project&quot;}

1. If you do not have an open terminal, select the \&quot;Terminal\&quot; tab at the top-right of the window, and then select \&quot;New Terminal\&quot;. The screenshot below shows you where to locate these options on your screen.

	![SN screenshot](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CD0210EN-Coursera/images/terminal.png)

2. Now clone the forked repository using given command by replacing &#x60;&lt;forked-repo-link&gt;&#x60; with your own repository link.

	&#x60;&#x60;&#x60;javascript
	git clone &lt;forked-repo-link&gt;
	&#x60;&#x60;&#x60;

3. Make sure your application name matches your project.

&lt;!--4. You can either find your own images for the project or use these suggested images from *[Pixabay](https://pixabay.com &quot;Pixabay&quot;)* and *[Unsplash](https://unsplash.com &quot;Unsplash&quot;)*, sites that supplies royalty-free images.

[License information for Pixabay images](https://pixabay.com/service/license-summary/ &quot;License information for Pixabay images&quot;)

[License information for Unsplash images](https://unsplash.com/license &quot;License information for Unsplash images&quot;)

Use the &#x60;wget&#x60; commands below to retrieve the images from Pixabay and Unsplash. Make sure you &#x60;cd&#x60; to the correct folder so the files download to the appropriate directory.

- Snake plant:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2021/01/22/06/04/snake-plant-5939187_1280.jpg
	&#x60;&#x60;&#x60;
- Spider plant:
	&#x60;&#x60;&#x60;bash
	curl https://pixabay.com/images/download/chlorophytum-3530413_640.jpg -o chlorophytum-3530413_640.jpg
	&#x60;&#x60;&#x60;
- Peace lily:

	&#x60;&#x60;&#x60;bash
	curl https://pixabay.com/images/download/peace-lilies-4269365_640.jpg -o peace-lilies-4269365_640.jpg
	&#x60;&#x60;&#x60;

- Boston fern:
	&#x60;&#x60;&#x60;bash
	curl https://pixabay.com/images/download/boston-fern-5114414_640.jpg -o boston-fern-5114414_640.jpg
	&#x60;&#x60;&#x60;
- Rubber plant:
	&#x60;&#x60;&#x60;bash
	curl https://pixabay.com/images/download/flower-4850729_640.jpg -o flower-4850729_640.jpg
	&#x60;&#x60;&#x60;
- Aloe vera:
	&#x60;&#x60;&#x60;bash
	curl https://pixabay.com/images/download/leaf-3283175_640.jpg -o leaf-3283175_640.jpg
	&#x60;&#x60;&#x60;
- Lavendar:
	&#x60;&#x60;&#x60;bash
	wget https://images.unsplash.com/photo-1589296986498-28cd9406425d
	&#x60;&#x60;&#x60;
- Jasmine:
	&#x60;&#x60;&#x60;bash
	wget https://images.unsplash.com/photo-1592729645009-b96d1e63d14b
	&#x60;&#x60;&#x60;
- Rosemary:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2019/10/11/07/12/rosemary-4541241_1280.jpg
	&#x60;&#x60;&#x60;
- Mint:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2016/01/07/18/16/mint-1126282_1280.jpg
	&#x60;&#x60;&#x60;
- Lemon balm:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2019/09/16/07/41/balm-4480134_1280.jpg
	&#x60;&#x60;&#x60;
- Marigold:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2022/02/22/05/45/marigold-7028063_1280.jpg
	&#x60;&#x60;&#x60;
- Basil:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2015/09/09/17/38/basil-932079_1280.jpg
	&#x60;&#x60;&#x60;
- Catnip:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2015/07/02/21/55/cat-829681_1280.jpg
	&#x60;&#x60;&#x60;
- Echinacea:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2014/12/05/03/53/echinacea-557477_1280.jpg
	&#x60;&#x60;&#x60;
- Peppermint
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2017/07/12/12/23peppermint-2496773_1280.jpg
	&#x60;&#x60;&#x60;
- Chamomile:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2016/08/19/19/48/flowers-1606041_1280.jpg
	&#x60;&#x60;&#x60;
- Calendula:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2019/07/15/18/28/flowers-4340127_1280.jpg
	&#x60;&#x60;&#x60;
- ZZ plant:
	&#x60;&#x60;&#x60;bash
	wget https://images.unsplash.com/photo-1632207691143-643e2a9a9361
	&#x60;&#x60;&#x60;
- Pothos:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2018/11/15/10/32/plants-3816945_1280.jpg
	&#x60;&#x60;&#x60;
- Cast iron plant:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2017/02/16/18/04/cast-iron-plant-2072008_1280.jpg
	&#x60;&#x60;&#x60;

- Succulents:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2016/11/21/16/05/cacti-1846147_1280.jpg
	&#x60;&#x60;&#x60;

- Aglaonema:
	&#x60;&#x60;&#x60;bash
	wget https://cdn.pixabay.com/photo/2014/10/10/04/27/aglaonema-482915_1280.jpg
	&#x60;&#x60;&#x60;
--&gt;
4. After cloning the repository you will see the folder structure like given screenshot.

	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/6XlKMR0N98tIY6ClKaa3Dw/plant-structure.png)

5. Write the command to enter the application folder in the terminal. The command will set your terminal path to run the React application in the &#x60;&lt;forked-folder-name&gt;&#x60; folder.
	&#x60;&#x60;&#x60;bash
	cd e-plantShopping
	&#x60;&#x60;&#x60;
6. To make sure that the code you have cloned is working correctly, you need to follow the given steps:
	- Write the following command in the terminal and select Enter to install all the necessary packages to execute the application.

		&#x60;&#x60;&#x60;bash
		npm install
		&#x60;&#x60;&#x60;
	- Then execute the following command to run the application, providing you with port number 4173.

		&#x60;&#x60;&#x60;bash
		npm run preview
		&#x60;&#x60;&#x60;

7. To view your React application, click the Skills Network icon on the left panel (refer to number 1). This action will open the **Skills Network Toolbox**. Next, click **Launch Application** (refer to number 2). Enter port number **4173** in **Application Port** (refer to number 3) and click ![arrow pointing outside of a box](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CD0210EN-Coursera/images/6.png).

	![Launch Your Application](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/7Zp_Csloj8ZcONEZiA4jbw/launch-app.jpg)

8. The output will be according to given screenshot with background picture.

	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/rdrEbBnT64JcAfhcKQHQUg/landing-plant.png)



9. Now click on &#x60;Get Started&#x60; button and then you will see the given layout according to screenshot which includes navbar with green background color.
	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/4YbW3vHz8RyXrcf07wbyZg/navbar-plant.png)

&lt;!--10. Create a basic directory structure by creating the following components and files within the &#x60;src&#x60; folder.
	- &#x60;CartItem.jsx&#x60; component
	- &#x60;CreatSlice.jsx&#x60; component--&gt;

10. The navbar contains three links:
	- &#x60;Paradise Nursey&#x60;- This will take you back to the landing page of the application.
	- &#x60;Plants&#x60;- This will navigate you to the page where information related to page will be visible.
	- &#x60;Cart icon&#x60;- This will navigate you to the cart items section.

11. When you will click on &#x60;cart icon&#x60; output will be visible as per given screenshot.

	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/1RpDJP4KErhPyBQNBthkvw/cartItem.png)

Complete the required tasks explained on the pages that follow. Your peers will assess you using a rubric provided based on these tasks.

&lt;!--::page{title&#x3D;&quot;GitHub Pages&quot;}

enter info about needing the link to their github page here for the peer review--&gt;

::page{title&#x3D;&quot;Task 1: ProductList component Layout&quot;}


The product page will allow your users to shop for the different plants you sell. Each plant will display on its own \&quot;card\&quot; with its related data stored in the plant object. You will store the plant objects in an array. Follow these steps for the array and plant objects.

1. Display the Plant Array
- Navigate to the &#x60;ProductList.jsx&#x60; component and you will see an array named &#x60;plantsArray&#x60; with the plants details.
- Each plant object contains the categories, properties name, image URL, description, and cost.

2. Display Plant Details within &#x60;div&#x60; tag with class name **product-grid**.
- Utilize array methods to map over the plant array.
&gt; Hint: use the &#x60;map()&#x60; method to iterate array.
 
- Render each plant\&#x27;s details on the page, including name, image, description, and cost.

3. Display an **Add to Cart** button for each plant.
 
	
&lt;details&gt;
	&lt;summary&gt;Display plants and add to cart button solution&lt;/summary&gt;

&#x60;&#x60;&#x60;javascript
	{plantsArray.map((category, index) &#x3D;&gt; (
	&lt;div key&#x3D;{index}&gt;
		&lt;h1&gt;&lt;div&gt;{category.category}&lt;/div&gt;&lt;/h1&gt;
		&lt;div className&#x3D;&quot;product-list&quot;&gt;
			{category.plants.map((plant, plantIndex) &#x3D;&gt; (
			&lt;div className&#x3D;&quot;product-card&quot; key&#x3D;{plantIndex}&gt;
				&lt;img className&#x3D;&quot;product-image&quot; src&#x3D;{plant.image} alt&#x3D;{plant.name} /&gt;
				&lt;div className&#x3D;&quot;product-title&quot;&gt;{plant.name}&lt;/div&gt;
				{/*Similarly like the above plant.name show other details like description and cost*/}
				&lt;button  className&#x3D;&quot;product-button&quot; onClick&#x3D;{() &#x3D;&gt; handleAddToCart(plant)}&gt;Add to Cart&lt;/button&gt;
			&lt;/div&gt;
			))}
		&lt;/div&gt;
	&lt;/div&gt;
	))}
&#x60;&#x60;&#x60;

&lt;/details&gt;

- Include above code within class name **product-grid**.

4. Create one variable named &#x60;addedToCart&#x60; for state management using the **useState** hook to track which products are added to the cart.
 
&lt;details&gt;
&lt;summary&gt;Sample solution for useState hook&lt;/summary&gt;

&#x60;&#x60;&#x60;js
const [addedToCart, setAddedToCart] &#x3D; useState({});
&#x60;&#x60;&#x60;
&lt;/details&gt;
 
5. Add to Cart Functionality
- Create the &#x60;handleAddToCart&#x60; function to implement the functionality for adding a plant to the cart when the user selects the **Add to Cart** button. This function should take one parameter that contains the information of the selected plant. This information should then be dispatched to the addItem inside the function component &#x60;CartSlice&#x60;.
 
- Additionally, reflect the product has been added to the cart. Update the &#x60;setAddedToCart&#x60; state to by setting the product name as a key and its value to true.

&lt;details&gt;
&lt;summary&gt;Sample solution for add to cart&lt;/summary&gt;

&#x60;&#x60;&#x60;js
const handleAddToCart &#x3D; (product) &#x3D;&gt; {
  dispatch(addItem(product));
  setAddedToCart((prevState) &#x3D;&gt; ({
     ...prevState,
     [product.name]: true, // Set the product name as key and value as true to indicate it&#x27;s added to cart
   }));
};
&#x60;&#x60;&#x60;
	
&lt;/details&gt;
 
&gt;Note: Make sure that you &#x60;import&#x60; the &#x60;addItem&#x60; reducer from &#x60;CartSlice.jsx&#x60;
 
6. The &#x60;handleAddToCart()&#x60; function &lt;!-- not sure what you mean by &quot;this function&quot;? Which function?--&gt; will carry the details of that plant which user want to add in the cart. And the plant details to the cart at a global level using &#x60;CartSlice.jsx&#x60;.
 
7. Make sure that you save these changes by pushing your code to your GitHub repository.

::page{title&#x3D;&quot;Task 2: State management using Redux&quot;}

1. You have the basic layout in the &#x60;CartSlice.jsx&#x60; file.
	
2. Define Reducer Functions
- Now implement the reducer property of the slice for adding, removing, and updating the number of items in the cart.
- These reducer functions will be called when user wants to add or remove the quantity of plants within the &#x60;cartItems&#x60; component.
 
- The &#x60;addItem()&#x60; reducer adds a new plant item to the &#x60;items&#x60; array which you  initialized in the previous step. 
- The &#x60;addItem()&#x60; function should get called when the user selects an **Add to cart** on the plant listing page. Subsequently, the &#x60;handleAddToCart()&#x60; gets called which has the plant type as a parameter.
- The &#x60;handleAddToCart()&#x60; function will then dispatch the plant details to the &#x60;addItem()&#x60; reducer function in &#x60;CartSlice.jsx&#x60;.

&lt;details&gt;
&lt;summary&gt;addItem() reducer sample solution&lt;/summary&gt;

&#x60;&#x60;&#x60;js
addItem: (state, action) &#x3D;&gt; {
  const { name, image, cost } &#x3D; action.payload;
  const existingItem &#x3D; state.items.find(item &#x3D;&gt; item.name &#x3D;&#x3D;&#x3D; name);
  if (existingItem) {
    existingItem.quantity++;
  } else {
    state.items.push({ name, image, cost, quantity: 1 });
  }
},
&#x60;&#x60;&#x60;
&lt;/details&gt;

- Now you need to complete code for the &#x60;removeItem()&#x60; and &#x60;updateQuantity()&#x60; reducers.

- &#x60;removeItem()&#x60;: This reducer removes an item from the cart based on its name and gets called when the user wants to remove products from the cart.

&lt;details&gt;
&lt;summary&gt;removeItem() reducer sample solution&lt;/summary&gt;

&#x60;&#x60;&#x60;js
state.items &#x3D; state.items.filter(item &#x3D;&gt; item.name !&#x3D;&#x3D; action.payload);
&#x60;&#x60;&#x60;
&lt;/details&gt;
	
- &#x60;updateQuantity()&#x60;: To create this function, start by extracting the item\&#x27;s name and amount from the &#x60;action.payload&#x60;. Then, look for the item in the &#x60;state.items&#x60; array that matches the extracted name. If the item is found, update its quantity to the new amount provided in the payload. This ensures the item&#x27;s quantity is correctly updated based on the action.

&lt;details&gt;
&lt;summary&gt;updateQuantity() reducer sample solution&lt;/summary&gt;

&#x60;&#x60;&#x60;javascript
const { name, quantity } &#x3D; action.payload;
const itemToUpdate &#x3D; state.items.find(item &#x3D;&gt; item.name &#x3D;&#x3D;&#x3D; name);
if (itemToUpdate) {
  itemToUpdate.quantity &#x3D; quantity;
}
&#x60;&#x60;&#x60;
&lt;/details&gt;

3. Handle Actions
- Export the action creators, &#x60;addItem()&#x60; to use in &#x60;ProductList.jsx&#x60;, &#x60;removeItem()&#x60;, and &#x60;updateQuantity()&#x60;, to use in the &#x60;CartItem.jsx&#x60;.
- Also export the reducer as the default to use in &#x60;store.js&#x60;.

4. Make sure you save these changes by pushing your code to your GitHub repository.

::page{title&#x3D;&quot;Task 3: CartItems component&quot;}

Next, you will complete the development of the &#x60;CartItem.jsx&#x60;component which displays the items held in the shopping cart. This component has a number of functionalities that you find in a typical shopping cart:
- Calculate the total for all items in the cart.
- Calculate the subtotal for each plant type in the cart.
- Continue shopping
- Increment and decrement the number of each plant type in the cart
- Remove (delete) a plant type from the cart altogether.

You will dispatch the increment, decrement, and update quantity details from a Redux file.

When you are done, the cart page should look similar to the following:
	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/p9Yu4z-YQsn0X0hbecMv9A/8.png)

1. Cost of all items in cart
- In the &#x60;calculateTotalAmount()&#x60; you need a function to calculate the cost of all of the items in the cart. There are a number of ways you can calculate this.

&lt;details&gt;
&lt;summary&gt;Sample algorithm description for calculating the total cost&lt;/summary&gt;

You can iterate through the item array, find the quantity of each item using the &lt;code&gt;item.quantity&lt;/code&gt; property and multiply by the cost of that plant type using the &lt;code&gt;item.cost&lt;/code&gt; property.
&lt;/details&gt;


2. Continue shopping
- Users should be able to return to the plant listing page to continue shopping while on the shopping cart page. So, in the &#x60;handleContinueShopping()&#x60; function call the function passed from the parent component.

3. Checkout
- In this project, you are not required to provide the &#x60;handleCheckoutShopping()&#x60; function, but you may wish to for further exploration and practice. For now, just add in the following code to alert the user this function will get added at a later date.
&#x60;&#x60;&#x60;js
const handleCheckoutShopping &#x3D; (e) &#x3D;&gt; {
  alert(&#x27;Functionality to be added for future reference&#x27;);
};
&#x60;&#x60;&#x60;

4. Increment and decrement
- For the &#x60;handleIncrement()&#x60; and &#x60;handleDecrement()&#x60; functions, you need to dispatch the &#x60;updateQuantity()&#x60; reducer in the &#x60;CartSlice.jsx&#x60; file. In the function argument, either add one to the &#x60;item.quantity&#x60; value or subtract one, respectively.

- Also, for the &#x60;handleDecrement()&#x60; you will need an if-else to handle the case if the number of items gets decremented to 0. In that case, you will need to dispatch the removeItem() method.

5. Remove plant from the cart
- For the &#x60;handleRemove()&#x60; function you need to dispatch the &#x60;removeItem()&#x60; method.

6. Item subtotal
- Calculate the total cost of the number of plants of a particular type with the &#x60;calculateTotalCost()&#x60; function by multiplying the unit cost of a plant by the number of that type of plant in the cart.

7. Event Handling
- Implement event handlers for incrementing and decrementing the quantity of the item in the cart. 
- When the user changes the number of a plant type in the cart, the following data needs updated: the cart icon, the number of that plant type, the subtotal, and the total cost.
- Implement an event handler to remove the item from the cart.
	
8. Total Quantity Counter
- Maintain a variable dedicated to counting the total number of items added to the cart.
- Update this variable as the user adds or removes plants from the cart.
- Display the total quantity on the cart icon in the navbar.
	
	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/8wJF2h4C8D2Q3Lh3pV0E6w/7.png)
	
9. Make sure that you save these changes by pushing your code to your GitHub repository.

::page{title&#x3D;&quot;Task 4: Integrate Redux functionality in your components&quot;}

1. ProductList Component
	- Initialize the cart items state in the Redux store.
	- Dispatch the &#x60;addItem&#x60; action to add items to the cart.
	- Retrieve the quantity of all the items in the cart from the Redux store.
	
2. CartItem Component
	- Dispatch the &#x60;updateQuantity&#x60; action to update the quantity of the cart item.
	- Dispatch the &#x60;addItem&#x60; action to add the item from the cart.
	- Dispatch the &#x60;removeItem&#x60; action to remove the item from the cart.
	
*Note: Make sure that you save these changes by pushing your code to your GitHub repository*

::page{title&#x3D;&quot;Task 5: Import details to store.js&quot;}

1. Importing Necessary Functions and Files:

	- The &#x60;configureStore()&#x60; function from the &#x60;@reduxjs/toolkit&#x60; package is imported to set up the Redux store.
	- The &#x60;cartReducer&#x60; from the &#x60;CartSlice.jsx&#x60; file which is imported, manages the state slice related to the shopping cart.

&#x60;&#x60;&#x60;js
import { configureStore } from &#x27;@reduxjs/toolkit&#x27;;
import cartReducer from &#x27;./CartSlice&#x27;;
&#x60;&#x60;&#x60;

2. Configuring the Store:

	- The &#x60;configureStore()&#x60; function is used to setup the Redux store.
	- Inside the configuration object passed to &#x60;configureStore()&#x60;, the &#x60;reducer&#x60; key specifies the reducer functions. In this case, the &#x60;cartReducer&#x60; is assigned to manage the &#x60;cart&#x60; slice of the state.
&#x60;&#x60;&#x60;js
const store &#x3D; configureStore({
    reducer: {
        cart: cartReducer,
    },
});
&#x60;&#x60;&#x60;


3. Exporting the Store:

	- The configured Redux store is exported using &#x60;export default store;&#x60;, so it can be used throughout the application to manage state.

&#x60;&#x60;&#x60;js
export default store;
&#x60;&#x60;&#x60;


*Note: 
	- This code is pre-configured in the repository and ready for use.
	- Make sure that you save these changes by pushing your code to your GitHub repository*

::page{title&#x3D;&quot;Task 6:  Set up the global store&quot;}

1. Navigate to the &#x60;main.jsx&#x60; file in the &#x60;src&#x60; folder.

2. The &#x60;Provider&#x60; component from the &#x60;react-redux&#x60; library is already imported. This component enables all components in the application to access the Redux store.
&#x60;&#x60;&#x60;js
import { Provider } from &#x27;react-redux&#x27;;
&#x60;&#x60;&#x60;

3. The Redux store is imported from the &#x60;store.js&#x60; file. This store holds the application\&#x27;s state, using the reducer defined in the &#x60;CartSlice.jsx&#x60; file.
&#x60;&#x60;&#x60;js
import store from &#x27;./store.js&#x27;;
&#x60;&#x60;&#x60;

4. The &#x60;App&#x60; component is wrapped with the &#x60;Provider&#x60; component, with the Redux store passed as a prop. This allows all components in the app to access and interact with the global state managed by Redux.


&#x60;&#x60;&#x60;js
&lt;Provider store&#x3D;{store}&gt;
  &lt;App /&gt;
&lt;/Provider&gt;
&#x60;&#x60;&#x60;
*Note:
	- This code is pre-configured in the repository and ready for use.
	- Make sure that you save these changes by pushing your code to your GitHub repository*

::page{title&#x3D;&quot;Project Completion&quot;}

### Congratulations!

You completed this project! Great work.

If you have not already done so, deploy your application. You can deploy it using GitHub Pages or your own hosting site. Make a note of the URL to the application, you will need that to submit your project for peer review.

Directions to deploy your application using GitHub pages are found in the [last step of this lab](https://author-ide.skills.network/render?token&#x3D;eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTVNraWxsc05ldHdvcmstQ0QwMjEwRU4tQ291cnNlcmEvbGFicy92Mi9tMS9TZXR0aW5nX3VwX3RoZV9lbnZpcm9ubWVudC5tZCIsInRvb2xfdHlwZSI6InRoZWlhIiwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3MTg4ODM0ODF9._81RcysQR9zG1jidLQplZqjtYFuLziQlTSJtBbAEeCo &quot;last step of this lab&quot;), *Setting up the GitHub Environment*, earlier in this course.

Deployment of your react application is important as your peer will review your work based on this.

### Summary

- You created function React components, composed, and nested them. 

- You implemented React Hooks, specifically the &#x60;useState&#x60; and &#x60;useEffect&#x60; hooks to manage component-level states.

-  You integrated Redux within your React application and applied Redux concepts like actions, reducers, and the store.

- You dynamically rendered data fetched from an array of objects onto the UI. You mapped over arrays to generate lists of components.

- You handled user events such as button selection and triggered corresponding actions to add and remove items in the cart.

#### Author
Richa Arora

Copyright IBM Corporation. All rights reserved. 
