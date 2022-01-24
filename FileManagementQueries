
### Currently in 02 - Inbox:
```dataview
	TABLE WITHOUT ID 
	
	file.link AS "", 
	
"[Move]" + "(obsidian://advanced-uri?&filepath=" + replace(file.path, " ", "%20") +
"&commandid=file-explorer%253Amove-file)"
AS " ", 
	
	"["	
	+ "Delete"
	+ "]("
	+ "obsidian://advanced-uri?&filepath="
	+ replace(file.path, " ", "%20")
	+ "&commandid=app%253Adelete-file)"
	AS "  "
	
		
	WHERE
		contains(file.folder, "02.02 - ")
		
```

%%AND
contains(file.path, "02") = false %%

### Untitled / empty:

```dataview
	TABLE WITHOUT ID
	
		file.link AS "File",
		
		file.size	AS " size", 
	
	"[Move]" + "(obsidian://advanced-uri?&filepath="
	+ replace(file.path, " ", "%20") +
	"&commandid=file-explorer%253Amove-file)"
		AS " ", 
	
	"["	
	+ "Delete"
	+ "]("
	+ "obsidian://advanced-uri?&filepath="
	+ replace(file.path, " ", "%20")
	+ "&commandid=app%253Adelete-file)"
	AS "  "
	
		
		
		
	FROM ""
	WHERE file.size = 0 OR file.name = "Untitled"
	SORT file.size ASC
```


%%



%%





### Created today:

```dataview
TABLE WITHOUT ID 

file.link AS "file",

string(file.ctime) as "time", 

"[Move]" + "(obsidian://advanced-uri?&filepath=" + replace(file.path, " ", "%20") +
"&commandid=file-explorer%253Amove-file)"
AS " ", 
	
	"["	
	+ "Delete"
	+ "]("
	+ "obsidian://advanced-uri?&filepath="
	+ replace(file.path, " ", "%20")
	+ "&commandid=app%253Adelete-file)"
	AS "  "
	
		
	
	WHERE contains(file.cday, date(today)) 
	
	SORT file.ctime
	
	LIMIT 20
	
```









%%
Other file stuff

```dataview
TABLE WITHOUT ID 

file.link AS "file",

string(file.ctime) as "time", 

"[Move]" + "(obsidian://advanced-uri?&filepath=" + replace(file.path, " ", "%20") +
"&commandid=file-explorer%253Amove-file)"
AS " ", 
	
	"["	
	+ "Delete"
	+ "]("
	+ "obsidian://advanced-uri?&filepath="
	+ replace(file.path, " ", "%20")
	+ "&commandid=app%253Adelete-file)"
	AS "  "
	
		
	
	
	
	WHERE contains(file.cday, date(today)) 
	
	SORT file.ctime
	
```
%%


---
[[01.01 - Home]] 
