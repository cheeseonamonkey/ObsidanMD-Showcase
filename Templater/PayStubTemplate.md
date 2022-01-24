[[01.01 - Home]]

<%*
	
	let inDate = await tp.system.prompt("Date (leave empty for today): ");
	let inAmount = await tp.system.prompt("Amount: ");
	let inHours = await tp.system.prompt("Hours: ");
	
	if(inDate === '' || inDate === null)
	{
		inDate = tp.date.now("MM-DD-YYYY");
	}
	
	tR += "### [[" + inDate + "]] PayStub:\n\n---\n";
	
	tp.file.rename(inDate + " PayStub");
	
	tR += "*$" + inAmount + "*\n";
	
	if(inHours === '' || inHours === null)
	{
		
	}else
	{
		tR += "Hours:" + inHours + "\n\n";
	}
	


%>

---
[[Budget Home]]
[[Stubs Home]]



%>
