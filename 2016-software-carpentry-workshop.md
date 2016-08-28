#Welcome to Software Carpentry

We will use this Etherpad to share links and snippets of code, take notes, ask and answer questions, and whatever else comes to mind.

The page displays a screen with three major parts:
    * The left side holds today's no cd
    
    
##Bash Shell Lesson
    
  Please download data for this section:
    
  [shell-novice-data](http://swcarpentry.github.io/shell-novice/data/shell-novice-data.zip)
    
PATH FOR WINDOWS (to use nano inside of git bash)
export PATH="$PATH:~/.swc/lib/make/bin:~/.swc/lib/nano:~/.swc/bin"

     Text for Pipes and Filters

     2012-11-05,deer
     2012-11-05,rabbit
     2012-11-05,raccoon
     2012-11-06,rabbit
     2012-11-06,deer
     2012-11-06,fox
     2012-11-07,rabbit
     2012-11-07,bear


###Bash Shell Notes - 26 Aug 2016 AM

[Useful Website](http://software-carpentry.org/lessons/)

Commands:

	whoami  #tells me my username
	pwd  #present working directory  (directory is the folder you are in)
	ls #list directory contents
	ls -F #gives information about the type of each object in the current directory
	ls -F -a #gives information about the type of ALL objects in the current directory (including hidden directories)
	cd #change directory (move to a new location)
	cd .. #move to a directory about (up one level)
	. #	represents the directory you are in
	.. #represents the directory one level above the one you are in 
	cd #command with no options takes you back to your home directory
	cd ~ #will also take you back to your home directory
	cd - #will take you back to the directory you were previously in
	ctrl l #clear the screen
	clear #also clears the screen
	mkdir #makes a directory
	rm #remove a file (be careful, YOU CAN'T UNDO IT!)!!!!!
	rm -r #remove an entire directory (it will wipe out EVERYTHING below that directory...double check your working directory!)
	rm -r -i #interactive remove; it will take you through each file removal. This is a safer option
	mv #will move a file or directory; can also be used to RENAME a file or directory if you keep it in the same location
	cp #will copy the file; can also rename the file after it is copied
	nano filename.txt #opens the document filename.txt; also CREATES the document filename.txt if it does not already exist
	
**EXAMPLE SYNTAX**:

	mv filename.txt newfilename.txt
	mv filename.txt new/path/filename.txt
	cp filename.txt new/path/newfilename.txt


Pipes and filters:

	wc  (word count) ＃Gives number of lines number of words number of characters  
	wc -w ＃just gives number of words in each file
	wc -l ＃just gives number of lines
	wc -c ＃just gives number of bytes
	wc -m ＃just gives number of characters
  	* ＃wildcard (matches any characters or numbers,  for example *.txt would get all files that end with .txt)
	wc > ＃redirects output to a new location or file
	wc < ＃uses a file as input 
 	| ＃the pipe character,takes the output from one operation and uses it as the input for a subsequent operation
	cat #simply print out content of text file less shows a portion of the file instead of the whole thing at once, can use the spacebar or return to scroll through more of the file
	sort -n #lists files in order of file size
	head -n 3 #file.txt     lists the first 3 lines of the file
	tail -n 3 #file.txt    lists the last 3 lines of the file
	*[AB].txt #finds files with EITHER an A or a B (the brackets work as "either/or" symbols)
	
**Note**: nerds love their "one liners".  There's a whole site devoted to them: 
[bashoneliners](http://www.bashoneliners.com/oneliners/oneliner/popular/)

**Note**: getting lost in the commands? [there you go](http://explainshell.com/ )


Loops:

The "for Loop": the following example shows how to print the first two lines of the two files basilisk.dat and unicorn.dat

	for filename in basilisk.dat unicorn.dat
	do
	head -n 2 $filename #the $ indicates that we are referencing a variable
	done

The following loop copies all of the lines that end with ".dat" and gives new names

	for filename in *.dat
	do
	cp $filename original-$filename
	done

Shortcuts

tab completion: if you start typing and hit tab it will auto complete (or prompt you if there are multiple files that have a similar beginning)

up arrow:  shows the previous command.  You can look through all of your previous commands keep hitting the up arrow

##Python Notes - 26 Aug 2016 PM

Data Exploration in IPython Notebook:

shift -> enter       will run each cell in a python notebook (.ipynb) 

[Website Reference giving a step-by-step of what we did in class](http://swcarpentry.github.io/python-novice-inflammation/01-numpy/)

%whos       magic command in ipython; prints variables and their current values 

Indexing a numpy array:

    data[30,10]       skips the first 30 lines of the data array, and skips the first 10 columns (chooses the point in the 31st line and the 11th column)
    data[0,:]            gives the 0th row (the first row, don't forget numpy is 0-based) and all of the columns
    data[:,0]            gives all of the rows, but only the 0th column

Loops and Stuff in IPython Notebook:

[Website Reference](http://swcarpentry.github.io/python-novice-)

	answer = 5
	for i in range(2):
    answer= answer * 5
	print(answer)

	str="Newton"
	length=len(str)
	counter = 0
	out =''
	for i in range (length):
    counter+=1
    c=str[length-1-i]
    out=out+c
	print (out)

	word = 'negative'
	reverse_word = ''
	for i in range(len(word)-1, -1, -1):
    	reverse_word.append(word[i])
	print(reverse_word)
    
[link](http://swcarpentry.github.io/python-novice-inflammation/03-lists/)

	mylist = []
	str="hello"
	for char in str:
    	mylist.append(char)
	print (mylist)



	string_for_slicing = "Observation date: 02-Feb-2013"
	list_for_slicing = [["fluorine", "F"], ["chlorine", "Cl"], ["bromine", "Br"], ["iodine", "I"], ["astatine", "At"]]
	print(string_for_slicing[-4:])
	print(list_for_slicing[-4:])

	beatles = "In an octopus's garden in the shade"
	print(beatles[::2])

Exercise "Close Enough"

	a=1.0
	b=1.0

	if (print( bool(abs(a-b)<=b*.1) )):
    print("Ouch! My entire life!")
    
how many paths: C

close enough:

	if a >= b-b*.1 and a <= b+b*.1:
    print ("true")
	else: print("false")


[link](http://swcarpentry.github.io/python-novice-inflammation/05-cond/)

##Version Control (Git) Notes - 27 Aug 2016 AM

[Why we need version control](http://www.phdcomics.com/comics/archive.php?comicid=1531)

Set Up:

	git config --global user.name "Your Name"
	git config --global user.email "you@example.com"
	git config --global color.ui "auto"
	git config --list     check what your current set up is
	
For config options for different editors, [see](http://swcarpentry.github.io/git-novice/02-setup/)

	git log #provides list of all committed changes made on files; provides commit/version IDs
	git log --stat #provides extra information on the changes - like which files were changed and how many lines added
	git diff #tracks your changes (before commits)

	git diff HEAD filename.txt #finds the latest changes
	git diff HEAD~1 filename.txt #finds the changes BEFORE the last commit 


[Simple Daily Git Workflow](http://www.slideshare.net/hbalagtas/simple-daily-workflow-with-git)

[Git humor](https://xkcd.com/1597/)

##Python Notes - 27 Aug 2016 PM

[Course Details](http://swcarpentry.github.io/python-novice-inflammation/06-func/)

Rescale function exercises

	def range_overlap(ranges):
    	lowest = 0.0
    	highest = float('inf')
    	for low, high in ranges:
        		lowest = max(lowest, low)
        		highest = min(highest,high)
    		if lowest <= highest:   
        	return lowest, highest
    		else:
        	return 'no overlap'


	def range_overlap(ranges):
    	lowest = float('-inf')
    	highest = float('inf')
    	for low, high in ranges:
        	lowest = max(lowest, low)
        	highest = min(highest, high)
        if lowest >= highest:
            lowest = None
            highest = None
    	return lowest, highest
    	
	assert range_overlap( [(0.0, 1.0)]) == (0.0, 1.0)
	assert range_overlap( [(2.0, 3.0), (2.0, 4.0)]) == (2.0, 3.0)
	assert range_overlap( [(0.0, 1.0), (0.0, 2.0), (-1.0, 1.0)]) == (0.0, 1.0)  
	assert range_overlap( [(0.0, 1.0), (3.0, 4.0)]) == (None, None)
	assert range_overlap([(-10,-1),(-5,5)]) == (-5,-1)


**let the range be specified in either order, so (0,5) is the same as (5,0)**


	def range_overlap(ranges):
    minimums=[]
    maximums=[]
    for range in ranges:
        minimums.append(min(range))
        maximums.append(max(range))

    # return None if there is no overlap    
    if max(minimums) > min(maximums):
        print("no overlap")
        return None
    
    return (max(minimums),min(maximums))


**Resources**

[Pandas](http://www.datacarpentry.org/python-ecology-lesson/)

Cartopy, fiona, rasterio, PySAL Unidata's Online Python training:

[python-online-training](https://unidata.github.io/online-python-training/)

[Matplotlib gallery](http://matplotlib.org/gallery.html)

[SciPy Lectures](http://www.scipy-lectures.org/)