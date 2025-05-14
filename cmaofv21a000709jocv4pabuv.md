---
title: "Fixing Text Jumps with \u00A0"
datePublished: Wed May 14 2025 21:14:24 GMT+0000 (Coordinated Universal Time)
cuid: cmaofv21a000709jocv4pabuv
slug: fixing-text-jumps-with-u00a0
tags: typing-effect, space, cursor, text-jumbping, u00a0, non-breaking-space

---

While implementing a blinking cursor effect, I noticed a subtle issue:  
The text would slightly shift left and right whenever th cursor (|) appeared and disappeared.  
  
This happends because when the cursor hidden and replaced with an empty string (““), it no longer takes up any space - causing the entire line to move.

  
✅ The simple fix? Replace ““ with `\u00A0`, a non-breaking space character that still takes up space but remains invisible.

```typescript
<span>{showCursor ? "|":"\u00A0"}</span>
```

> `\u00A0` ensures that even when the cursor disappears, the reserved space remains - so the text stays perfectly still.

* Issue
    

![before](https://cdn.hashnode.com/res/hashnode/image/upload/v1747257159560/0796dd50-d21e-47b8-9068-de44e6088f62.gif align="center")

* Fixed
    

![after](https://cdn.hashnode.com/res/hashnode/image/upload/v1747257171740/3a68f443-c2eb-4c93-9175-400112d51e36.gif align="center")