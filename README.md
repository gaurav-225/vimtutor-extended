This repository stems from my enthusiasm for learning to work effectively in Vim. In the past, I used Vim for simple coding tasks or to edit code after working in modern text editors. 

Now, I’ve committed to learning Vim thoroughly and incorporating it into my daily workflow.

Since I use Obsidian as my primary note-taking app, which supports Vim key bindings, it’s an excellent opportunity to immerse myself in Vim and build consistent practice.

I’ve completed vimtutor and explored YouTube videos to understand how other developers use Vim and to learn from their experiences and tips.

vimtutor is a fantastic starting point for getting familiar with Vim. There’s no single “right” way to learn Vim everyone starts with the basics and adapts the tool to suit their needs.

One setting I’ve found particularly helpful is :set relativenumber. 
This command enables relative line numbering, which displays line numbers relative to the cursor’s position. 
It makes navigating code much faster, especially when combined with commands like 5j to jump five lines down or 3k to move three lines up.

In the sections below, I’ll share the insights and techniques I’ve found most useful for my own Vim journey.
#  Structured Vim Learning

---

##  Chapter 0 – Starting with Vim

* Start Vim with a file:

  ```bash
  vim FILENAME
  ```
* Quit without saving: `:q!`
* Save and quit: `:wq`

Insert text:

* `i` → insert **before cursor**
* `a` → append **after cursor**
* `A` → append at **end of line**
* `o` → open a new line **below**
* `O` → open a new line **above**

---

## Chapter 1 – Moving Around

Movement keys:

```
h → left   l → right
j → down   k → up
```

Word motions:

```
w → next word start
e → end of word
b → back to previous word
0 → beginning of line
^ → first non-blank char
$ → end of line
```

Paragraphs and matching:

```
{ → previous paragraph
} → next paragraph
% → jump between (), [], {}
```

Search:

```
/word → forward search
?word → backward search
n → next match
N → previous match
* → search word under cursor (forward)
/# → search word under cursor (backward)
```

---

##  Chapter 2 – Operators and Motions

Operators work with motions:

```
d → delete
y → yank (copy)
c → change
```

Pattern:

```
OPERATOR [COUNT] MOTION
```

Examples:

```
dw  → delete word
d$  → delete to end of line
2w  → move forward 2 words
3dd → delete 3 lines
yw  → yank word
yy  → yank current line
p   → paste after
P   → paste before
```

Change operator:

```
ce  → change to end of word
c$  → change to end of line
cc  → change whole line
ci" → change inside quotes
ci( → change inside parentheses
ca( → change around parentheses
```

---

## Chapter 3 – Registers & Clipboard

* By default, Vim copies into **internal registers**.
* Named registers: `"a`, `"b`, … `"z`.

Examples:

```
"ayw  → yank word into register a
"ap   → paste from register a
```

System clipboard (if supported):

```
"+y   → yank to system clipboard
"+p   → paste from system clipboard
```

---

## Chapter 4 – Visual Mode

* `v` → characterwise selection
* `V` → linewise selection
* `Ctrl+v` → blockwise selection

Operations with visual selection:

```
y → yank
d → delete
> → indent
< → un-indent
:s/old/new/g → substitute in selected area
```

Select structures:

```
vi" → select inner quotes
va" → select around quotes
vi[ → select inner brackets
va[ → select brackets with content
```

---

## Chapter 5 – Editing Tricks

Replace:

```
rX → replace char with X
R  → replace mode (type over)
xp → swap two characters
ddp → swap two lines
```

Repeating:

```
.  → repeat last change
;  → repeat last f/t/F/T
,  → repeat last f/t/F/T in reverse
```

Counts:

```
8k → move 8 lines up
d3j → delete 3 lines down
50a= <ESC> → insert "=" 50 times
```

---

## Chapter 6 – Searching & Substitution

Search:

```
/word   → forward
?word   → backward
n / N   → next/prev match
```

Substitute:

```
:s/old/new/       → first occurrence in line
:s/old/new/g      → all in line
:%s/old/new/g     → all in file
:%s/old/new/gc    → confirm each
```

Case & highlighting:

```
:set ic     → ignore case
:set noic   → case-sensitive
:set hls    → highlight matches
:noh        → clear highlight once
```

---

## Chapter 7 – Files & Buffers

* Save file as new:
  `:w newFile`
* Read file into current:
  `:r fileName`
* Execute shell command:
  `:!ls`, `:!dir`
* Insert shell output:
  `:r !date`, `:r !ls`
* Select text and write:
  `v motion :w out.txt`

---

## Chapter 8 – Windows, Tabs, Help

Windows:

```
Ctrl+w s → split horizontally
Ctrl+w v → split vertically
Ctrl+w w → switch window
```

Tabs:

```
:tabnew file
:tabn / :tabp
```

Help system:

```
:help
:help w
:help :s
```

---

## Quick Reference

```
ggVG   → select all
zt/zz/zb → align current line top/center/bottom
d/word → delete until word
f( / t( → move to / before next (
;/,     → repeat f/t forward/back
```

# For practice similar to vimtutor

- Download file to practise
```bash
# cmd to open file 
vim vim-tutor-extended-part-A.txt 
vim vim-tutor-extended-part-B.txt 
```

- To view relative number
```
:set number
:set relativenumber
```
---

# Refrence

- [@ThePrimeagen Playlist](https://youtube.com/playlist?list=PLm323Lc7iSW_wuxqmKx_xxNtJC_hJbQ7R&si=1btxj3PdfsfC6u0T)
- [Quickref.me](https://quickref.me/vim)
