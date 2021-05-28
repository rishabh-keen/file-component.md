<h1 align=center> What is File Component and How we can use it </h1>
<p align=center> [Code Pic](https://github.com/rishabh-keen/photos.md/blob/master/1.png) </p>
<p align=center> [Output Log](https://github.com/rishabh-keen/photos.md/blob/master/2.png) </p>
<p align=center> [POM File](https://github.com/rishabh-keen/photos.md/blob/master/pom) </p>

<p align=center>The File component provides access to file systems, allowing files to be processed by any other Camel Components or messages from other components to be saved to disk. It supports both consumer and producer. </p>

<h3 align=center> This is code of File Component </h3> 

|***SN***| ***Code***  |    ***DESCRIPTION***  |
| :---: | :------: | :-----: |
|:one:| **route id="simple-route"** <br/> | We can use multiple Route IDs in a CamelContext project.  But it should be noted that the name of each Route ID should be different. |
|:two:| **from id="route-timer" uri="file:/home/rishabh/Downloads/input?noop=true&amp;include=.*.csv&amp;delay=10000&amp;sortBy=reverse:file:modified"/>** <br/> | In the uri option, we will write the file component next.  Then we will give the path of our producer. <br> **noop -** If the condition of our noop is true then the file will only be copied.  If the condition of our noop is false then the file will be deleted from the producer and go to the consumer. <br> **include -** And include means.  We can also define our type in which type of file we want to send. <br> **delay -** And we are using delay because in how long will our file go? <br> **&amp -** we are using & amp because we can use multiple components on the same line. <br> **sortBy -** sortBy we are doing shorting of files.|
|:three:| **log id="route-log" message=">>> Hello"/>** <br/> | And we are using the log before receiving the file.  Therefore, just before the file is received, our log will be printed and the message will be Hello. |
|:four:| **to id="t01" uri="file:/home/rishabh/Downloads/output?doneFileName=${file:name}.done"/>** <br/> | In the option, we give the path where we want the file. |
|:five:| **log id="route-log" message=">>> headers : ${headers}"/>** <br/> | And in this header log our header log is generated such as in the output folder from where we are sending the file and the path of the input folder where the file is going. |

