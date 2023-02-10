1. Problem that I faced: While making [[carrot_MArkte.excalidraw]] screen, I didn't know how to make scrolll x in css. 
	- Example, I want to style buttons like this: ![[Drawing 2023-01-31 15.42.03.excalidraw]] 
2. Resolution: 
- first, put
```
	display: flex;

    flex-wrap: nowrap;

    overflow-x: auto;

```
	these css code on the parents.
- second, put 
```
flex: 0 0 auto;
```
	this code on child elements.

it will be gonna like this: 

![[Pasted image 20230131155101.png]]



3.  Explaination: 