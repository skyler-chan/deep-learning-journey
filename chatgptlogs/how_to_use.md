# How to convert ChatGPT to MD

### Source:

https://github.com/ryanschiang/chatgpt-export

- Copy contents of exportMarkdown.min.js, paste into browser console

`!function(){var n="",e=document.querySelectorAll("[class*='min-h-[20px]']"),t=new Date(new Date(new Date(new Date).toISOString()).getTime()-6e4*(new Date).getTimezoneOffset()).toISOString().slice(0,19).replace("T"," ");n+=`\`${t}\`

`;for(var a=0;a<e.length;a++){var o=e[a].firstChild;if(o){if(o.nodeType===Node.ELEMENT_NODE){var l=o.childNodes;o.className.includes("request-")&&(n+=`_ChatGPT_:
`);for(var d=0;d<l.length;d++){var c,r,i=l[d];i.nodeType===Node.ELEMENT_NODE&&(c=i.tagName,r=i.textContent,"P"===c&&(n+=r+`
`),"OL"===c&&i.childNodes.forEach((e,t)=>{e.nodeType===Node.ELEMENT_NODE&&"LI"===e.tagName&&(n+=`${t+1}. ${e.textContent}\n`)}),"UL"===c&&i.childNodes.forEach((e,t)=>{e.nodeType===Node.ELEMENT_NODE&&"LI"===e.tagName&&(n+=`- ${e.textContent}
`)}),"PRE"===c&&(n+=`\`\`\`
${r}\`\`\`
`),n+="\n")}}o.nodeType===Node.TEXT_NODE&&(n=(n+=`_Prompt_:
`)+o.textContent+`
`+"\n")}}console.save=function(e,t){t=t||"chatgpt.md";var e=new Blob([e],{type:"text/plain"}),n=document.createElement("a"),t=(n.download=t,n.href=window.URL.createObjectURL(e),n.dataset.downloadurl=["text/plain",n.download,n.href].join(":"),new MouseEvent("click",{canBubble:!0,cancelable:!1,view:window,detail:0,screenX:0,screenY:0,clientX:0,clientY:0,ctrlKey:!1,altKey:!1,shiftKey:!1,metaKey:!1,button:0,relatedTarget:null}));n.dispatchEvent(t)},console.save(n,"chatgpt.md")}();`
