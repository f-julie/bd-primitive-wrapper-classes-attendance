## Weekly Roster Manager

**GitHub repo:** [ebd-primitive-wrapper-classes-attendance](https://github.com/LambdaSchool/ebd-primitive-wrapper-classes-attendance)

### Context

This activity was written during a previous version of ATA. At the time,
participants attended after-hours class once a week. Class was offered
two days a week (Tuesday and Thursday), with the participants split
approximately evenly between days, referred to as "Sections".

### Intro
Today we are going to be building a small tool to help ATA's program
managers track and report to instructors weekly absences and swaps.
Let's take a look at the skeleton code that we have been provided. Open
the `WeeklyRosterManager` class in this package.

The class has two private fields and a constructor to initialize them:
- `mondayOfTeachingWeek : LocalDate` - the monday of the week's
  classes that attendance is being managed for
- `manger : ParticipantManger` - an object that stores `Participant`
  data (currently a hard coded set of participants), and can be used to
  look up `Participant` s by their id.
  
The class also has four unimplemented methods. Three for completion of
this activity:
- `void addParticipantsToSection(SectionDay section, String participantList)`
- `void printClassRosters()`
- `boolean scheduleAbsence(SectionDay attendedSection, long participantId)`

and one for extension:
- `boolean scheduleSwap(SectionDay swapOutOf, long participantId)`

Review the methods' Javadocs and discuss what they are doing with your
table.

Finally, there is a main method. Go ahead and run the main method with
the current code in `WeeklyRosterManager`. You should see something like
this:
    
    Marking participants as absent.
    ERROR: Unsuccessful in marking Participant with id: 7 as absent from TUESDAY
    
The main method is interacting with the `WeeklyRosterManger`, trying to
assign participants to their respective sections, mark a few as absent,
and print the rosters for each sections after the updates have been
made. We have included some tests in the `main` method to ensure we are unable
to mark participants absent in the wrong section or swap participants out
of a section they do not typically attend.

At the moment, not a lot is happening, since the methods of `WeeklyRosterManger`
have yet to be implemented. We are running into an error, then the program is
exiting. Your goal is to decide how to store and maintain the rosters for each
section, then write the logic for the methods listed above. Once you have
implemented those methods you should see output like the following:

    Setting class rosters to standard sections.
    
    Marking participants as absent.
    Participant with id: 7 marked as absent from TUESDAY
    Participant with id: 37 marked as absent from THURSDAY
    
    Printing section rosters.

    28 participants attending class on: TUESDAY the week of: 2019-08-13
    
    Participant ID: 1, Alias: beckwc, Name: Conner Beckwith
    Participant ID: 2, Alias: shanelys, Name: Shane Lyse
    Participant ID: 3, Alias: macase, Name: Matt Case
    Participant ID: 4, Alias: alsepta, Name: Aaron Alsept
    Participant ID: 5, Alias: rosnyde, Name: Bob Snyder
    Participant ID: 6, Alias: kabilaw, Name: Kabila Williams
    Participant ID: 8, Alias: milhoanb, Name: Theta Milhoan
    Participant ID: 9, Alias: sulscott, Name: Scott Sullivan
    Participant ID: 10, Alias: metwg, Name: Max Twogood
    Participant ID: 11, Alias: jpaulm, Name: John-Paul Mullally
    Participant ID: 12, Alias: marmi, Name: Michael Martinez
    Participant ID: 13, Alias: aeedberg, Name: Aaron Edberg
    Participant ID: 14, Alias: clooney, Name: Clinton Looney
    Participant ID: 15, Alias: tinayun, Name: Tina Yun
    Participant ID: 16, Alias: jakebest, Name: Jacob Best
    Participant ID: 17, Alias: bpollitt, Name: Blake Pollitt
    Participant ID: 18, Alias: carriaus, Name: Austin Carrillo
    Participant ID: 19, Alias: wickerts, Name: Sammy Wickert
    Participant ID: 20, Alias: holleej, Name: Hollee Klesh
    Participant ID: 21, Alias: albaum, Name: Adam Albaum
    Participant ID: 22, Alias: hansubin, Name: Subin Hong
    Participant ID: 23, Alias: khinp, Name: Pavel Khinotskiy
    Participant ID: 24, Alias: beilfuss, Name: Lindsay Beilfuss
    Participant ID: 25, Alias: maryliu, Name: Mary Liu
    Participant ID: 26, Alias: fishbone, Name: Daniel Fishbone
    Participant ID: 27, Alias: mitcreed, Name: Mitch Reed
    Participant ID: 28, Alias: jackslin, Name: Jackson Lin
    Participant ID: 29, Alias: thrall, Name: Thomas Ralls

    29 participants attending class on: THURSDAY the week of: 2019-08-13

    Participant ID: 30, Alias: hrachyag, Name: Hrach Gabrielyan
    Participant ID: 31, Alias: wartyle, Name: Ty Warren
    Participant ID: 32, Alias: anthleng, Name: Anthony Leng
    Participant ID: 33, Alias: kuljot, Name: Kuljot Anand
    Participant ID: 34, Alias: mnnategh, Name: Mahsa Nategh
    Participant ID: 35, Alias: evgenb, Name: Evgenia Belofastowa
    Participant ID: 36, Alias: rakundan, Name: Kundan Rai
    Participant ID: 38, Alias: davfrost, Name: Dave Frost
    Participant ID: 39, Alias: llna, Name: Lina Liu
    Participant ID: 40, Alias: belvinjb, Name: Jon Belvin
    Participant ID: 41, Alias: jbrossea, Name: Julia Brosseau
    Participant ID: 42, Alias: jamisch, Name: Jami Schwarzwalder
    Participant ID: 43, Alias: suncarol, Name: Carolyn Sun
    Participant ID: 44, Alias: londonbr, Name: London Brown
    Participant ID: 45, Alias: bjckso, Name: Bri Jackson
    Participant ID: 46, Alias: halirick, Name: Ricky Halim
    Participant ID: 47, Alias: stelunga, Name: Adlaai Stelung
    Participant ID: 48, Alias: cbbenben, Name: Christopher Benben
    Participant ID: 49, Alias: mbrandow, Name: Brandon Williams
    Participant ID: 50, Alias: callaj, Name: Callahan Jacobs
    Participant ID: 51, Alias: cwhitese, Name: Chad Whitesel
    Participant ID: 52, Alias: bitsez, Name: Zach Bitseff
    Participant ID: 53, Alias: janaravi, Name: Janani Ravi
    Participant ID: 54, Alias: oliviabr, Name: Oz Brown
    Participant ID: 55, Alias: mpopish, Name: Mario Popish
    Participant ID: 56, Alias: stepsong, Name: Stephanie Song
    Participant ID: 57, Alias: mwimwila, Name: Mwila Mwila
    Participant ID: 58, Alias: ynng, Name: Y Ngo
    Participant ID: 59, Alias: jacobnew, Name: Jacob Newton-Gladstein

    
### Getting to know relevant classes
#### `SectionDay`
An enum with two values, TUESDAY and THURSDAY. You should not need to
modify.

#### `Participant`
A POJO describing an ATA Participant. This includes an id, alias, and
name. You should not need to modify.


#### `ATASet<E>`
A class that stores and provides access to a unique collection of
elements. For example: if the ATASet currently contains {"hello", "hi",
"hey"} and you try to add "hi", the add method will return false and the
ATASet will still just contain {"hello", "hi", "hey"}. The collection is
fixed size, and the capacity is provided at construction. Elements can
be added up to the capacity. Once the collection is full, elements will
fail to be added. The elements can also be searched.

### Implement `WeeklyRosterManager`
For completion, implement the methods:
- `void addParticipantsToSection(SectionDay section, String participantList)`
- `void printClassRosters()`
- `boolean scheduleAbsence(SectionDay attendedSection, long participantId)`

You can interact with the code via the main method provided by running
it in IntelliJ.

### EXTENSION: Implement `scheduleSwap`
As an extension, you can implement section swaps. You should implement 
the following method:
- `boolean scheduleSwap(SectionDay swapOutOf, long participantId)`

Once you have `scheduleSwap` implemented you can uncomment the code
blocks in the bottom of the main method to try out your swapping logic.
Your main method should generate output like the following:
Setting class rosters to standard sections.

    Marking participants as absent.
    Participant with id: 7 marked as absent from TUESDAY
    Participant with id: 37 marked as absent from THURSDAY
    
    Performing participant swaps.
    Participant with id: 22 swapped into THURSDAY
    Participant with id: 36 swapped into TUESDAY
    
    Printing section rosters.
    
    28 participants attending class on: TUESDAY the week of: 2019-08-13
    
    Participant ID: 1, Alias: beckwc, Name: Conner Beckwith
    Participant ID: 2, Alias: shanelys, Name: Shane Lyse
    Participant ID: 3, Alias: macase, Name: Matt Case
    Participant ID: 4, Alias: alsepta, Name: Aaron Alsept
    Participant ID: 5, Alias: rosnyde, Name: Bob Snyder
    Participant ID: 6, Alias: kabilaw, Name: Kabila Williams
    Participant ID: 8, Alias: milhoanb, Name: Theta Milhoan
    Participant ID: 9, Alias: sulscott, Name: Scott Sullivan
    Participant ID: 10, Alias: metwg, Name: Max Twogood
    Participant ID: 11, Alias: jpaulm, Name: John-Paul Mullally
    Participant ID: 12, Alias: marmi, Name: Michael Martinez
    Participant ID: 13, Alias: aeedberg, Name: Aaron Edberg
    Participant ID: 14, Alias: clooney, Name: Clinton Looney
    Participant ID: 15, Alias: tinayun, Name: Tina Yun
    Participant ID: 16, Alias: jakebest, Name: Jacob Best
    Participant ID: 17, Alias: bpollitt, Name: Blake Pollitt
    Participant ID: 18, Alias: carriaus, Name: Austin Carrillo
    Participant ID: 19, Alias: wickerts, Name: Sammy Wickert
    Participant ID: 20, Alias: holleej, Name: Hollee Klesh
    Participant ID: 21, Alias: albaum, Name: Adam Albaum
    Participant ID: 23, Alias: khinp, Name: Pavel Khinotskiy
    Participant ID: 24, Alias: beilfuss, Name: Lindsay Beilfuss
    Participant ID: 25, Alias: maryliu, Name: Mary Liu
    Participant ID: 26, Alias: fishbone, Name: Daniel Fishbone
    Participant ID: 27, Alias: mitcreed, Name: Mitch Reed
    Participant ID: 28, Alias: jackslin, Name: Jackson Lin
    Participant ID: 29, Alias: thrall, Name: Thomas Ralls
    Swaps: 
    Participant ID: 36, Alias: rakundan, Name: Kundan Rai
    
    29 participants attending class on: THURSDAY the week of: 2019-08-13
    
    Participant ID: 30, Alias: hrachyag, Name: Hrach Gabrielyan
    Participant ID: 31, Alias: wartyle, Name: Ty Warren
    Participant ID: 32, Alias: anthleng, Name: Anthony Leng
    Participant ID: 33, Alias: kuljot, Name: Kuljot Anand
    Participant ID: 34, Alias: mnnategh, Name: Mahsa Nategh
    Participant ID: 35, Alias: evgenb, Name: Evgenia Belofastowa
    Participant ID: 38, Alias: davfrost, Name: Dave Frost
    Participant ID: 39, Alias: llna, Name: Lina Liu
    Participant ID: 40, Alias: belvinjb, Name: Jon Belvin
    Participant ID: 41, Alias: jbrossea, Name: Julia Brosseau
    Participant ID: 42, Alias: jamisch, Name: Jami Schwarzwalder
    Participant ID: 43, Alias: suncarol, Name: Carolyn Sun
    Participant ID: 44, Alias: londonbr, Name: London Brown
    Participant ID: 45, Alias: bjckso, Name: Bri Jackson
    Participant ID: 46, Alias: halirick, Name: Ricky Halim
    Participant ID: 47, Alias: stelunga, Name: Adlaai Stelung
    Participant ID: 48, Alias: cbbenben, Name: Christopher Benben
    Participant ID: 49, Alias: mbrandow, Name: Brandon Williams
    Participant ID: 50, Alias: callaj, Name: Callahan Jacobs
    Participant ID: 51, Alias: cwhitese, Name: Chad Whitesel
    Participant ID: 52, Alias: bitsez, Name: Zach Bitseff
    Participant ID: 53, Alias: janaravi, Name: Janani Ravi
    Participant ID: 54, Alias: oliviabr, Name: Oz Brown
    Participant ID: 55, Alias: mpopish, Name: Mario Popish
    Participant ID: 56, Alias: stepsong, Name: Stephanie Song
    Participant ID: 57, Alias: mwimwila, Name: Mwila Mwila
    Participant ID: 58, Alias: ynng, Name: Y Ngo
    Participant ID: 59, Alias: jacobnew, Name: Jacob Newton-Gladstein
    Swaps: 
    Participant ID: 22, Alias: hansubin, Name: Subin Hong

### Commit & Push
 
1. When you have the code to where you want it (at least compiling,
   ideally tests succeeding), commit it.
1. Push it to your remote branch.
1. Go back to the Weekly Roster Manger Canvas page and paste in a link
   to your commit.
