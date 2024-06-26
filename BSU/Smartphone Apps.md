
# activity - an ouput window? 

Comes with 2 files:

layout file - design of the app. written in xml file


logic file - logic of the app.  written in kotlin file
	like on button click, do **something**.

# Kotlin

We have to predefine our variables, which is why we put them on top of the `class`, before any function implementation.

```kotlin
class MainActivity : AppCompatActivity() {  
  
private lateinit var n1: EditText  
private lateinit var n2: EditText  
private lateinit var sum: TextView  
  
override fun onCreate(savedInstanceState: Bundle?) {  
super.onCreate(savedInstanceState)  
setContentView(R.layout.activity_main)  
  
n1 = findViewById(R.id.n1)  
n2 = findViewById(R.id.n2)  
sum = findViewById(R.id.sum)  
}  
  
fun addValues(view: View) {  
val n1 = n1.text.toString().toInt()  
val n2 = n2.text.toString().toInt()  
  
val result = n1 + n2  
sum.text = "Sum $result"  
}  

}
```

Syntax:

`fun` represents **function**.

`private` represents the **scope** of the variable.
`lateinit` means the variable is to be **assigned later**.
`EditText`, `TextView` are data types.


`var` and `val` are keywords used to create **immutable**, and **mutable** variable. 
`$` is used as the equivalent of an `f-string` in Python. Also known as **variable** or **string**
**interpolation**.

## Creating an array (list)

`arrayOf()`. The arguments in `arrayOf` are the list elements themselves.

Model:
	\[List View] <--> \[Adapter] <--> \[Data Source]

List View refers to the layout file

Adapter is a class something something

Data Source is the array itself
# Assessment 1 - Reddit

Evaluate the following:

**Architecture and Functionality** - Describe design and flow of the app. Bring up limitations. Discuss functionality of the app.

**Aesthetics** - Color scheme and how it affects the objective of the app. Is the layout well balanced? Are icons and images attractive and approppriately sized?

**Fitness for purpose** - Discuss if the app accomplishes its goal. Are there flaws?


## Intro 

Reddit is a social news site and a mobile application, which allows for users to post their content-- could be any allowed content-- on any community and their content is ranked by popularity, which is determined by a system of community votes. Basically, posts with high votes are showed at the top of the app when users would first go into the app. 

Reddit separates its contents by its communities. These communities are also called as "subreddits". Subreddits can be about pets, memes, video games in general, a specific video game, news, a public figure, and so on. If you have an interest, chances are, there's probably a subreddit for it, too.


## Architecture and Functionality

The app is designed to be easy to navigate, even with just one hand. When you open the app, you are immediately in the `Home` page of Reddit. In the home page, this is where posts from different subreddits will show.

You'll notice at the top, an option box currently named `Home`. Clicking on this will show different tabs in the home page. You can also swipe in the home page to move to these tabs. This shows that Reddit is functionality designed to be used as easily as possible.

The app's features are easy to see, this is because the main features are shown in the first page of the app. Clicking on the top-left option shows subreddits you've joined, and clicking on the top-right shows all the options in your account.

For every feature of the app, there tends to be an icon accompanied as well. This helps users to faster recognize similar features from different apps, leading to an easier user-experience.

Overall Reddit's design is about on-par with most modern apps, they tend to share similar designs so that users are able to map-on what they know from a different app to the current one. 

And it contains all the relevant functions for the app to function as it originally did on its web-counterpart.

## Aesthetics

The app looks very minimal, primarily utilizing white-and-black color scheme. There is a dark mode feature to invert the color scheme. From what I've seen of the app, the `join` button is the only button that's different, being colored in blue.

The aesthetic borrows from the original Reddit site. Which is also primarily in white and black. 

I agree with this design choice because it fosters familiarity between the 2 platforms. What you know from the website will translate well into the app. 

The layout focuses on the main content of Reddit, which is showcasing posts from subreddits. "Navigational buttons" are located at the top and bottom bar. This is so that the user is faced with the main contents of the app, only putting the navigation features at the corners.

The icons, typically come with text that describe what that feature is, sometimes they do not; like the search bar on the top-right has no text that says "Search" or the top-left that says "Communities". This is to prevent cluttering and only using the text + icon combination on features that are more specific on what they do and the ones that are not as intuitive. And the icons themselves generally encapsulate what the feature represents or what it does.


## Fitness for Purpose 

The mobile app of Reddit is designed so that users of the site can have access to Reddit on their phones without primarily accessing it through the browser. The reason for why this app exists is the same reason why YouTube, Twitter, and so on, have mobile apps; which is to target the mobile demographics that may not have accessed the app through mobile internet browsing.

That is to say that the goal of the Reddit app is to bring its platform to the mobile industry. This means that all features of the Reddit website will be implemented in its mobile counterpart. And so far, it mirrors it very well.

~~--**just show how similar the app is to the website**.~~

There is one problem I have with the app, and that is when you search for something, but you want to refine it, but you don't go through with it, pressing the back icon will lead to the `home` page instead of the initial query results. There's no going back to where you were in your inital query, so you'd have to scroll all the way to get there again.

This is different in the website counterpart, where you can just click any non-link on the site to cancel your refined query, and you're still where you left off.


## Conclusion 

Overall, Reddit mobile sufficiently mirrors its website counterpart, which is the point of many apps that were once website-only. It has its own feature like this `communities` tab because I've never seen that in the website, so this is probably done as a mobile-exlusive feature, but it could also just be a new feature of Reddit. And I only found 1 thing I didn't like, so that's good. I would give Reddit a 99/10. 

The joke is that it's common in Reddit communities to have the same post become popular, so the second 9 was a "repost". That's about it.




# [Google Slides](https://docs.google.com/presentation/d/e/2PACX-1vTEfCZxZ876L1JpxVJsdM1I_g-36UPeQLwQPaWcep6KiS7TU9ChauVN3WEb_PWPJpAPHLuWCgeJz8_j/pub?start=false&loop=false&delayms=3000#slide=id.p)

## Android OS

Open-source and Linux-based. Led by Google.

## FAAF Framework

Functionality - how it works, crashes, instructions, buttons, gestures and touches, optimal

Architecture - structure, pages, hierarchy, follow guidelines

Aesthetics - color scheme, high-quality images, appropriate animations, white spacing, graphics support

Fitness - accomplish goals, missing features or bloated, easy to use


## Layouts 

Linear Layout - Single-line layout of widgets, either only(??) horizontally or vertically. 

Relative Layout - Widget position is based on the parent container.

Constraint Layout - Flexible, can do whatever

Other - Grid, Frame, Table -- Layouts

[Constraint Layout](https://docs.google.com/presentation/d/e/2PACX-1vTEfCZxZ876L1JpxVJsdM1I_g-36UPeQLwQPaWcep6KiS7TU9ChauVN3WEb_PWPJpAPHLuWCgeJz8_j/pub?start=false&loop=false&delayms=3000#slide=id.g2bc9effbdf6_0_154)



## Images

Stored in res/drawable directory.

Can be png, jpeg, gif.

ImageView used.

How to add Images:

- [ ] Copy-paste image in `drawable` folder. Image **must** be lowercase and or underscore only.
- [ ] Drag and drop `ImageView` to the GUI.


## Toast Messages

Small message to provide information or feedback.

Syntax: `Toast.makeText( this, "Welcome", Toast.LENGTH_SHORT ).show()

`LENGTH_SHORT` - 2 secs
`LENGTH_LONG` - 3.5 secs


## ArrayOf()

The data structure of the Kotlin to the GUI looks like this:

ListView <-> Adapter <-> Data Source

### Definition

ListView - GUI in the layout .xml

Adapter - The middleman 

Data Source - Hard-coded values

### Mechanics


Adapter creates a `View` for each item in the data source. It then inserts the items into a `ListView`. Can customize how the items are to be displayed. All done when instantiating an object of the `Adapter` class.










## Change Icon

- [ ] In `App/res/drawable`, create a `New` `Image asset`. 

## Create new icons

In `drawable`, create a new `Image Asset`. And in the `Icon Type`, change it to `Action Bar and Tab Icons`.
## Adding mp4

in `App/res/`,  
- [ ] create a new folder called `raw`, 
- [ ] drag and drop the mp4 to `raw`.
- [ ] create a variable holding `MediaPlayer` data type.
- [ ] assign `MediaPlayer.create(this, mp4 )` to said variable

To go to the start of the mp4, `mediaPlayer.seekTo(milliseconds)`, milliseconds is self-inputted.


## When adding Images,

Make the `scaleType` to `cropCenter` or something 


# Assessment 2 - NaN Calculator 

## Critical Summary

### Conceptual Goals

Since we were tasked with creating a NaN calculator app (i.e an app that outputs something based on an input, but must not be a number), the first thing that came to my mind was the thought of color combination. In most programming languages, colors are represented either by their hexadecimal form or by a function of rgb, taking 3 arguments: red, green and blue.

And how this works is that red, green, and blue are an 8-bit unsigned integer data (a number that ranges: 0~255), and based on this number, determines the amount of intensity or brightness of that color. This gives the illusion of seeing any color in the visible spectrum, all because the pixels are so close together that they look like a single point in the human eye.

And my app is supposed to make use of this concept, as there are many ways to mix-and-match primary colors, without necessarily outputting a number.

### Aesthetic Choices

The app is designed to be simple to use. At the very top is the name of the app, called "ColorMix", the word *Mix* is colored in differing intensities corresponding to red, green, and blue. I added the color on the latter word so the app doesn't just display a bland text referring to the title of the app.

In the middle, there are 3 input fields, each corresponding to the red, green, and blue inputs. They are accompanied by an icon to show the intensity of the corresponding color, as well as having a "random" button to generate any number in that input field from 0~255. These widgets are in the middle so that they are most likely to be focused on by the user, and that they serve one of the primary functions of the app, which is to take inputs.

At the bottom of the app is the resulting color, which has a bigger icon than the last 3, and is accompanied by a hexadecimal label corresponding to the color of the resulting color. By default, the hexadecimal value will be #000000, which corresponds to the color black. In a hierarchical view, it makes sense to put the output at the bottom when the inputs are at the top, and so these widgets are here.

At the very bottom of the app is the "help" icon, showing steps on how to use the app. I put this at the bottom-left of the app as I don't think looking at the tutorial of the app is one of the primary functions, so it's just placed somewhere at the edge of the screen to be found by the user when they are looking for more information about the app.

### Technical Description

The main concept of the app (the idea of color mixing) comes from the way we represent colors in many programming languages; specifically, the use of hexadecimal representation or its rgb() form. Many programming languages, including Kotlin, accept the hexadecimal or its rgb() form, so I designed the app in a way that the user will be the one to input what goes in to the rgb() function, then the job of the app is to take in this input, turn it into its hexadecimal form, and change the background of an ImageView based on this hexadecimal form.

Why I chose this is because there can be many combinations that can be generated, so even if the app is simple, you can't really say you've seen everything the app has to show unless you've seen all the colors possible in the color wheel. To put this into perspective, the amount of possible colors available is 256**3, which is equivalent to 16,777,216 colors.

### Self-reflection

#### Strengths

I think the app does a great job of balancing the challenges of implementing data structures and algorithms, and user experience, with the icons being responsive to an input, as well as having an input button for added quality-of-life.

I think the app is quite user-friendly, it shows where an input is supposed to be and what it corresponds to. And the name of the app sufficiently describes what the main function of the app is supposed to be. In cases of doubt, a pop-up view is available, and it contains a sample of how an interaction is done.

I think the app did a good job of handling errors as well. In the cases where a user enters an invalid input, instead of crashing, it assigns a number 0 on that input instead.

I think the app is flexible and responsive; if the user does not want to input their own value, they can instead press a button to generate a number for them, and on top of this feature, is the responsiveness of the ImageView corresponding to that input. This provides user feedback and lets the user know that their inputs are being recognized by the app

#### Weaknesses

Given the scope of the app, I think it implements all of the necessary structure pretty well, but there is one thing that can be improved upon, which is a way to copy the resulting color's hexadecimal form into the user's clipboard for use. It's one thing to see what the resulting color is and its hexadecimal form, and it's another to be able to do the same, but with the ability to use this outputted value for use.



# Assessment 2 - Multi-view App

## Scope

- [x] Must have logo

- [x] Must have a splash screen.

- [x] Project name should be the app's name ("equinox").

- [x] Provide instructions through a popup activity.

- [x] Must have shared preferences.

- [x] Must have a 3-min walkthrough. First should be displaying the source code, and the next is demonstrating the app.

- [x] Share the code in a github repository.

- [x] 700-word document critical summary. 1: Conceptual goals. 2: How you structured the layout and design. 3: Technical decisions you made in the app. 4: Success, Limitation, and Recommendation. 
## App 
Done with an MVVM architecture. A development process to make the app clean, and testable.

3 elements - activity fragments, view model, repository. We get our data from the "room database" ???, which returns it to the repository, which is then passed to the view model, and can be then observed by activity fragments.

### Set-up Dependencies

In `build.gradle (Project)`:
```
	plugins {  
		...  
		id("com.google.dagger.hilt.android") version "2.44" apply false  
	}
```



In `build.gradle (Module)`:
```
	plugins {  
		id ("kotlin-kapt")  
		id("com.google.dagger.hilt.android")  
	}
	
	android {  
		...  
	}
	
	dependencies {  
		implementation("com.google.dagger:hilt-android:2.44")  
		kapt("com.google.dagger:hilt-android-compiler:2.44")  
	}  
	  
	// Allow references to generated code
	kapt {  
		correctErrorTypes = true  
	}
```

Create a new `Kotlin Class.kt` file with this code:
```
// The name of the file is "NotesApplication"
	package com.example.simplenotesapp  
	import android.app.Application  
	import dagger.hilt.android.HiltAndroidApp  
	  
	@HiltAndroidApp  
	class NotesApplication: Application() {  
	}
```

And put this to your `manifests`:
```
// The name of the class file is "NotesApplication"
	android:name=".NotesApplication"
```

Create a new `package` in `com.example.notesapp` (the same folder where your `.kt` files are). name it: "di".

Then create a new `kotlin class` file, and select `Object`. name it: "AppModule".

Write this code into "AppModule":
```
	package com.example.simplenotesapp.di  
	  
	import dagger.Module  
	import dagger.hilt.InstallIn  
	import dagger.hilt.components.SingletonComponent  
	  
	@Module  
	@InstallIn(SingletonComponent::class)  
	object AppModule {  
	}
```

### Set-up Room DB 

Room provides compile-time verification of sql queries. Provides annotations which minimizes boilerplate code.

Put this code in your `build.gradle.kts (:app)` file:
```
	dependencies {  
	val room_version = "2.6.1"  
	implementation("androidx.room:room-runtime:$room_version")  
	annotationProcessor("androidx.room:room-compiler:$room_version")  
	  
	kapt("androidx.room:room-compiler:2.6.1")  
	  
	implementation("androidx.room:room-ktx:$room_version")  
	implementation("androidx.room:room-rxjava2:$room_version")  
	implementation("androidx.room:room-rxjava3:$room_version")  
	implementation("androidx.room:room-guava:$room_version")  
	testImplementation("androidx.room:room-testing:$room_version")  
	implementation("androidx.room:room-paging:$room_version") 
	}
```

In the same file, add this code in `plugins`:
```
	id("kotlin-parcelize")
```

Create a `package` inside `com.example.notesapp`. name it: "data". 

Then create a `package` inside "data". name it: "entity".

Inside "entity", create a `kotlin class` file, select `Data class`. name it: "Notes".

Write this code inside the "Notes" class:
```
	package com.example.simplenotesapp.data.entity  
	  
	import android.os.Parcelable  
	import androidx.room.Entity  
	import androidx.room.PrimaryKey  
	import kotlinx.android.parcel.Parcelize  
	  
	@Entity(tableName = "notes")  
	@Parcelize  
	data class Note(  
	@PrimaryKey(autoGenerate = true) val id: Int,  
	val title: String?,  
	val content: String?,  
	val date: Long  
	):Parcelable
```

Create a `package` inside "data". name it: "database".

Inside "database", create a `kotlin class` file, name it: "NoteDatabase".

Write this code inside "NoteDatabase":
```
	package com.example.simplenotesapp.data.database  
	  
	import androidx.room.Database  
	import com.example.simplenotesapp.data.entity.Note  
	  
	@Database(entities = arrayOf(Note::class), version = 1)  
	abstract class NoteDatabase: RoomDatabase() {  
	}
```

Inside "data", create a new `package`, and name it: "dao".

Inside "dao", create a `kotlin class` file, select `interface`, and name it: "NoteDao".

In "NoteDao", write this code:
```
	package com.example.simplenotesapp.data.dao  
	  
	import androidx.room.Dao  
	import androidx.room.Delete  
	import androidx.room.Insert  
	import androidx.room.Query  
	import androidx.room.Update  
	import com.example.simplenotesapp.data.entity.Note  
	import kotlinx.coroutines.flow.Flow  
	  
	@Dao  
	interface NoteDao {  
	@Query("Select * from notes order by date desc")  
	fun getAllNotes(): Flow<List<Note>>  
	  
	@Insert  
	suspend fun insertNote(note: Note)  
	  
	@Update  
	suspend fun updatedNote(note: Note)  
	  
	@Delete  
	suspend fun deleteNote(note: Note)  
	}
```

Inside "NoteDatabase", write this code:
```
	abstract fun noteDao(): NoteDao
```

Inside "AppModule", in "di", update the code with:
```
	package com.example.simplenotesapp.di  
	  
	import android.content.Context  
	import androidx.room.Room  
	import com.example.simplenotesapp.data.database.NoteDatabase  
	import dagger.Module  
	import dagger.Provides  
	import dagger.hilt.InstallIn  
	import dagger.hilt.android.qualifiers.ApplicationContext  
	import dagger.hilt.components.SingletonComponent  
	import javax.inject.Singleton  
	  
	@Module  
	@InstallIn(SingletonComponent::class)  
	object AppModule {  
	  
	@Provides  
	@Singleton  
	fun provideRoomDatabase(@ApplicationContext context: Context) =  
	Room.databaseBuilder(context, NoteDatabase::class.java, "NoteDatabase").  
	fallbackToDestructiveMigration().build()  
	  
	@Provides  
	@Singleton  
	fun provideNoteDao(db: NoteDatabase) = db.noteDao()  
	}
```

### Set-up ViewModel

In `com.example.simplenotesapp`, create a `package` called "viewmodel". 

Inside "viewmodel", create a `kotlin class` file, and call it "NoteViewModel".

Write this code into the `dependency` block of `build.gradle.kts (:app)`:
```
	implementation("androidx.lifecycle:lifecycle-viewmodel-ktx:2.8.1")
```

Inside "NoteViewModel", write this code:
```
	package com.example.simplenotesapp.viewmodel  
	  
	import androidx.lifecycle.ViewModel  
	import androidx.lifecycle.viewModelScope  
	import com.example.simplenotesapp.data.dao.NoteDao  
	import com.example.simplenotesapp.data.entity.Note  
	import dagger.hilt.android.lifecycle.HiltViewModel  
	import kotlinx.coroutines.channels.Channel  
	import kotlinx.coroutines.flow.receiveAsFlow  
	import kotlinx.coroutines.launch  
	import javax.inject.Inject  
	  
	@HiltViewModel  
	class NoteViewModel @Inject constructor(private val noteDao: NoteDao): ViewModel() {  
	  
	val notes = noteDao.getAllNotes()  
	  
	val notesChannel = Channel<NotesEvent>()  
	val notesEvent = notesChannel.receiveAsFlow()  
	fun insertNote(note: Note) = viewModelScope.launch {  
	noteDao.insertNote(note)  
	notesChannel.send(NotesEvent.NavigateToNotesFragment)  
	}  
	  
	fun updateNote(note: Note) = viewModelScope.launch {  
	noteDao.updatedNote(note)  
	notesChannel.send(NotesEvent.NavigateToNotesFragment)  
	}  
	  
	fun deleteNote(note: Note) = viewModelScope.launch {  
	noteDao.deleteNote(note)  
	notesChannel.send(NotesEvent.  
	ShowUndoSnackBar("Note Deleted Successfully!", note))  
	}  
	  
	sealed class NotesEvent{  
	data class ShowUndoSnackBar(val msg: String, val note: Note): NotesEvent()  
	object NavigateToNotesFragment: NotesEvent()  
	}  
	}
```

### Designing the UI

In `res/layout`, create a `resource` file, and call it "fragment_notes". Design the "home" screen of the app from here.

After designing "fragment_notes" layout, create another `resource` file called "fragment_addedditnotes". Design the "writing notes" from here.

Then, create another `resource` file and name it: "item_notes".

Then, create a new `Package` in `com.example.simplenotesapp`, and name it: "ui". 

In this new `package`, create a new `Kotlin class` file, name it: "NoteFragment", and write this code:
```
	package com.example.simplenotesapp.ui  
	  
	import androidx.fragment.app.Fragment  
	import com.example.simplenotesapp.R  
	import dagger.hilt.android.AndroidEntryPoint  
	  
	@AndroidEntryPoint  
	class NoteFragment: Fragment(R.layout.fragment_notes) {  
	}
```

In the same `package`, create another `Kotlin class` file, and name it: "AddEditNoteFragment", and write this code:
```
	package com.example.simplenotesapp.ui  
	  
	import androidx.fragment.app.Fragment  
	import com.example.simplenotesapp.R  
	import dagger.hilt.android.AndroidEntryPoint  
	  
	@AndroidEntryPoint  
	class AddEditNoteFragment: Fragment(R.layout.fragment_addeddit_notes) {  
	}
```

Then, go to `MainActivity.kt`, and annotate the class with `@AndroidEntryPoint`:
```
	package com.example.simplenotesapp  
	  
	import androidx.appcompat.app.AppCompatActivity  
	import android.os.Bundle  
	import dagger.hilt.android.AndroidEntryPoint  
	  
	@AndroidEntryPoint  
	class MainActivity : AppCompatActivity() {  
		override fun onCreate(savedInstanceState: Bundle?) {  
		super.onCreate(savedInstanceState)  
		setContentView(R.layout.activity_main)  
		}  
	}
```

### Set up ViewBinding

In the `build.gradle.kts (:app)` file, go to the `android{ }` block and write this code:
```
	buildFeatures{  
		viewBinding = true  
	}
```

Create a new `package` file in `com.example.simplenotesapp`, and name it: "adapter".

In "adapter", create a new `Kotlin class` file, and name it: "NoteAdapter". In this file, write this code:
```
	package com.example.simplenotesapp.adapter  
	  
	import android.view.LayoutInflater  
	import android.view.ViewGroup  
	import androidx.recyclerview.widget.RecyclerView  
	import com.example.simplenotesapp.data.entity.Note  
	import com.example.simplenotesapp.databinding.ItemNotesBinding  
	import java.text.SimpleDateFormat  
	  
	class NoteAdapter(private val mNotes: List<Note>, private val listener: 
	OnNoteClickListener): RecyclerView.Adapter<NoteAdapter.ViewHolder>() {  
	  
		interface OnNoteClickListener{  
			fun onNoteClick(note: Note)  
			fun onNoteLongClick(note: Note)  
		}  
		
		inner class ViewHolder(private val binding: ItemNotesBinding): 
		RecyclerView.ViewHolder(binding.root){  
		  
			init {  
				binding.apply{  
					root.setOnClickListener{  
						val position = adapterPosition  
						if (position != RecyclerView.NO_POSITION){  
							val note = mNotes[position]  
							listener.onNoteClick(note)  
						}  
					}  
			  
					root.setOnLongClickListener{  
						val position = adapterPosition  
						if (position != RecyclerView.NO_POSITION){  
								val note = mNotes[position]  
								listener.onNoteLongClick(note)  
						}  
			  
						true  
					}  
				}  
			}  
			
			fun bind(note: Note){  
				binding.apply{  
					titleNote.text = note.title  
					contentNote.text = note.content  
					val formatter = SimpleDateFormat("dd/MM/yyyy")  
					dateNote.text = formatter.format(note.date)  
				}  
			}  
		}  
		  
		  
		override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): 
		ViewHolder {  
		
			val binding = ItemNotesBinding.inflate(LayoutInflater.from
			(parent.context), parent, false)  
			return ViewHolder(binding)  
		}  
		  
		override fun getItemCount(): Int {  
			return mNotes.size  
		}  
		  
		override fun onBindViewHolder(holder: ViewHolder, position: Int) {  
			with(mNotes[position]){  
				holder.bind(this)  
			}  
		}  
	}
```

### Set up Navigation component

In the `res` folder, create a new `resource` file, name it: "nav_graph", in the `resource type:` change it to `Navigation`. Allow to import the dependencies.

Add the screens for "noteFragment" and "addEditNoteFragment", and connect them to each other.

In "addEditNoteFragment", add an `Argument`, name it: "note"; its type is `Custom Parcelable`; its class is `Note`. Check `nullable`, and add it.

In "activity_main.xml", clear the screen, and drag-and-drop a `NavHostContainer`, and select on "nav_graph".

In "MainActivity.kt", write this code:
```
	package com.example.simplenotesapp  
	  
	import androidx.appcompat.app.AppCompatActivity  
	import android.os.Bundle  
	import androidx.navigation.NavController  
	import androidx.navigation.fragment.NavHostFragment  
	import androidx.navigation.ui.navigateUp  
	import androidx.navigation.ui.setupActionBarWithNavController  
	import dagger.hilt.android.AndroidEntryPoint  
	  
	@AndroidEntryPoint  
	class MainActivity : AppCompatActivity() {  
	    lateinit var navController: NavController  
	    override fun onCreate(savedInstanceState: Bundle?) {  
	        super.onCreate(savedInstanceState)  
	        setContentView(R.layout.activity_main)  
	  
	        val navHostFragment = supportFragmentManager.findFragmentById(R.id.nav_host) as NavHostFragment  
	  
	        navController = navHostFragment.navController  
	  
	        setupActionBarWithNavController(navController)  
	    }  
	  
	    override fun onSupportNavigateUp(): Boolean {  
	        return super.onSupportNavigateUp() || navController.navigateUp()  
	    }  
	}
```

Add these dependencies:

Top-level `build.gradle`:
```
	buildscript{  
	    repositories{  
	        google()  
	    }  
	  
	    dependencies{  
	        val nav_version = "2.7.7"  
	        classpath("androidx.navigation:navigation-safe-args-gradle-plugin:$nav_version")  
	    }
```

Module-level:
```
	plugins{
		id("androidx.navigation.safeargs.kotlin")
	}
```

### Completing the App

In "NoteFragment.kt", write this code:
```
	package com.example.simplenotesapp.ui  
	  
	import android.os.Bundle  
	import android.view.View  
	import android.widget.GridLayout  
	import androidx.fragment.app.Fragment  
	import androidx.fragment.app.viewModels  
	import androidx.lifecycle.lifecycleScope  
	import androidx.navigation.fragment.findNavController  
	import androidx.recyclerview.widget.GridLayoutManager  
	import com.example.simplenotesapp.R  
	import com.example.simplenotesapp.adapter.NoteAdapter  
	import com.example.simplenotesapp.data.entity.Note  
	import com.example.simplenotesapp.databinding.FragmentNotesBinding  
	import com.example.simplenotesapp.viewmodel.NoteViewModel  
	import com.google.android.material.snackbar.Snackbar  
	import dagger.hilt.android.AndroidEntryPoint  
	import kotlinx.coroutines.launch  
	  
	@AndroidEntryPoint  
	class NoteFragment: Fragment(R.layout.fragment_notes), NoteAdapter.OnNoteClickListener {  
	    val viewModel by viewModels<NoteViewModel>()  
	    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {  
	        super.onViewCreated(view, savedInstanceState)  
	          
	  
	        val binding = FragmentNotesBinding.bind(requireView())  
	  
	        binding.apply {  
	            recyclerViewNotes.layoutManager = GridLayoutManager(context, 2)  
	            recyclerViewNotes.setHasFixedSize(true)  
	  
	            addButton.setOnClickListener{  
	                val action = NoteFragmentDirections.actionNoteFragmentToAddEditNoteFragment(null)  
	                findNavController().navigate(action)  
	            }  
	  
	            viewLifecycleOwner.lifecycleScope.launch {  
	                viewModel.notes.collect{notes ->  
	                    val adapter = NoteAdapter(notes, this@NoteFragment)  
	                    recyclerViewNotes.adapter = adapter  
	                }  
	            }  
	            viewLifecycleOwner.lifecycleScope.launch {  
	                viewModel.notesEvent.collect{event ->  
	                    if (event is NoteViewModel.NotesEvent.ShowUndoSnackBar){  
	                        Snackbar.make(requireView(), event.msg, Snackbar.LENGTH_LONG).setAction("Undo"){  
	                            viewModel.insertNote(event.note)  
	                        }.show()  
	                    }  
	                }  
	            }        }    }  
	  
	    override fun onNoteClick(note: Note) {  
	        val action = NoteFragmentDirections.actionNoteFragmentToAddEditNoteFragment(note)  
	        findNavController().navigate(action)  
	    }  
	  
	    override fun onNoteLongClick(note: Note) {  
	        viewModel.deleteNote(note)  
	    }  
	}
```

In "AddEditNoteFragment.kt", write this code:
```
package com.example.simplenotesapp.ui  
  
import android.os.Bundle  
import android.view.View  
import androidx.fragment.app.Fragment  
import androidx.fragment.app.viewModels  
import androidx.lifecycle.lifecycleScope  
import androidx.navigation.fragment.findNavController  
import androidx.navigation.fragment.navArgs  
import com.example.simplenotesapp.R  
import com.example.simplenotesapp.data.entity.Note  
import com.example.simplenotesapp.databinding.FragmentAddedditNotesBinding  
import com.example.simplenotesapp.databinding.FragmentNotesBinding  
import com.example.simplenotesapp.viewmodel.NoteViewModel  
import dagger.hilt.android.AndroidEntryPoint  
import kotlinx.coroutines.launch  
  
@AndroidEntryPoint  
class AddEditNoteFragment: Fragment(R.layout.fragment_addeddit_notes) {  
    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {  
        super.onViewCreated(view, savedInstanceState)  
  
        val viewModel by viewModels<NoteViewModel>()  
        val binding = FragmentAddedditNotesBinding.bind(requireView())  
        val args: AddEditNoteFragmentArgs by navArgs()  
        val note = args.note  
  
        if (note != null){  
            binding.apply {  
                titleEdit.setText(note.title)  
                contentEdit.setText(note.content)  
                saveButton.setOnClickListener{  
                    val title = titleEdit.text.toString()  
                    val content = contentEdit.text.toString()  
                    val updatedNote = note.copy(title = title, content = content, date = System.currentTimeMillis())  
                    viewModel.updateNote(updatedNote)  
                }  
            }        }  
  
        else{  
            binding.apply {  
                saveButton.setOnClickListener{  
                    val title = titleEdit.text.toString()  
                    val content = contentEdit.text.toString()  
                    val note = Note(title = title, content = content, date = System.currentTimeMillis())  
                    viewModel.insertNote(note)  
                }  
            }        }  
  
        viewLifecycleOwner.lifecycleScope.launch {  
            viewModel.notesEvent.collect{event ->  
                if (event is NoteViewModel.NotesEvent.NavigateToNotesFragment){  
                    val action = AddEditNoteFragmentDirections.actionAddEditNoteFragmentToNoteFragment()  
                    findNavController().navigate(action)  
                }  
            }  
        }    
	}  
}
```

Go to `data/entity/Note`, and write this code:
```
	package com.example.simplenotesapp.data.entity  
	  
	import android.os.Parcelable  
	import androidx.room.Entity  
	import androidx.room.PrimaryKey  
	import kotlinx.android.parcel.Parcelize  
	  
	@Entity(tableName = "notes")  
	@Parcelize  
	data class Note(  
	    @PrimaryKey(autoGenerate = true) val id: Int = 0,  
	    val title: String?,  
	    val content: String?,  
	    val date: Long  
	):Parcelable
```

In "AndroidManifest.xml", find `android:theme` and change it to `"@style/Theme.AppCompat"`.



## Summary

### Conceptual Goals

When thinking about what my second app should be, I wanted to make something that can be useful; something that can be used outside of just being a project to submit for school. I wanted an app that had some utility. This is the main theme behind why I created the apps the way they are.

I found myself using a notes application "Obsidian", so I thought: "Maybe I should make a notes application, as well". I later realized that the task to create an app like this, with the current knowledge I have, was going to be impossible to do on my own. But despite this, I pressed on with my plan to create a "notes" application, despite most of the app's logic being borrowed from a series of YouTube videos.


### Layout and Design

The app's design is very simple. It uses a RecyclerView, which uses a GridLayoutManager which is why you can see if you have 2 notes, they are arranged side-by-side. This RecyclerView allows for reusing Views when they are scrolled off the screen, hence the name "RecyclerView". I did not hardcode the layout of the design; instead, the RecyclerView does all the layout management.

There are a few buttons on the app: The "help" button, the "theme" button, and the "add note" button. These buttons are the only allowed actions a user can make other than reading the notes or editing them. I've put them in the bottom since this is where "action" buttons are being put primarily nowadays. Just like the "back", "home", "opened apps" buttons in android phones being put at the bottom, I've also decided to put the 3 buttons at the bottom.
  
From what you can see in the app, the "help" and "theme" buttons are both on the left side of the screen, whereas the "add notes" button is on the right. This is because the "add notes" button performs a primary action, like adding a new note, whereas the other 2 buttons show a PopupView and the other changes the theme of the app. Bottom line: The "add notes" button is part of the core design of the app, whereas the other 2 buttons are for improving the user experience. I thought it would be best to make that distinction and put the buttons separately.

### Technical Decisions

The app uses a few dependencies, mainly: "Hilt" and "Room" dependencies. These dependencies allow for use of annotations, which reduces manual code writing for boilerplate codes. We can just annotate Classes and functions with features from these dependencies to our code, thus minimizing the requirement for "reinventing the wheel".

The app creates a Room database that manages a local SQLite database. This is how the app is keeping all the notes persistently, by using local storage data. Deleting the app may delete all the notes as well. The app is able to insert, delete, and query the notes. These functions have been annotated by the Room dependency, so the code is actually from the dependency itself; it is not built by me.

The app has a Data class that represents the contents of the notes, which is annotated by "Room". There is a ViewModel that interacts with one of the classes to perform "insert", "delete", and "update" operations. These functions are database operations, which interact with the created database upon installing the app.

How the RecyclerView works is by using an adapter to get the data from the created database, which then binds the data into the views, which is how the user can see what they've written on the app after creating a note. And when the user writes on a note, it is either updated or inserted as a new entry into the database.

There is also a feature on the app where if the user long-clicks a note, it is automatically deleted. After deleting a note, there is a "grace" period where the user can undo the action; clicking on undo reinserts the note back.

### Self-reflection

#### Success

The app that I made satisfied my want to make a usable app that goes beyond than just a simple school project app. It went above-and-beyond to what I was trying to accomplish and I feel that this is enough for my second app project.

#### Limitations

Making this app made me realize how much I needed to know before making a simple notes app; I simply do not know enough about how the app works and why it works. I was just being handheld by the tutorial that I followed.

I hope I can find the time to learn more about how this app works.

#### Recommendation

Next time I should be prepared to make an app that could satisfy school requirements without having to rely on tutorials to implement the core concepts I want. I either make it on my own or I don't.


## Video Script

This is my multi-view application. It is a notes-taking app. What this means is that you can create a note that contains a header and body. 

After creating the note, the note's contents will be written in a local database to store the data. This means the content you've written will persist in the app as long as you don't delete the application.

The data is displayed through a RecyclerView with an adapter. The adapter communicates with the database, and outputs the data into the RecyclerView, and the RecyclerView creates the respective views to represent each note.

The RecyclerView is used to display the app in a by-2 grid layout. When the app has a lot of notes, it removes the Views of notes that are off-screen and use this View to create views for the ones that are on-screen, hence the name: "RecyclerView". At least, this is my understanding of it. 

Most of the code uses annotations, which are responsible for creating the boilerplate code of the core mechanics of the app. The rest of the code is written to bind events on the items in the layout to make the app functional.

The app has shared preferences, which is a button to change to dark/light mode, and a PopupView to show instructions to the user.

