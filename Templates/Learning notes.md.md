#### 🗓️ Date: <% tp.date.now("YYYY-MM-DD") %> | 🏷️ Tags: 
---
 

---
<%*
if (tp.file.title.startsWith("Untitled")) {
  const newName = await tp.system.prompt("Enter a new name for this file:");
  if (newName) {
    await tp.file.rename(newName);
  } else {
    tp.user.error("You must provide a valid name.");
  }
}
%>
