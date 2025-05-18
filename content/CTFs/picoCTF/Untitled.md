---
created: 2025-05-14T22:21
updated: 2025-05-18T14:11
---
<%*
let title = tp.file.title;
if (title.startsWith("Untitled")) {
  title = await tp.system.prompt("Challenge Title:", null, false, true);
  await tp.file.rename(title);
}

const ctf = await tp.system.prompt("CTF Name (e.g., picoCTF, HTB)");
const category = await tp.system.prompt("Category (Web, Crypto, etc.)");
const difficulty = await tp.system.prompt("Difficulty (Easy, Medium, Hard)");
const points = await tp.system.prompt("Points (e.g., 100)", "0");
const status = await tp.system.suggester(["Solved", "In Progress", "Unsolved"], ["Solved", "In Progress", "Unsolved"]);
const flag_format = await tp.system.prompt("Flag Format (e.g., picoCTF{...})");
const date = tp.date.now("YYYY-MM-DD");

-%>
---
title: "<%* tR += title %>"
ctf: "<%* tR += ctf %>"
challenge: "<%* tR += title %>"
category: "<%* tR += category %>"
difficulty: "<%* tR += difficulty %>"
points: <%- points %>
status: "<%* tR += status %>"
flag_format: "<%* tR += flag_format %>"
date: <%- date %>
tags:
  - ctf
  - <%* tR += category.toLowerCase() %>
---

# <%* tR += title %>

<!-- Write your solution, methodology, and flag here -->
