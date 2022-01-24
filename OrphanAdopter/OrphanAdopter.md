









## OrphanAdopter
[[OrphanAdopter#OrphanAdopter Readme|Readme]]


```dataviewjs

//================================
//functions:

//delay function
function delay(time) {
  return new Promise(resolve => setTimeout(resolve, time));
}



//
//copy function
//(row item, cbtn click)
function copy(event){

try {

//wacky function workaround:
// - passes data via the element's name

let sender = event.target.name;

let lnk = "[[" + event.target.name + "]]" ;

let preStr = "";
preStr = txtPrepend.value;

let appStr = "";
appStr = txtAppend.value;

lnk = preStr + lnk + appStr;

clipb = "\n" + lnk + clipb;

navigator.clipboard.writeText(clipb);

clipbDisplay.innerHTML = clipb;


con("\n\n" + cbr + "success!\nnew clipboard contents:\n" + clipb + "\n\n");



event.target.style = "width: 200px; height: 35px; background-color: #326369; box-shadow: 2px 2px black;"
delay(85).then(() => event.target.style = "width: 200px; height: 35px; background-color: #3a8dab" )
event.target.innerHTML = "COPIED!"

//
}catch(exc) {
	con(exc.message + " ## ERROR ERROR ERROR ##\N\tError:  - " +exc.toString());
	
}

} //end copy function


//=========================
//con function
function con(str) {

txtCon.value = str + "\n" + txtCon.value;

}//end con


/*
dataviewjs doesn't like a function to print rows, can't do this
	function(pRow) {
	}
*/






//======================================================
//init 
//=================



let conParentDiv = this.container.createEl('div');
conParentDiv.style = 'float: left; ';


let conLbl = conParentDiv.createEl('h5');
conLbl.style = 'margin: 0px; text-align: center;';

conLbl.innerHTML = "Console:";

let tmpEl;



//console line break
let cbr = "\n_______________\n"
//console textarea

let clipb = "";



let txtCon = conParentDiv.createEl('textarea');

txtCon.style = "font-size: 70%; font-family: monospace; float: left; width: 300px; height: 400px; margin: 10px; padding: 5px;";

dv.paragraph("");


let clipbParentDiv = this.container.createEl('div');
clipbParentDiv.style = 'float: left;'

tmpEl = clipbParentDiv.createEl('h5');
tmpEl.style = 'margin: 0px; text-align: center;';

tmpEl.innerHTML = "current clipboard:";

let clipbDisplay = clipbParentDiv.createEl('textarea');

clipbDisplay.style = 'float: left; font-size: 45%; line-height: 85%; font-family: monospace; background-color: gray; width: 300px; height: 400px; margin: 10px; padding: 5px;';
clipbDisplay.innerHTML = "(clipboard is empty)";

tmpEl = this.container.createEl('div');
tmpEl.style = "clear: both;";


let postProccessLbl = dv.el('h3', 'Post-processing:');







//
//precede:

let d3 = await dv.el('div');

tmpEl = d3.createEl('span');
tmpEl.innerHTML = "Precede(before <i>all</i> links):<br><br>";

let txtPrecede = d3.createEl('input');
txtPrecede.style = "width: 85px;"

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



let dclear = await dv.el('div');
dclear.style = "clear: both;";

dv.paragraph("\n\n---");



txtCon.value = "";

con(cbr + "console init...")

navigator.clipboard.writeText("");
con(cbr + "cleared clipboard contents.")


let qConStr = cbr + "querying for orphans...";







//==============================================
//  main query:
//=======
//query all unlinked pages:
var pages = await dv.pages()
.where(p => p.file.inlinks.length == 0)

//.map(p => [p.file.link,
//p.file.folder ]
//); 
//leaving .map() example here for future reference. simpler queries should use it. 

qConStr += "\n" + "found orphans: " + pages.length;

con(qConStr);



tmpEl = this.container.createEl('h2');
tmpEl.innerHTML = 'Queried orphan files:';

tmpEl.style = "margin-bottom: -10px !important;";

tmpEl = this.container.createEl('span')
tmpEl.innerHTML = '<b>' + pages.length + '</b><i> orphans found. </i>';

tmpEl.style = "color: gray; margin: 0px; margin-left: 150px; font-size: 75%;";

dv.span('\n---');

//=========================
//foreach matching page
//=========
for(let i=0; i<pages.length; i++) {

/*
	wacky dataviewjs doesn't like this in a function. just leave it here.

*/

	let p = pages[i];

	//linked name label
	let filN = dv.span("**" + p.file.link + "**");
	
	//folder part
	let filF = dv.span("<br><small>*" + p.file.folder+ "*</small>");



	dv.paragraph("");
	
//cbtn
dv.span("**Append link to Clipboard:**");
dv.el("br")
let cbtn = this.container.createEl('button');



cbtn.name = p.file.path;
cbtn.onClick = copy;
cbtn.style = "width: 170px; font-size: 75%; height: 35px; background-color: DarkSlateGrey;";
cbtn.innerHTML = "Add to clipboard"
cbtn.addEventListener("click", copy);

dv.paragraph("---")

} //end for 



/* test button
 
	let btn = this.container.createEl('button');
	
	btn.addEventListener("click", copy);
	
	btn.name = "btnAsd";
	
	btn.value = "aaa";
*/


//debug output
dv.span("example file:\n" + pages[7]);




```

---








