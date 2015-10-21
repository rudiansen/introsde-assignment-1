## 1st assignment: Introduction to SDE

The application consists of two packages i.e. dao and model. The package dao contains one Java file i.e. "PeopleStore.java". It represents data access for Person object. Basically the Person object is stored in a List and there are two methods setData(List person) and getData() for storing and retrieving the object respectively. The package model contains two Java files, "Person.java" and "HealthProfile.java". These are Plain Old Java Objects (POJO) which represent the object of Person and HealthProfile. The main programs for the application do not have any packages, it resides in the home directory.

Here I will explain how the application works and meets all the requirements asked for this assignment. For the requirements based on Lab 3 (1-4), it is implemented in HealthProfileXMLReader.java file. Basically the program loads an XML file (i.e. people.xml) into memory using DOM interface. XPath is used to retrieve data on the XML document. For getWeight and getHeight methods, it is solved by implementing getWeightByID(personID) and getHeightByID(personID) methods respectively. The Xpath that are used to retrieve the data are 
	```
	/people/person[@id=personID]/healthprofile/weight 
	```
	and 
	```
	/people/person[@id=personID]/healthprofile/height
	```
The methods for printing all people on XML document are getAllPeople() by implementing XPath "
	```
	//person
	```
and printPersonNode(personNode) by selecting data from personNode using getElementsByTagName() method from DOM Element class. The next requirement is solved by implementing method getPeopleByID(personID) with specific XPath 
	```
	/people/person[@id=personID]
	```
The last requirement based on lab 3 is solved by implementing getPeopleByWeight(condition,number) method by using XPath 
	```
	//person[healthprofile/weight condition number]
	```
The parameter given by a user for this method is a single string e.g. ">90", "<80". The application will parse the parameter and split it into condition and number of weight. The requirements based on lab 4 (1-3) are solved as the following: the first requirement is solved by creating people.xsd file. The second requirements i.e. marshalling and un-marshalling to and from XML are solved by HealthProfileReader.java and HealthProfileWriter.java respectively. The last requirement is solved by HealthProfileJSON.java file.

To execute the codes for the requirements based on lab 3 and 4, you can run on your terminal by executing the following command: 
	```
	ant execute.evaluation
	```
If you want to run a specific method, you can type ant target name contained in build.xml file. 
To run getPeopleByID(personID) method, for instance, you can type the following command: 
	```
	ant getPeopleByID
	```
To be able to execute this command, you are expected to have ivy library set on your system.

  