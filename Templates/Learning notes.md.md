#### 🗓️ Date: 16-12-2024 | 🏷️ Tags: [[Learning]]
---
### 📝 Content:
- 

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
