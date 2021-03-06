## Navigation Component 
[Jetpack Navigation Component in One Video](https://www.youtube.com/watch?v=IEO2X5OU3MY&t=1098s) by Mitch

[Get started with the Navigation component](https://developer.android.com/guide/navigation/navigation-getting-started) by Google Developers

__Android Jetpack: Introducing Navigation Component__ [by google](https://www.youtube.com/watch?time_continue=54&v=Y0Cs2MQxyIs&feature=emb_logo)

* Simplifed setup for common navigation patterns
* Handles backstack
* Automates fragmnet transactions
* Type safe arrguments passing
* Handles transition animations
* Simplified deep linking

### Three major parts working together in harmony
1) **Navigation graph:** An XML resource that contains all navigation-related information in one centralized location. This includes all of the individual content areas within your app, called destinations, as well as the possible paths that a user can take through your app.

2) **NavHost:** An empty container that displays destinations from your navigation graph. The Navigation component contains a default `NavHost` implementation, NavHostFragment, that displays fragment destinations.

3) **NavController:** An object that manages app navigation within a `NavHost`. The `NavController` orchestrates the swapping of destination content in the NavHost as users move throughout your app


#### Project Instructions

`List by mitch`
1) Creating a project with Kotlin and androidX
2) Navigation Component dependencies
3) Creating a navigation graph
3) NavHostFragment (Navigation Host Fragment)
4) Adding fragments to the navigation graph
5) NavController and navigating between fragments
6) Fragment transition animations using the navigation graph
7) Backstack management with PopUpTo and PopUpToInclusive attributes
8) Sending data as Arguments through a Bundle to a Fragment

----

`list by Me` :sunglasses: 
1. Add dependencies in build.gradle app 
    ```
    def nav_version = "2.1.0"
    implementation "androidx.navigation:navigation-fragment-ktx:$nav_version"
    implementation "androidx.navigation:navigation-ui-ktx:$nav_version"
    ```

2. Create Navigation Graph

    `res > new android resource file > (file name) (Res type Navigation)`
    
3. Create fragment - use fragment blank (class and layout)

4. Create fragment to main activity as host fragment 
    > What's view or activity is hosting your navigation graph
       
    ```
      <fragment
        android:id="@+id/nav_host_fragment"
        android:name="androidx.navigation.fragment.NavHostFragment"
        app:defaultNavHost="true"
        app:navGraph="@navigation/nav_graph" />
    ``` 
   
    - __The `android:name` attribute contains the class name of your NavHost implementation.__
   
    - __The `app:navGraph` attribute associates the NavHostFragment with a navigation graph. The navigation graph specifies all of the destinations in this NavHostFragment to which users can navigate.__
   
    - __The `app:defaultNavHost="true"` attribute ensures that your NavHostFragment intercepts the system Back button. Note that only one NavHost can be the default. If you have multiple hosts in the same layout (two-pane layouts, for example), be sure to specify only one default NavHost.__

5. Insert fragments to Graph as destination

__What is difference between the pop animation and non pop animation?__
pop refer to what happens when you navigate backward (back stack)
not pop is forward
