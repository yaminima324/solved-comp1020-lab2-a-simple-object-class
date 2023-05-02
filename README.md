Download Link: https://assignmentchef.com/product/solved-comp1020-lab2-a-simple-object-class
<br>
<ul>

 <li>Basic objects – instance variables, instance methods, constructors</li>

 <li>Class variables and class methods (i.e. static)</li>

 <li>Sorting objects using compareTo (Gold exercise only)</li>

</ul>

Notes:

<ul>

 <li>In the lab, all exercises are to be done using Dr. Java. (At home, use anything, as usual.)  Make sure your TA has recorded your mark before leaving.</li>

 <li>The three questions are sequential – each builds on the previous one.</li>

 <li>Always try to complete as many as you can. The Gold exercise uses some material that has not yet been fully covered, but it is explained briefly here.</li>

</ul>

<ol>

 <li>Create a file <strong>HockeyTeam</strong><strong><sub>.java</sub></strong> which will implement a class of objects that will store some information about a hockey team. In your file, implement the following variables and methods.

  <ol>

   <li><strong>private</strong> instance variables that will store the team’s name (a <strong><sub>String</sub></strong>), and the number of wins, losses, and overtime losses (three <strong><sub>int</sub></strong> values).</li>

   <li>a constructor that will accept those four data values, in the order listed above. A new <strong>HockeyTeam</strong> object will always be created by using an expression such as</li>

  </ol></li>

</ol>

<strong>new HockeyTeam(“Winnipeg”,22,14,8) </strong>

<ol>

 <li>three <strong>public</strong> methods <strong>void won()</strong>, <strong>void lost()</strong>, and <strong>void lostOvertime()</strong>, each of which will add one to the corresponding integer value.</li>

 <li>a <strong>public</strong> method <strong><sub>int points()</sub></strong> which will calculate and return the number of points that the team has. A team receives 2 points for each win, 0 points for each loss, and 1 point for each overtime loss.</li>

 <li>a <strong>public</strong> method <strong>String toString()</strong> which will return a <strong>String</strong> giving all of the information stored about a team, and the number of points that the team has, in the format <strong>“Winnipeg(22,14,8=52)” </strong>where 52 is the number of points (22*2+8). This method should call the <strong><sub>points()</sub></strong></li>

</ol>




<ol start="2">

 <li>Run the supplied file <strong><sub>java</sub></strong> to test your <strong><sub>HockeyTeam</sub></strong> class. Look at the contents of that file to see how it is creating, updating, and printing team data. If your class is working correctly the output should be:</li>

</ol>

<strong>Initial teams: </strong>

<strong>Winnipeg(22,14,8=52) Chicago(28,13,2=58) </strong>

<strong>Colorado(18,17,8=44) </strong>

<strong>St. Louis(27,13,3=57) Dallas(19,16,7=45) </strong>

<strong>Minnesota(18,19,5=41) </strong>

<strong>Nashville(29,9,4=62) </strong>

<strong> </strong>

<strong>Final teams: </strong>

<strong>Winnipeg(28,14,8=64) Chicago(28,15,2=58) </strong>

<strong>Colorado(19,17,9=47) </strong>

<strong>St. Louis(28,13,4=60) Dallas(19,18,7=45) Minnesota(18,20,5=41) </strong>

<strong>Nashville(29,9,5=63)</strong>




<ol>

 <li>Modify your <strong><sub>HockeyTeam</sub></strong> class by adding the following class (static) variables and methods:

  <ol>

   <li>A few <strong>private</strong> class variables to keep a list of all of the <strong><sub>HockeyTeam</sub></strong> objects that have been created, as a partially-full array with a maximum capacity of 64 teams. You will need an array of <strong>HockeyTeam</strong> objects, an <strong>int</strong> to keep track of the current number of teams, and a constant for the maximum capacity (64). (A separate <strong>HockeyTeamList</strong> class would be another way to do this – don’t do that this time. If you know how to use an <strong>ArrayList</strong>, go ahead and use one of those instead of an array if you want to.)</li>

   <li>Modify the constructor, so that every time a new <strong><sub>HockeyTeam</sub></strong> object is created it will be added to the list of <strong>HockeyTeam</strong></li>

   <li>Add a <strong>public</strong> class method <strong>void listTeams()</strong> which will print all of the teams in the list, one per line. You can simply use <strong>out.println</strong> to print a</li>

  </ol></li>

</ol>

<strong>HockeyTeam</strong>, and the <strong>toString</strong> method you wrote in the Bronze exercise should take care of the rest automatically.

<ol start="2">

 <li>Modify the supplied file <strong>TestLab1Silver</strong><strong><sub>.java</sub></strong> to test your new <strong><sub>HockeyTeam</sub></strong> In two places, marked with <strong>****ADD ONE LINE HERE****</strong>, add a line that will call your <strong>listTeams</strong> class method.</li>

 <li>Run the <strong>java</strong> file to test your modified class. The output should be identical to the Bronze exercise output, except that now it is your <strong><sub>listTeams</sub></strong> method that is doing the printing, not the <strong><sub>main</sub></strong> method.</li>

</ol>

<strong> </strong>

When the list of teams is printed, it should be sorted into descending order according to the number of points each team has, as standings always are.

The built-in method <strong>Arrays.sort(a, 0, n)</strong> will sort elements <strong>a[0] </strong>to <strong>a[n-1]</strong> of <em>any</em> array of objects <strong>a</strong>, provided that a <strong><sub>compareTo</sub></strong> method has been supplied that will compare those objects. You will need the import statement <strong>import java.util.Arrays; </strong>to access this method.

Modify your <strong>HockeyTeam</strong> class to use this method to sort the teams.

<ol>

 <li>Add a <strong>public</strong> instance method <strong>int compareTo(Object other)</strong> which will compare a <strong>HockeyTeam</strong> object to some <strong>other</strong> The type <strong>Object</strong> is a generic type that can refer to any object. Use the ordinary cast <strong>(HockeyTeam)other</strong> to convert it into a <strong>HockeyTeam</strong> object before using it. This method should return a negative number if the <strong>other</strong> team is “larger” and should appear later in the list, a positive number if the <strong>other</strong> team is “smaller” and should appear earlier in the list, and a zero if the two teams are equal and can appear in either order.</li>

 <li>Add the words <strong>implements Comparable</strong> to your class header, just before the <strong>{</strong>. This means “I hereby promise to implement a <strong>compareTo</strong> ” and allows <strong>Arrays.sort</strong> to be used.</li>

 <li>Write a <strong>public</strong> class method <strong>void sortTeams()</strong> which uses the <strong>sort</strong> method to sort the teams in your list of teams into the proper order.</li>

 <li>Modify the supplied file <strong>java</strong> to test your new <strong>HockeyTeam</strong> class. In the places marked with <strong>****ADD ONE LINE HERE****</strong>, add lines that will first call your <strong>sortTeams</strong> class method, and then call your <strong>listTeams</strong> class method.</li>

 <li>Run the <strong>java</strong> file to test your modified class. The output should be identical to the Bronze exercise output, except that now the teams should be listed in descending order according to points.</li>

</ol>

<strong> </strong>


