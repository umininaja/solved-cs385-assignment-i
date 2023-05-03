Download Link: https://assignmentchef.com/product/solved-cs385-assignment-i
<br>
Your first programming assignment will be for the purpose of reviewing basic Java. Your prior knowledge of Java and the review lectures of module 1 should be sufficient for doing this assignment.  In this assignment you are to write classes for a <em>simple calendar </em>application.  More specifically, you should write the following three classes:

<ul>

 <li><strong>java:</strong> for representing the dates/days</li>

 <li><strong>java:</strong> for representing an event.</li>

 <li><strong>java:</strong> for storing a set of events</li>

</ul>

The specification for each class is as follows:

<h1>Class Date</h1>

<strong>Class Definition: </strong>

Class Date should implement the “Comparable” interface:

<strong>public</strong> <strong>class</strong> <u>Date</u> <strong>implements</strong> <u>Comparable&lt;Date&gt;</u> { //Data fields and Method}

<strong>Data Fields: </strong>

Class Date has three data fields:

<ul>

 <li><strong>int year</strong> (must be between 2014-2020)</li>

 <li><strong>int month</strong> (must be between 1-12)</li>

 <li><strong>int day </strong>(must be between 1-31)</li>

</ul>

<strong>Constructors: </strong>

Class Date has one constructor which initializes year, month, and year. The signature for this constructor is as follows:

<strong>public</strong> Date(<strong>int</strong> year, <strong>int</strong> month, <strong>int</strong> day) <strong>throws</strong> IllegalArgumentException {

//constructor body}

You should check to see if each argument is within the specified range and throw an IllegalArgumentException otherwise. (If you don’t remember the exception handling in java watch this complete tutorial on youtube: <a href="https://www.youtube.com/watch?v=-aQeyTGqoQc">http://www.youtube.com/watch?v=-aQeyTGqoQc</a> )

<strong>Methods </strong>

<ul>

 <li>Accessors for all three data fields<strong>: int getYear(), int getMonth(), int getDay() </strong></li>

 <li><strong>String toString():</strong> produces a string version of the date which should be in the form “month/day/year”</li>

 <li><strong>Boolean equals( Object obj): </strong>This method overrides the “equals” method in the Object class. It returns true if this Date object has the same year, month and day as obj. Otherwise, it returns false. Before checking for equality “obj” must be casted to “Date as follows:</li>

</ul>

<strong>public</strong> <u>Boolean</u> equals(Object obj){

Date otherDate = (Date)obj;

//the rest of the method body}

Now you can compare  this Date object with “otherDate” object.

<strong>  </strong>

<ul>

 <li><strong>public int compareTo(Date otherDate):</strong> This method is inherited from Comparable interface and must return</li>

</ul>

o    0 if this Date object is equal to the otherDate object o           -1 if this Date object is earlier than the otherDate object o           +1  if   this Date object is later than the otherDate object

<h1>Class Event</h1>

<strong>Class Definition: </strong>

<strong>        </strong>

<strong>public</strong> <strong>class</strong> Event { //Date <u>fields</u> and Methods}

<strong>Data Fields: </strong>

<ul>

 <li><strong>Date date:</strong> (the date of the event)</li>

 <li><strong>int start: (</strong>The start time/hour of the event. It must be a number between 0-23)</li>

 <li><strong>int day: </strong>(the end time/hour of the event. It must be a number between 0-23)</li>

 <li><strong>String description: </strong>( A description of the event.)</li>

</ul>

<strong>Constructors: </strong>

Class Event has one constructor which initializes Date, start, end, and description. The signature for this constructor is as follows:

<strong>public</strong> Event (Date date, <strong>int</strong> start, <strong>int</strong> end, String description) <strong>throws</strong>

IllegalArgumentException{

//constructor body}

You should check to see if “start” hour is less than or equal “end” hour and throw an IllegalArgumentException otherwise.

<strong>Methods: </strong>

<ul>

 <li>Accessors for all three fields: <strong>Date getDate(), int getStart(), int getEnd(), String getDescription().</strong></li>

 <li>A Mutator for the description field: <strong>void setDescription(String newDescription)</strong></li>

 <li><strong>String toString()</strong>: Produces a string version of an Event which should be of the form: “month/day/year start–end: description”.</li>

 <li><strong>Boolean equals(Object obj)</strong> – Determines whether two Event objects represent the same event. True if both event objects have the same date, start, end, and description attributes (use equals to compare dates and description).</li>

</ul>

<h1>Class Calendar</h1>

<strong>public</strong> <strong>class</strong> Calendar { //Date <u>fields</u> and Methods}

<strong>Data Fields: </strong>

<ul>

 <li><strong>static final int MAXEVENTS=4 : </strong>A constant representing the maximum number of events that can be stored. Make it just 4 to support easy testing!</li>

 <li><strong>Event[] events: </strong>An array holding the scheduled events, of size MAXEVENTS. If you don’t remember how to initialize an array and access its elements, please refer to this Oracle Tutorial</li>

</ul>

<a href="https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html">(</a><a href="https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html">http://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html</a><a href="https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html"> )</a>

<ul>

 <li><strong>int numEvents – </strong>The number of events currently scheduled (i.e., the number of entries in the “events” array).</li>

</ul>

<strong>Constructors: </strong>

Class Calendar has one default constructor which creates an empty array of events of size MAXEVENTS, and initializes numEvents to zero.

<strong>public</strong> Calendar() {

//Constructor Body

}

<strong>Methods: </strong>

<ul>

 <li><strong>Boolean addEvent(Event e): </strong>Adds an event to the events array if array is not full</li>

</ul>

(numEvents==MAXEVENTS). It returns true if the event is successfully added and false otherwise. If the array is not already full, you should traverse the array and insert the event in place of the first null entry. Don’t forget to increment the “numEvents” if an event is added successfully.

<ul>

 <li><strong>int findEvent(Event e):</strong> traverses the “events” array to look for an event that is equal to “e”. If such event is found, then the index of it in the array is returned. Otherwise, “-1” is returned. Note that the array may contain null entries so before checking for equality, make sure that the array entry is not null otherwise your program may throw a NullPointerException.</li>

 <li><strong>Boolean removeEvent(Event e):</strong> removes an event from the array and returns true if the remove operation is successful and false otherwise. Your method should first call FindEvent to retrieve the index of the array entry that contains the event. If FindEvent returns -1 then the event does not exist in the array and your method should return false. Otherwise, your method should set the array entry to null.</li>

 <li><strong>Void dump():</strong> Prints all the events in the calendar (i.e. all <strong>non-null</strong> entries in the “events” array). Each event should be printed in a separate line.</li>

</ul>

<strong> </strong>

After you are done with writing the above three classes. Use that attached <strong>“CalendarTest.java”</strong> class to test your three classes. This is the test harness I use for grading your program. Make sure that your classes pass all the tests.

<strong>What you should turn in: </strong>

You should turn in three java files: “<strong>Date.java”, “Event.java”, and  “Calendar.java”</strong>.  Please do not leave extra/unwanted code (particularly print/debug statements) in your submission.


