# Vim & Neovim Workshop: Master Cheat Sheet

## 1. Survival Kit (The "Don't Panic" Buttons)
| Key | Name | Function |
| :--- | :--- | :--- |
| **`i`** | Insert | Enter **Insert Mode** (start typing like normal). |
| **`Esc`** | Escape | Exit to **Normal Mode** (The panic button). |
| **`:w`** | Write | Save the file. |
| **`:q`** | Quit | Close the file. |
| **`:q!`** | Force Quit | Close without saving (if you made a mess). |
| **`:wq`** | Write & Quit | Save and exit together. |
| **`u`** | Undo | Undo last change (Ctrl+Z). |
| **`Ctrl` + `r`** | Redo | Redo the undo. |

---

## 2. Navigation (Move without a Mouse)
*Keep your fingers on the Home Row!*

| Key | Direction | Description |
| :--- | :--- | :--- |
| **`h`** | Left | Move left. |
| **`j`** | Down | Move down. |
| **`k`** | Up | Move up. |
| **`l`** | Right | Move right. |
| **`w`** | Word | Jump forward to the start of the next word. |
| **`b`** | Back | Jump backward to the start of the previous word. |
| **`0`** | Start | Jump to the **very start** of the line. |
| **`$`** | End | Jump to the **very end** of the line. |
| **`gg`** | Go-Go | Jump to the **top** of the file. |
| **`G`** | Ground | Jump to the **bottom** of the file. |
| **`%`** | Match | Jump between matching brackets `{ }` or `( )`. |

---

## 3. The Grammar of Editing (Verb + Noun)
*Think of these as sentences: "Delete Word" or "Change Line".*

| Command | Action | Logic |
| :--- | :--- | :--- |
| **`dw`** | Delete Word | **d** (Delete) + **w** (Word). |
| **`d$`** | Delete to End | **d** (Delete) + **$** (End of line). |
| **`dd`** | Delete Line | Special command: Deletes the whole line. |
| **`yy`** | Copy Line | **y** (Yank) the whole line. |
| **`p`** | Paste | **p** (Put) text below the cursor. |
| **`x`** | Cut Char | Deletes the single character under the cursor. |
| **`cw`** | Change Word | Deletes word and switches to **Insert Mode**. |
| **`A`** | Append | Jumps to **end of line** and switches to **Insert Mode**. |
| **`o`** | Open | Opens a new line **below** and switches to **Insert Mode**. |

---

## 4. The "Magic Tricks" (Impress Your Friends)
*Use these to show why Vim is faster than VS Code.*

| Command | Name | The Magic |
| :--- | :--- | :--- |
| **`ci"`** | Change Inside Quotes | Deletes everything inside `""` and lets you type. |
| **`ci(`** | Change Inside Parens | Deletes everything inside `()` and lets you type. |
| **`.`** | The Dot | **Repeats** your exact last command instantly. |
| **`V`** | Visual Line | Highlights the whole line (use `j/k` to select more). |
| **`>>`** | Indent | Shifts the line to the right. |
| **`<<`** | Unindent | Shifts the line to the left. |
| **`==`** | Auto-Indent | Fixes the indentation of the current line. |

---

## 5. Search & Replace (Find Anything Instantly)

| Command | Action | Example |
| :--- | :--- | :--- |
| **`/pattern`** | Search Forward | `/function` searches for "function" below cursor. |
| **`?pattern`** | Search Backward | `?import` searches for "import" above cursor. |
| **`n`** | Next Match | Jump to the **next** occurrence. |
| **`N`** | Previous Match | Jump to the **previous** occurrence. |
| **`*`** | Search Word | Searches for the exact word under cursor. |
| **`#`** | Search Word Back | Same as `*` but searches backward. |
| **`:s/old/new/`** | Substitute | Replace first "old" with "new" on current line. |
| **`:s/old/new/g`** | Substitute All | Replace **all** "old" with "new" on current line. |
| **`:%s/old/new/g`** | Global Replace | Replace "old" with "new" in **entire file**. |
| **`:%s/old/new/gc`** | Confirm Replace | Ask confirmation for each replacement. |

---

## 6. Working with Multiple Files

| Command | Action | Description |
| :--- | :--- | :--- |
| **`:e filename`** | Edit | Open another file. |
| **`:bn`** | Buffer Next | Switch to the next open file. |
| **`:bp`** | Buffer Previous | Switch to the previous open file. |
| **`:bd`** | Buffer Delete | Close the current file (buffer). |
| **`:ls`** | List Buffers | See all open files. |
| **`:sp filename`** | Split Horizontal | Open file in horizontal split. |
| **`:vsp filename`** | Split Vertical | Open file in vertical split. |
| **`Ctrl + w + w`** | Switch Window | Jump between split windows. |
| **`Ctrl + w + q`** | Close Window | Close the current split. |
| **`Ctrl + w + =`** | Balance Splits | Make all splits equal size. |

---

## 7. Text Objects (The Real Power of Vim)
*These let you select and manipulate entire structures.*

| Command | What it Selects | Example |
| :--- | :--- | :--- |
| **`ciw`** | Change Inner Word | Changes the word under cursor (no spaces). |
| **`caw`** | Change A Word | Changes word + surrounding space. |
| **`ci"`** | Change Inside Quotes | Changes text inside `"..."`. |
| **`ca"`** | Change Around Quotes | Changes text + the quotes themselves. |
| **`ci(`** | Change Inside Parens | Changes content inside `(...)`. |
| **`ci{`** | Change Inside Braces | Changes content inside `{...}`. |
| **`ci[`** | Change Inside Brackets | Changes content inside `[...]`. |
| **`cit`** | Change Inside Tag | Changes content inside HTML/XML tags. |
| **`das`** | Delete A Sentence | Deletes entire sentence. |
| **`dap`** | Delete A Paragraph | Deletes entire paragraph (blank line separated). |
| **`yip`** | Yank Inner Paragraph | Copies the paragraph without blank lines. |

*Works with `d` (delete), `c` (change), `y` (yank/copy), `v` (visual select).*

---

## 8. Macros (Record & Replay Actions)

| Command | Action | Description |
| :--- | :--- | :--- |
| **`qa`** | Record Macro | Start recording actions into register `a`. |
| **`q`** | Stop Recording | Stop the macro recording. |
| **`@a`** | Play Macro | Execute the macro stored in register `a`. |
| **`@@`** | Repeat Last Macro | Run the last macro again. |
| **`10@a`** | Repeat 10 Times | Run macro `a` ten times. |

**Example Workflow:**
1. `qa` - Start recording
2. `I// ` - Add comment at start of line
3. `Esc` - Back to normal mode
4. `j` - Move down
5. `q` - Stop recording
6. `100@a` - Comment 100 lines instantly!

---

## 9. Cool Advanced Commands

| Command | Action | Why It's Cool |
| :--- | :--- | :--- |
| **`zz`** | Center Screen | Moves current line to center of screen (great for focus). |
| **`zt`** | Top of Screen | Moves current line to top of screen. |
| **`zb`** | Bottom of Screen | Moves current line to bottom of screen. |
| **`Ctrl + o`** | Jump Older | Jump back to previous cursor position (like browser back). |
| **`Ctrl + i`** | Jump Newer | Jump forward in jump history. |
| **`gf`** | Go to File | Opens the file path under cursor. |
| **`gd`** | Go to Definition | Jump to definition of variable/function under cursor. |
| **`gx`** | Open URL | Opens URL under cursor in browser. |
| **`~`** | Toggle Case | Switch between UPPER/lower case. |
| **`gu`** | Lowercase | Make selection lowercase (use with motion: `guw`). |
| **`gU`** | Uppercase | Make selection uppercase (use with motion: `gUw`). |
| **`J`** | Join Lines | Merges the line below with current line. |
| **`xp`** | Swap Characters | Swaps character under cursor with next one. |
| **`ddp`** | Swap Lines | Moves current line down by one. |
| **`yyp`** | Duplicate Line | Copies line and pastes it below. |
| **``.`** | Last Edit Position | Jump to the exact spot of your last edit. |
| **`:earlier 5m`** | Time Travel Back | Undo to 5 minutes ago (yes, this exists!). |
| **`:later 2m`** | Time Travel Forward | Redo to 2 minutes in the future. |
| **`Ctrl + a`** | Increment Number | Adds 1 to number under cursor (5 → 6). |
| **`Ctrl + x`** | Decrement Number | Subtracts 1 from number under cursor (5 → 4). |
| **`:%!sort`** | Sort File | Sorts entire file alphabetically (uses Unix sort). |
| **`:!command`** | Run Shell Command | Execute any terminal command (`:!ls`, `:!python %`). |
| **`:read !command`** | Insert Command Output | Puts command output into file (`:read !date`). |
| **`:%norm A;`** | Execute on All Lines | Adds `;` to end of every line in file. |
| **`qa` ... `q` ... `100@a`** | Repeat 100x | Records a macro and repeats it 100 times. |

---

## 10. Visual Mode Tricks

| Command | Action | Description |
| :--- | :--- | :--- |
| **`v`** | Visual Character | Select character by character. |
| **`V`** | Visual Line | Select entire lines. |
| **`Ctrl + v`** | Visual Block | Select rectangular blocks (column editing!). |
| **`o`** | Switch End | In visual mode, jump to other end of selection. |
| **`gv`** | Re-select | Re-selects the last visual selection. |

**Visual Block Magic:**
1. `Ctrl + v` - Enter visual block mode
2. `jjj` - Select 3 lines down
3. `I// ` - Insert `// ` at start
4. `Esc` - Apply to all selected lines!

---

## 11. Marks & Bookmarks

| Command | Action | Description |
| :--- | :--- | :--- |
| **`ma`** | Set Mark | Creates bookmark `a` at current position. |
| **`` `a ``** | Jump to Mark | Jump to exact position of mark `a`. |
| **`'a`** | Jump to Line | Jump to the line of mark `a`. |
| **`:marks`** | List Marks | Show all bookmarks. |
| **`` `. ``** | Last Edit | Jump to position of last edit. |
| **`` `` ``** | Last Jump | Jump back to previous location. |

---

## 12. Registers (Copy/Paste on Steroids)

| Command | Action | Description |
| :--- | :--- | :--- |
| **`"ayy`** | Yank to Register | Copy line to register `a`. |
| **`"ap`** | Paste from Register | Paste from register `a`. |
| **`:reg`** | Show Registers | Display all register contents. |
| **`"0p`** | Paste Last Yank | Paste from yank register (ignores deletes). |
| **`"+y`** | Copy to Clipboard | Copy to system clipboard. |
| **`"+p`** | Paste from Clipboard | Paste from system clipboard. |

---

## 13. The Nuclear Options (When Things Go Wrong)

| Command | Action | When to Use |
| :--- | :--- | :--- |
| **`:w !sudo tee %`** | Save as Root | When you forgot to open with sudo. |
| **`:e!`** | Reload File | Discard all changes and reload from disk. |
| **`:recover`** | Recover Crash | Restore from swap file after crash. |
| **`u` ... `u` ... `u`** | Mass Undo | Spam undo until you find sanity. |
| **`:earlier 1h`** | Time Travel | Go back 1 hour in undo history. |
| **`Ctrl + z`** | Suspend | Puts Vim in background (type `fg` to return). |

---

## 14. Final Boss Commands (Show Off Mode)

| Command | What It Does | Mind Blown Yet? |
| :--- | :--- | :--- |
| **`:g/pattern/d`** | Global Delete | Delete all lines matching pattern. |
| **`:v/pattern/d`** | Inverse Delete | Delete all lines NOT matching pattern. |
| **`:g/TODO/t$`** | Copy All TODOs | Copy all TODO lines to end of file. |
| **`:%norm @a`** | Macro on All Lines | Run macro `a` on every line. |
| **`:sort u`** | Sort + Unique | Sort file and remove duplicates. |
| **`ggVG`** | Select All | `gg` (top) + `V` (visual line) + `G` (bottom). |
| **`=G`** | Auto-Indent File | Fix indentation from cursor to end of file. |
| **`gg=G`** | Auto-Indent All | Fix indentation of entire file. |
| **`:retab`** | Convert Tabs/Spaces | Convert tabs to spaces (or vice versa). |

---

## 15. Cheat Code: The Dot Command (`.`)
The **`.`** (dot) repeats your last change. This is the most powerful command in Vim.

**Example:**
1. `cw` + type `hello` + `Esc` (Change word to "hello")
2. `j` (Move down)
3. `.` (Repeat: changes next word to "hello")
4. `j.j.j.` (Keep changing words)

**Pro Tip:** Always think "Can I repeat this with dot?" when editing.

---

## 16. Neovim Specific (If You've Upgraded)

| Command | Action | Description |
| :--- | :--- | :--- |
| **`:checkhealth`** | Health Check | Diagnose Neovim setup issues. |
| **`:Telescope find_files`** | Fuzzy Finder | Find files instantly (requires Telescope plugin). |
| **`:TSUpdate`** | Update Treesitter | Update syntax parsers (requires Treesitter). |
| **`:LspInfo`** | LSP Status | Check language server connection. |
| **`:Mason`** | Package Manager | Install LSP servers, linters, formatters. |

---

## 17. The Philosophy: Thinking in Vim

Vim isn't about memorizing commands. It's about **composing** them:

- **Operators**: `d` (delete), `c` (change), `y` (yank)
- **Motions**: `w` (word), `$` (end), `i"` (inside quotes)
- **Counts**: `3` (repeat 3 times)

**Examples:**
- `d3w` = Delete 3 words
- `c2j` = Change current line + 2 lines below
- `y4k` = Yank current line + 4 lines above

Once you learn the "grammar", you can create commands on the fly.

---

## Resources

- **Interactive Tutorial**: Run `vimtutor` in terminal (30 min crash course)
- **Vim Golf**: Practice efficiency at [vimgolf.com](https://vimgolf.com)