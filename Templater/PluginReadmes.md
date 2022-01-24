<%*

//for input, copy json lists of your plugins found in .obsidian folder

let inpComm = "[\n  \"customizable-sidebar\",\n  \"homepage\",\n  \"url-into-selection\",\n  \"templater-obsidian\",\n  \"dataview\",\n  \"obsidian-advanced-uri\",\n  \"obsidian-show-file-path\",\n  \"obsidian-code-block-enhancer\",\n  \"obsidian-related-notes-finder\",\n  \"tag-page-preview\",\n  \"find-unlinked-files\",\n  \"note-refactor-obsidian\",\n  \"random-structural-diary-plugin\",\n  \"advanced-toolbar\",\n  \"recent-files-obsidian\",\n  \"extract-url\",\n  \"hotkey-helper\",\n  \"music-code-blocks\",\n  \"obsidian-wikipedia\",\n  \"tag-wrangler\",\n  \"obsidian-command-alias-plugin\",\n  \"nldates-obsidian\",\n  \"obsidian-tabs\",\n  \"darlal-switcher-plus\",\n  \"obsidian-vault-statistics-plugin\",\n  \"reveal-active-file-button\",\n  \"quickadd\",\n  \"obsidian-icon-folder\",\n  \"obsidian-collapse-all-plugin\",\n  \"file-explorer-note-count\",\n  \"obsidian-spotlight\",\n  \"drawio-obsidian\"\n]";


//tR += inpComm;

let comm = JSON.parse(inpComm);

let core = JSON.parse(inpCore);

tR += "## Community:\n---\n\n"

for(let i = 0; i< comm.length; i++)
{
	displayPluginsLink(i, comm);
} 


tR += "## Core:\n---\n\n"

for(let i = 0; i< core.length; i++)
{
	displayPluginsLink(i, core);
} 


function displayPluginsLink(id, pluginArray)
{

tR += "[" + pluginArray[id] + "](obsidian://goto-plugin?id=" + pluginArray[id] + ")\n";
		
		
}
%>
