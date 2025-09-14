# Code comments and README Generator for Simple Projects

_Created on_ **2025-08-28**

## Overview:

**Purpose / Description:**  
Generates in-line comments for a **small frontend project** and produces a README based on the code.

**Intended Use Case:**  
Best suited for small, single-file apps or toy projects where quick documentation is needed. 

**Compatibility:**  
- Works well with: [Claude](https://claude.ai/) (Sonet4, FreeTier)

**Example Workflow:**  
1. Give the assistant the first & second instructions and provide the assistant with the code.  

2. After the assistant comments the code to your liking ask for a README based on the commented code.


## PROMPTS:

### Prompt 1 - HTML & CSS Comments:

```markdown 
I'm going to give you the HTML and CSS files of a project. I want you to add brief inline comments that:
- Separate major sections with clear headers
- Indicate functionality when it's essential for understanding the project structure
- Use a consistent commenting style throughout
- Focus on making navigation easier rather than explaining obvious code
- If the HTML file is missing any standard declarations or meta tags (DOCTYPE, lang="en", charset="UTF-8", viewport), please add them.
- Add accessibility improvements through attributes only - no new HTML elements or structural changes, just enhance existing tags with aria-labels, alt text, and similar attributes. 

The goal is to make the codebase easier to navigate and understand at a glance.
```
```markdown
   [Include both files here. If your JavaScript (or similar) is tested/safe you can send it too. Untested code goes in a following prompt]
```

### Prompt 2 - JavaScript Comments:

```markdown
Now I need you to comment the JavaScript file with two specific requirements:

1. **Descriptive comments**: Add comprehensive section headers and functionality explanations using the same organization style as the previous files

2. **Comment out crash-prone code**: Use /* */ block comments to disable any sections that require:
   - API connections
   - External dependencies that may not be installed
   - Environment variables
   - Network requests
   - Any other external resources

Add safe placeholder functions where needed so the app runs without crashing during development.
```
```markdown
   [Include JS file]
```

### Prompt 3 - README:

```markdown
Please create a concise README.md for this project that includes:
- **Description**: What the app does (maximum 2 paragraphs)
- **Status**: Mark as "[Work in Progress | Completed], [Date]"
- **Technologies**: List all technologies and dependencies used
- **Format**: Clean, professional markdown suitable for GitHub
```

## Suggestions:

1. **Add example snippets** if you want a very specific commenting style
2. **Specify priority levels** if some sections are more critical than others
3. **Mention target audience** (e.g., "for junior developers" vs "for experienced team")


