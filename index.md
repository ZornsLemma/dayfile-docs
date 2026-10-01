[<img src="assets/badge-f-droid.png" alt="Get it on F-Droid" height="80">](https://f-droid.org/packages/app.zornslemma.dayfile)
&nbsp;&nbsp;
[<img src="assets/badge-obtainium.png" alt="Get it on Obtainium" height="80">](https://apps.obtainium.imranr.dev/redirect?r=obtainium://add/https://github.com/ZornsLemma/dayfile/releases)

# Overview

This Android app helps you make notes about your daily life. It works entirely offline, so your notes are private and it's your responsibility to back them up so you don't lose them if something happens to your phone.

The idea is that making a note should be as low-friction as possible. You open the app, you type, you close or background the app. The note is automatically attached to the current date. You can optionally have pre-defined categories to help to split up the day's notes but that's it. Entries are free text with no attempt at imposing a structure beyond the categories. There are no reminders or alarms. There is no formal support for any time tracking more precise than "a day".

There's nothing wrong with more structured note-taking, and there's no shortage of apps that will help you do it. The emphasis here is on being able to make a quick note with minimal ceremony. The less effort it is to make the note, the more likely it is that you'll invest the time to make it.

This is almost embarrassingly primitive, which is the whole point. You can use a text editor to make notes, but you have to make sure you have the right file open, you have to make sure you enter the date correctly, etc. You can use a calendar app but it isn't easy to review the notes after, such apps are naturally organised around making entries for arbitrary future dates and you probably don't want your random "what I did today" notes getting mixed in with your formal appointments. You can use a journalling app, but that might be too heavyweight or prone to inspirational reminders if you just want to just down that you went for a 30 minute walk.

The uses are, as they say, limited only by your imagination. Try it and see, feel free to pair it with a more structure app to get the best of both worlds if that works for you.

# Getting started

On first run the app creates some plausible demonstration categories. You are of course free to edit these - use the overflow menu at the top right of the main screen to go to the category editor. The switches on this screen enable and disable categories. Disabling a category is pragmatically very similar to deleting it, but if you really want to fully delete a category you can disable it and then choose the delete option from the category's triple dot menu (which is greyed out for enabled categories to avoid accidents).

The basic use of the app should otherwise be fairly straightforward and you will likely figure it out for yourself. Note that you must use the Settings->Backup option to perform backups at suitable intervals, otherwise you risk losing your notes. The most unusual aspect of the app is the way the history works - this is effectively a very safe if unconventional form of undo. Read on for more details on the various features.

# Main screen

The app's main screen shows the log entries for a specific date, today by default: TODO: EXPERIMENT WITH SCALE OF THESE FULL-SCREEN SHOTS

<img src="assets/main-screen.png" alt="Main screen showing sample categories and entries" style="max-width: 50%; height: auto;">

You can use the left and right arrows next to the current date to move to the previous or next day respectively. You can also tap on the date to bring up a date selector.

The padlock icon - here shown as "unlocked" - indicates whether you are allowed to edit the displayed entries. The current date defaults to being unlocked, other dates default to being locked. The idea here is to make it hard for you to accidentally edit an entry for any day other than today, e.g. if you browsed back a few days and then put the app into the background before returning. Tapping the padlock icon will toggle it between locked and unlocked - you always have the choice to edit old entries (or future dates, for that matter), the app just doesn't want you to do it without realising. There is no persistent storage of whether a date is locked or not - as soon as you move from one date to another, any manual changes to the lock status are discarded.

Tapping on a category's text entry will allow you to edit it in the normal way, provided the date is not locked.

The triple dot icon at the top right allows you to access the app's menu in the usual way. This allows the category, history and settings screens to be accessed.

If you leave the app briefly (e.g. to check something in another app), it will remember the selected date and protection status when you return. After 10 minutes, re-opening the app will return you to the main screen for today no matter where you were when you left it.

# TODO CATEGORY SCREEN(S)

# TODO HISTORY AKA UNDO

# TODO SETTINGS (INCLUDING BACKUP/RESTORE)

# TODO DAY STARTS AT (MAYBE UNDER SETTINGS)

# Historical note

The original version of this app, called Daily Log, was the first Android app I wrote. In 2012 I got my first Android phone, a second-hand HTC Desire Z *with a physical keyboard*. (Those were the days, my friend!) I couldn't find an app that would let me make notes the way I wanted, so I wrote it. This was probably also my first attempt at writing Java too. I bought an electronic copy of Mark Murphy's ["The Busy Coder's Guide to Android Development"](https://commonsware.com/Android/) and took frequent advantage of his generous offer to get the latest versions for free if you submitted even the most basic corrections (typos, grammar).

At the time I thought it would be cool to have an app on the Play Store, probably just for free with no ads. Development stalled when I tried to add a category editor, particularly one which supported dragging categories around, and as the app worked just fine for me with the hard-coded categories I was able to use it myself just fine, but a public release never happened because it was never finished. I used to back up the database periodically with adb, and eventually (around TODO) I fought with a fresh install of whatever the latest Android development environment was to hack in a really crude database export so I could do backups while away from my PC without needing adb.

I used the incomplete app literally daily from June 2012 to January 2025. When the app was written I was using Android 2.x and the "menu" button was alive and well. Over the years, I upgraded phones but there was usually some practical workaround for no longer having a "menu" button. Eventually I upgraded to a phone where I couldn't seem to get this to work properly, even with third party apps, and I switched to the best available alternative I could find on the Play Store. (I'm grateful to the author, but since I wasn't using the app for what it was designed for - it had a journalling flavour to it - and I therefore found it somewhat annoying in a way that isn't really their fault, I won't name it here.) I used that from January 2025 and had the idea of writing my own modern version of my own app at the back of my mind, if only I could find the time and energy.

An urge to experiment with LLM-assisted coding after creating [my first modern Android app](https://zornslemma.github.io/my-price-log-docs/) by hand made me start on this app when I otherwise perhaps didn't feel I had the time or inclination. TODO REFDERENCE AI STUFF IN GITHUB README OR PERHAPS WRITE IT HERE??? It was developed under the name Daily Log, even though I had checked and seen that the name was definitely already taken. I can hardly complain after sitting on my original version all that time, can I? I struggled to come up with a new name and did some brainstorming with ChatGPT, eventually ending up with Dayfile. It is a shame not to have retained the original name, but Dayfile is growing on me.

I started using this new app myself daily from September 2026.

The new app contains no code from the original, although the main screen layout is obviously influenced by it. The original app had "Save" and "Cancel" buttons at the bottom of the main screen which caused me intermittent grief over the years as I would fat-finger "Cancel" by mistake, but resuscitating my Android build environment, getting back into the code and confronting all the evolutions in Android tooling and libraries over the year were just too much of a hurdle to stop me resuming development when the app did mostly work fine in practice.

I was and still am surprised at how hard it was to find an app like this one. I feel sure there must be dozens which I have somehow overlooked, but whenever I made a diligent effort to look, I struggled to find anything which worked quite how I wanted. It feels like this app (except for the complexity of making the categories user-definable) is so close to "My First Android App" that I can't believe no one has done it before. Maybe it's just too boring to ever get properly polished up and released. Maybe I'm just too picky and every implementation I find just doesn't work quite the right way for me to feel comfortable with. Anyway, here we are.

# Feedback

Please raise bug reports and suggestions for enhancements as issues at the [app's GitHub repository](https://github.com/ZornsLemma/dayfile/issues).

This app is open source and is freely available under the MIT license on GitHub.
