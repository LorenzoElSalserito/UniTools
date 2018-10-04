XPath Reference
---------------

Resources:
 - http://learn.onion.net/language=en/35426/w3c-xpath
 NB: onion.net currently only supports functions from XPath 1.0;
 
 - https://www.w3schools.com/xml/

Xpath command local test: example here.

### Attribute selection
````
<document name="getit Übungsaufgaben" />

/document/@name
````

### Conditional element selection
````
<document xmlns:xlink="http://www.w3.org/1999/xlink">
  <linkList name="A">
    <document xlink:href="15024" />
    <document xlink:href="15028" />
  </linkList>
  <linkList name="B">
    <document xlink:href="15030" />
    <document xlink:href="15032" />
  </linkList>
</document>

/document/linkList[@name = 'A']/document
````

### Merging character strings
````
<person>
  <lastName>Peter</lastName>
  <firstName>Hans</firstName>
</person>

concat(person/lastName, ', ', person/firstName)
````

### Attribute selection
````
<document name="getit Übungsaufgaben" />

/document/@name
````
