<img align="right" src="Figures/icon.png?raw=true" alt="icon" width="20%" height="20%">
<br/>

# Pantree: Mobile Cooking Assistant Application

<br/>
<br/>
<br/>

This report documents the research, design and development that went into the Android application Pantree. A cooking assistant app with the aim of providing a recipe sharing platform, with pantry tracking and ingredient-based recipe searching. 

Using these features, I hope to tackle two problems, food waste by using up the left-over ingredients that would otherwise go to waste, and the decrease of home cooking over the last 30 years. Home cooking is a vital component to a healthy balanced diet, in a world where fast food and processed foods are an easily accessible commodity, Pantree attempts to simplify the process of cooking and its organisational aspect to therefore motivate people to start cooking at home.

The Application is built within Android Studio and uses Firebase technologies, this allows users to sign in on any phone and instantly be able to use the application seamlessly thank to Firebase’s Realtime Database, as well as maintain a secure application thanks to Firebase Authentication.

## Application Wireframe
<p align="center">
<img src="Figures/wireframe.png?raw=true" alt="Wireframe" width="80%" height="80%">
</p>


## Sign in Activity
This activities purpose is simply to allow the user to sign in, it is the first activity the user interacts with when first opening the application or once signed out. Access to the Sign-Up Activity (Figure 8) is provided via the clickable TextView at the bottom of the screen. If the user is signed in, they will automatically skip this page when opening the app, and land in the Main Application Activity (Figure 9). Error signs are displayed if the email is invalid and if the password is too short, as adhering to the Firebase authentication requirements. 

<p align="center">
<img src="Figures/sign_in.png?raw=true" alt="Sign In Activity" width="40%" height="40%">
</p>


## Sign up Activity
This Activity is Equally simple and after being accessed through the sign in Activity allows the user to create an account. Both the email and the Password are checked if they adhere to the Firebase Authentication requirements, and then the user is signed in and are then send to the Main Application Activity (see figure 9). They can also return to the Sign in Activity (Figure 7) via the clickable TextView at the bottom of the screen.

<p align="center">
<img src="Figures/sign_up.png?raw=true" alt="Sign Up Activity" width="40%" height="40%">
</p>


## Application Activity

This is where all the application functionality is presented to the user, the Activity is deceptively simple, and is composed of only a FrameLayout, and a BottomNavigationBar. The navigation bar can be used to access all Fragments that make up the application, the FrameLayout is then replaced with the corresponding Fragment. If the user is not authenticated, they are sent back to the sign in screen, where they will be required to sign in.

<p align="center">
  <img src="Figures/app_activity.png?raw=true" alt="Application Activity" width="40%" height="40%">
</p>


### User Profile Fragment
This is the first Fragment a user sees displayed in the FrameLayout within the Main Application Activity. Here the user can add/change their profile picture, view their name, and sign out of the application. This Fragment has substantial potential for future implementations.

<p align="center">
  <img src="Figures/up_fragment.png?raw=true" alt="User Profile Fragment" width="40%" height="40%">
</p>

### Pantry Fragment
Within this fragment all the ingredient tracking functionality can be accessed, a user can view all the ingredients currently in their pantry, as well as add ingredients via search when the button on the top right is pressed. The Ingredients can be removed by clicking on the minus symbol on the right of the ingredient list item. 

<p align="center">
  <img src="Figures/pantry_fragment.png?raw=true" alt="Pantry Fragment" width="40%" height="40%">
</p>

### Recipe Search Fragment
This Fragment has similarities in design to the Pantry Fragment (Figure 11), but differs in functionality, the list view is populated by the Recipes Stored in the Firebase Realtime Database. The user may now search via Title of the Recipe, as well as searching by the ingredients available in their Pantry by clicking the switch. Recipes can be accessed by clicking them in the ListView, which opens the Recipe View Fragment (Figure 13), which is populated with the corresponding information. By pressing the add button on the top right the user can access the Add Recipe Fragment .

<p align="center">
  <img src="Figures/rs_fragment.png?raw=true" alt="Recipe Search Fragment" width="40%" height="40%">
</p>

### Recipe View Fragment
A simple Fragment with little intractability and is only used to view the recipes and the information associated with it, this can be accessed only via the Recipe Search Fragment (see figure 12). This displays information such as a recipe image, the recipe contributor, the time for completion, ingredients required and amounts, and the preparation steps. This Fragment is instantiated on clicking a recipe item within the ListView and destroyed when the back button on the top left is clicked.

<p align="center">
  <img src="Figures/rv_fragment.png?raw=true" alt="Recipe View Fragment" width="40%" height="40%">
</p>

### Recipe Add Fragment
This Fragment can also only be accessed through the Recipe Search Fragment (see Figure 12). Here a user can fill in the information to add their own recipe to database, all the fields are required when uploading a recipe. An image can be added by clicking on the camera icon, the title and time can be add through the EditText’s, ingredients can be searched and are then added on click, Steps are added by pressed the plus button which will create an EditText which can then be filled with the necessary information. 

<p align="center">
  <img src="Figures/ra_fragment.png?raw=true" alt="Recipe Add Fragment" width="40%" height="40%">
</p>

## Firebase Authentication
Provides the backend services, for authenticating users, with integration with other federated identity providers that can be used as sign in options, such as Google, Facebook etc. The user data is securely stored and allows me to keep the application secure by checking the user’s identity and only allowing the correct user access to their information.

## Firebase Realtime Database
The Fire base Realtime Database is a cloud-hosted database, which keeps the data synchronised between all the connected clients. This was vital, as the user data as well as the recipe data is all stored within the database regular consistent updates should be instant and synchronised for other users, e.g. adding recipes, adding/removing ingredients, changing the user profile image.
In Figure 14 we can see the structure of the database and the data it contains, represented in an Entity Relationship Diagram.

<p align="center">
  <img src="Figures/Database.png?raw=true" alt="Database Entity Relationship Diagram" width="80%" height="80%">
</p>

# CREDITS

Vegetables free icon made by Freepik from www.flaticon.com
Fish free icon made by Freepik from www.flaticon.com
Oil bottle free icon made by Freepik from www.flaticon.com
Meat free icon made by Freepik from www.flaticon.com
Salt free icon made by Freepik from www.flaticon.com
Round bread free icon made by Freepik from www.flaticon.com
Wardrobe free icon made by Freepik from www.flaticon.com
Apple free icon made by Smashicons from www.flaticon.com
Carrot free icon made by Smashicons from www.flaticon.com
Milk free icon made by Smashicons from www.flaticon.com

## Libraries Used
- Glide by Sam Judd
- Circilar ImageView by Lopez Mikhael
