# Basics #
All the layout related definition work is done in **modules.js**

# Module Definition #
Firstly, define all the necessary information for a given module ID in _modules variable, e.g.,_<pre>
...<br>
m301:{l:"m301.html", t:"Module Definition"},<br>
m302:{l:"m302.html", t:"Layout Definition"},<br>
m303:{l:"m303.html", t:"Column Width Definition", c:"green"},<br>
...<br>
</pre>
Wherein:
  * m301 - the module ID
  * l - short for link, defines the url of this module, can point to a static or dynamic resource
  * t - short for title, defines the title of the module when loaded
  * c - short for color, defines the color theme of the module, now "red", "orange", "green", "yellow", "white" are supported with blue as default.

# Layout Definition #
Secondly, define where to put all the modules in _layout variable, e.g.,_<pre>
...<br>
{i:'m301', c:'c1', t:'t3'},<br>
{i:'m302', c:'c2', t:'t3'},<br>
{i:'m303', c:'c3', t:'t3'},<br>
...<br>
</pre>
Wherein:
**i - short for id, the module ID** c - short for column, defines which column this module goes to, c1, c2 or c3
**t - short for tab, defines the tab the module shall appear**

# Column Width Definition #
Lastly, define widths of the columns for the tab in _tabs variable, e.g.,_<pre>
...<br>
t1:{c1:"33.3%",c2:"33.3%",c3:"33.3%",helper:true},<br>
t2:{c1:"200px",c2:"400px",c3:"200px"}<br>
t3:{c1:"50%",c2:"50%",c3:"100%",helper:true},<br>
t4:{c1:"200px",c2:"auto",c3:0}<br>
...<br>
</pre>
Wherein:
  * t2, t3, t4 - tab ID
  * c1, c2, c3 - column widths definitions. Valid combination include:
    * %, %, % - columns will float alongside each other. If the sum is greater than 100%, columns may appear on different rows
    * px, px, px - fixed widths are set likewise. If the sum is greater than 100%, columns may appear on different rows
    * px, "auto", 0 - c1 is given a fixed width, and c2 will fill the rest of the row, and c3 is usually hidden
    * ... (More features can be added by adjusting function HeaderTabClickdefined in myext.js)
  * helper - an optional value, when set to true, will load a helper page above the columns named after tab ID, aka, "t3.html" in this case