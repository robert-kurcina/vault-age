### **Quick Regex Reference**

- **Flags:**
  - `g` (Global): Replace all occurrences.
  - `i` (Insensitive): Ignore casing.
  - `m` (Multiline): `^` and `$` match start/end of lines.

### **Common Snippets**

| Goal                       | Find      | Replace   |
| :------------------------- | :-------- | :-------- |
| **Remove Trailing Spaces** | `[ \t]+$` | _(empty)_ |
| **Remove Double Spaces**   | ` +`      | ` `       |
| **Squash Newlines**        | `\n{3,}`  | `\n\n`    |
| **Convert Bullets**        | `^\s*•`   | `-`       |

### **Advanced Examples**

**1. Fix Detached Code Block Languages**
_Moves a language name (e.g., "Bash") sitting on the line above a code block inside the block._

- **Find:** `^[ \t]*([a-zA-Z0-9+#-]+)(?:[ \t]*\n)+([ \t]*` ` `)`
- **Replace:** `$2$1`
- **Flags:** `gm`

---

### **Logic: The "KEEP" Checkbox (🛡️)**

When enabled, the plugin prioritizes **Protecting Content** over replacing it.

1. **Group 1 (`$1`) is Protected:** Anything matched by the first set of parentheses is kept exactly as is.
2. **Everything else is Squashed:** If the match occurs but Group 1 is empty, the entire match is replaced with a single newline `\n`.

**Use Case: Squash newlines, but protect Code Blocks**

- **Find:** `(```[\s\S]*?```)|(\n(?: *\n)+)`
- **Explanation:**
  - Part 1: `(```[\s\S]*?```)` matches code blocks (Group 1) -> **KEPT**.
  - Part 2: `|(\n(?: *\n)+)` matches multiple newlines -> **SQUASHED**.

### **Logic: The "Aa" Checkbox**

When enabled, the final replacement string is converted to **lowercase**.

- **Example:** `# MY TITLE` -> `# my title`
