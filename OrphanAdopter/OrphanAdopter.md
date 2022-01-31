


## OrphanAdopter
[[OrphanAdopter-Readme|Readme]]


```dataviewjs




//=================
//functions:
//

//save function
function save(event) {

let sender = event.target;

sender.innerHTML = "SAVED!"

sender.style = "box-shadow: 4px 3px black; width: 40%; height: 45px; float:right; background-color: purple;"

storeStr = localStorage.getItem("store1");

storeStr += "," + sender.name

localStorage.setItem("store1", storeStr);

con("saved to store: " + sender.name)
con(cbr)
con("\n")

}//end save

//delay function
function delay(time) {
  return new Promise(resolve => setTimeout(resolve, time));
}

//clear store function
function clrStore() {
store1 = ""
localStorage.setItem("store1", "");

con("cleared store.")
con(cbr)
cbr("\n")

}


//
//copy function - adds link
//
function copy(event){

try {


//passes data via the element's name i guess?
let sender = event.target.name;

let lnk = "[[" + event.target.name + "]]"

let precedeStr = "";
precedeStr = txtPrecede.value;

let preStr = "";
preStr = txtPrepend.value;

let appStr = "";
appStr = txtAppend.value;

lnk = preStr + lnk + appStr;

clipb = "\n" + lnk + clipb;

navigator.clipboard.writeText(clipb);

clipbDisplay.innerHTML = clipb;


con("\n\n" + cbr +  "success!\nnew clipboard contents:\n" + clipb + "\n\n");



event.target.style = cbtnStyleStr + "background-color:  #3a8dab; box-shadow: 4px 3px black;"

event.target.innerHTML = "COPIED!"

//
}catch(exc) {
	con(exc.message + " ## ERROR ##\n\tError:  - " +exc.toString());
	
}
} //end copy function


//=========================
//con function
function con(str) {

txtCon.value = str + "\n" + txtCon.value;

}//end con





//===================================
//init 
//=================

const cbtnStyleStr = "width: 40%; font-size: 75%; height: 45px; float: left; background-color: DarkSlateGrey;"; 

if(localStorage.getItem("store1") === null) {
localStorage.setItem("store1", "");
}

let conParentDiv = this.container.createEl('div');
conParentDiv.style = 'float: left; ';

let conLbl = conParentDiv.createEl('h5');
conLbl.style = 'margin: 0px; text-align: center;';

conLbl.innerHTML = "Console:";

let tmpEl;

let storeStr;


//console line break
let cbr = "\n_______________\n"

//
//console 

let clipb = "";

let txtCon = conParentDiv.createEl('textarea');

txtCon.style = "font-size: 70%; font-family: monospace; float: left; width: 300px; height: 400px; margin: 10px; padding: 5px;";

dv.paragraph("");

con("## console init ##")
con('\n')

let clipbParentDiv = this.container.createEl('div');
clipbParentDiv.style = 'float: left;'

tmpEl = clipbParentDiv.createEl('h5');
tmpEl.style = 'margin: 0px; text-align: center;';

tmpEl.innerHTML = "current clipboard:";

let clipbDisplay = clipbParentDiv.createEl('textarea');

clipbDisplay.style = 'float: left; font-size: 55%; line-height: 85%; font-family: monospace; background-color: gray; width: 300px; height: 400px; margin: 10px; padding: 5px;';
clipbDisplay.innerHTML = "(clipboard is empty)";








let dclear = await dv.el('br');
dclear.style = "width: 100%; clear: both;";

let postProccessLbl = dv.el('h3', 'Post-processing');


//
//precede:

let d3 = await dv.el('div');

tmpEl = d3.createEl('span');
tmpEl.innerHTML = "Precede(before <i>all</i> links):<br><br>";

let txtPrecede = d3.createEl('input');
txtPrecede.style = "clear: both; width: 85px;"

tmpEl = d3.createEl('span');
tmpEl.style = "font-size: 95%;"
tmpEl.innerHTML = "<small><br>↑<br><a>Link</a><br><a>Link</a></small>";

d3.style = "border: 2px solid black; width: 310px; text-align: center; padding: 4px; margin: 5px; font-size: 90%; clear: both;";


//
//prepend link text box:

let d1 = await dv.el('div');

tmpEl = d1.createEl('span');
tmpEl.innerHTML = "Prepend (<i>before</i> link):<br><br>";

let txtPrepend = d1.createEl('input');
txtPrepend.style = "width: 50px;"

tmpEl = d1.createEl('span')
tmpEl.innerHTML = "←<a>Link</a>";










//
//append link text box:

let d2 = await dv.el('div');

d1.style =
"border: 2px solid black; float: left; width: 150px; text-align: center; padding: 4px;  margin: 5px; font-size: 90%";

d2.style =
"border: 2px solid black; float: left; width: 150px; text-align: center; padding: 4px; margin: 5px; font-size: 90%;";



tmpEl = d2.createEl('span');
tmpEl.innerHTML = "Append (<i>after</i> link):<br><br>";




tmpEl = d2.createEl('span')
tmpEl.innerHTML = "<a>Link</a>→";
let txtAppend = d2.createEl('input');
txtAppend.style = "width: 50px;"

let clrBtn = this.container.createEl('button');
clrBtn.style = "clear: both; height: 40px; width: 70%;";
clrBtn.addEventListener("click", clrStore);  
clrBtn.innerHTML= "clear store"
navigator.clipboard.writeText("");
con("cleared clipboard contents.");

dclear = await dv.el('div');
dclear.style = "clear: both;";

dv.el('br');
dv.el('p', '---');

let storeEnabled = false;

if (typeof(Storage) !== "undefined") {
	storeEnabled = true;
} else {
	storeEnabled = false;
}

con("store enabled: " + storeEnabled);

let store1 = localStorage.getItem("store1")


con('store: ' +  store1);

con(cbr);
con("querying for orphans...") 




//==============================================
//  main query:
//=======
//query all unlinked pages:
var pages = await dv.pages()
.where(p => p.file.inlinks.length == 0)



con("found orphans: " + pages.length) 

con(cbr)



tmpEl = this.container.createEl('h2');
tmpEl.innerHTML = 'Queried orphan files:';

tmpEl.style = "margin-bottom: -10px !important;";

tmpEl = this.container.createEl('span')
tmpEl.innerHTML = '<b>' + pages.length + '</b><i> orphans found. </i>';

tmpEl.style = "color: gray; margin: 0px; margin-left: 150px; font-size: 75%;";

dv.el('p', '---');


storeStr = localStorage.getItem("store1");
let storeArr = storeStr.split(',')

con(storeArr.length)

//======================
//foreach matching page
//======
for(let i=0; i<pages.length; i++) {
/*
	wacky dvjs doesn't all like this in a function. leave it here.
*/

	let p = pages[i];

	//linked name label
	let filN = dv.span("**" + p.file.link + "**");
	
	//folder label underneath 
	let filF = dv.span("<br><small>*" + p.file.folder+ "*</small><br>");




//cbtn
let cbtn = this.container.createEl('button');
cbtn.name = p.file.path;

	cbtn.style = cbtnStyleStr;
cbtn.innerHTML = "Add link to clipboard"
cbtn.addEventListener("click", copy);









//sbtn
let sbtn = this.container.createEl('button');
sbtn.name = p.file.name;

sbtn.innerHTML = "Save"



sbtn.style = cbtnStyleStr + "; float:right; ";

for(let ii=0; ii<storeArr.length; ii++) { 

con('')

if(storeArr[ii] === p.file.name) {

con("SAVE MATCH")
//stored match
tmpEl = this.container.createEl('span');
tmpEl.innerHTML = 'SAVED!';
tmpEl.style = "background-color: purple; padding: 8px; border: 1px solid orange;";




 

} 
}//end search iterator


sbtn.addEventListener("click", save);

tmpEl = this.container.createEl('span')
tmpEl.innerHTML = '<br><hr>'
tmpEl.style = "clear: both;"

} //end for 


```

---
 
