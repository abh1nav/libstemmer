libstemmer
==========

Mavenized version of the Snowball libstemmer distribution.

Source taken from: http://snowball.tartarus.org/

Install
-------

Install the library into your local Maven cache:

```
git clone http://github.com/abh1nav/libstemmer.git
cd libstemmer
mvn clean install
```

Depend
------
  
And add it to your dependencies list in `pom.xml`:
  
```
<!-- libstemmer -->
<dependency>
    <groupId>org.tartarus.snowball</groupId>
    <artifactId>libstemmer</artifactId>
    <version>1.0.0</version>
</dependency>
```
To include it  without building it before you can add the repository  http://raisercostin.googlecode.com/svn/maven2/org/tartarus/snowball/libstemmer/1.0.0/
```
  <repositories>
		<repository>
			<id>org.raisercostin.public.releases</id>
			<url>http://raisercostin.googlecode.com/svn/maven2</url>
			<snapshots>
				<enabled>false</enabled>
			</snapshots>
		</repository>
	</repositories>
```

Use
---
  
```java
SnowballStemmer stemmer = new englishStemmer();
String sentence = "I'm liking libstemmer";
for(String word : sentence.split(" ")) {
    stemmer.setCurrent(word);
    stemmer.stem();
    System.out.println(stemmer.getCurrent());
}
```
  
Output:
  
```
I'm
like
libstemm
```
  
License
-------

All the software given out on this Snowball site is covered by the BSD License (see http://www.opensource.org/licenses/bsd-license.html ), with Copyright (c) 2001, Dr Martin Porter, and (for the Java developments) Copyright (c) 2002, Richard Boulton.

Essentially, all this means is that you can do what you like with the code, except claim another Copyright for it, or claim that it is issued under a different license. The software is also issued without warranties, which means that if anyone suffers through its use, they cannot come back and sue you. You also have to alert anyone to whom you give the Snowball software to the fact that it is covered by the BSD license.
