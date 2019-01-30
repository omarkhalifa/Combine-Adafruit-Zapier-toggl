# Combine-Adafruit-Zapier-toggl
Manual by Omar Khalifa

By following the instructions in this manual is it possible to make a fully functional setup between Adafruit, Zapier and Toggl. You can also create a system where you can see if someone is home or not.

*Make sure that you have a working internet connection and a up-to-date webbrowser.* 

# Setup a Adafruit IO Account

*Adafruit is an Internet of Things platform where you can make online sensor data visible in a so called "feed"* 

You have to make an account if you want to make use of Adafruit IO. So the first step is to make an account with an dashboard.
1. Go to https://io.adafruit.com/ , click on "Get Started for free" and make an account.
2. Go to the left sidebar and click "Dashboards", create a new dashboard and give your dashboard a name. *If you don't see "Dashboard" in the left sidebar, make sure that you used the previous links. Make sure that you are not on https://www.adafruit.com/ .*
3. It's time to create a Adafruit IO Key. Look for the "Adafruit IO Keybutton" (AIO Key). Receive your key by clicking on the key button. *If you can't find the key button then it's also possible to go to "settings" in the menu on the left and find the AIO key there.*
4. Your AdafruitIO Key should appear on your screen. Make sure you don't forget the AIO key because we need it later.
5. Its time to make a feed. You can find "feeds" in the menu on the left. Click on the "Actions" box and a drop down will appear. Click "create a new feed"
6. Make a new feed and call it "toggl". *You can give your feed a different name but it's easier for now to call it "toggle".*

At this point you have a decent Adafruit setup. We will come back later to receive values from the feed.
This is the end of the Adafruit setup. If you want to learn more about adafruit and learn more than the basics you can find info at https://learn.adafruit.com/series/adafruit-io-basics.

# Zapier
*Users can use Zapier to make triggers and send the value to their personal Adafruit IO feed*

1. We start by creating an account. Go to https://zapier.com/ and click on the "Sign up" button in the top right.
2. Start by making a zap. Click on the "Make a Zap!" Button to create a zap. *Make sure that you are logged in!*
3. It's time to make new triggers. Typ "Toggle" in the search bar and look for the power button icon in the list.
4. When you click on Toggle there will appear a screen with 3 options: New project, New Time Entry, New Time Entry Started. We will use "New Time Entry Started". We use this one so every time you log in on your Toggl account this trigger get started again.
5. To link Zapier and Toggl we have to connect the acounts. Click "Connect an Account".
6. Now we need your person API Key from Toggl. Go to https://www.toggl.com/login/ and log in to your Toggl account or make one if you don't have one already.
7. Now click on your account name in the bottom left and click on "profile settings"
8. Scroll down and copy your personal API token. Paste the Toggl API token in Zapier. 
9. To make sure it works fine you can press on the test button to test the connection between Zapier and Toggl. Click continue to (duh....) continue.
10. Zapier wants to test is but we will skip it to save time. Click on "Skip this step" and after that you have to click on "continue with default settings".
11. Zapier is not very usefull jet! To make it usefull we have to add an action to our zap. This action wil be executed whenever the trigger gets triggered. In our case is that when we start a new time in our Toggl. Click on "+ add a step" and after that "Action/Search".
12. Find Adafruit IO in the list and add it. Select "Send Value to Feed" and click on continue.
13. At this point you have to connect your Adafruit IO account with Zapier to make a connection. Click on "Connect an Account" and a new API window will appear.
14. At this point you have to use the AIO key from Adafruit IO that found earlier in the manual (Adafruit Setup, Step 4)
15. Now you see Adafruit IO in the list. Click on test or continue right away.
16. It's time to add some values. Those values will be send to our Adafruit IO feed at the moment that a trigger gets triggerd. For value we fill in "100" and for the feed we will fill in "toggle". *If you named your feed differently you have to fill your own chosen name in.*
17.  Now it's time to test our Zap. Click on "Send Test To Adafruit IO". Open your feed in https://io.adafruit.com .
18. At this point you will see the given value, in our case is that 100. *if you don't see a value you have to check if the feed matches with the feed you named in zap. If those are the same you have to check all the steps we went through.*
19. At last you click Finish and name your Zap. Give your zap a useful name so you know what the zap.

_This was the hardest part in this Manual. We made sure that Adafruit, Zapier and Toggl are connected so we are almost finished._
_It's possible to give another value to our feed without removing the 100 value.If you want to learn about that keep following this manual._

# Make a new zap
1. Follow all the Zapier steps till step 4. We now choose "New Trigger Entry". Don't fill in the optional text fields and continue.
2. Continue all the Zapier steps until step 16. now you will add 0 to our value. The feed is still called Toggl. Continue till you finished the proces.
3. When someone stops using Toggl a trigger will be send to Adafruit and the value in the feed will be 0.

Congrats! You made a system that will show if someone is using Zappier or not. This could be useful to see if you want to make a system to see if someone is home or not. These values (100 & 0) can be used in a code. 100 could be the value of someone being home and 0 is the value for an empty house.
