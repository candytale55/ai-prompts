# Prompt for Commenting Code and Generating Commit Messages for Self-Contained pages.


Created: **2025-09-14** 

These prompts instruct ChatGPT to take a given HTML/CSS project and produce a fully **commented version with metadata** at the top, explaining the structure, CSS variables, animations, media queries, and other techniques, along with a **ready-to-copy commit message** summarizing improvements, refactors, and added comments. The expected output is a single, self-contained HTML/CSS file with inline explanations and a separate markdown commit message.

They are intended for **self-contained webpages or small projects**, where all HTML, CSS, and optional JavaScript are included in one file, making it easy to document, version-control, and share.


- Tested with ChatGPT FreeTier (ChatGPT5, ChatGPT4)
- Consistently good results, but after commenting several pages, the prompt needs to be given again.
- It is possible that it doesn't divide the commented code from the commit message.

## Condensed Prompt for Commented Code + Commit Message

### Prompt:

```md

I am giving you an HTML/CSS project. Please do the following in one output:

1. Commented Code with Metadata:

- Add an HTML comment block at the top with these fields:

	```
	File: [new file name]
	Old File Name: [current file name]
	Title: [descriptive project title]
	Status: [completion date] (Revisited [current month/year])
	Technologies used: HTML5, CSS3
	Series: [if part of a series]
	Live Demo in CodePen: [leave empty]

	Description:
	[Concise explanation including main concepts, CSS variables, keyframes, animations, media queries, or other notable features.]
	```

- Add descriptive comments inside the code for key sections: explain CSS selectors, properties, HTML structure, variables, animations, and any special techniques.

2. Commit Message in Markdown:

- Provide a commit message that summarizes improvements, refactors, added metadata, and comments. Format like this:

	```
	Refactor [project description] HTML/CSS

	- [First improvement]
	- [Second improvement]
	- ...
	```

Notes:

- Keep metadata and comments consistent with previous projects.
- Always include the “Revisited” note in the status.
- If any field is missing, leave the space blank but keep the structure.
- Ensure commit message is concise, clear, and copy-paste ready.
```


### Long Prompt for Commenting Code and Generating Commit Messages

### Prompt:

```md
I am giving you an HTML/CSS project. Please do the following:

1. Generate enhanced, fully commented code

	* Add a metadata block at the top using HTML comments (`<!-- -->`) with the following fields:

		```
		File: [new file name in lowercase kebab-case].html
		Old File Name: [current file name]
		Title: [descriptive, human-readable project title]
		Status: [Completion date] (Revisited [current month and year])
		Technologies used: HTML5, CSS3
		Series: [optional, if part of a series]
		Live Demo in CodePen: [leave empty for me to fill later]

		Description:
		[Write a concise explanation of the project, including main concepts demonstrated and techniques used. Include notes on variables, media queries, animation, or other special CSS features where relevant.]
		```

	* Inside the code, add descriptive comments for key sections:

		* Explain the purpose of each main CSS selector, property, and HTML structure.
		* Include short notes for variable usage, Bezier curves, keyframes, and any other CSS concepts demonstrated.

2. Generate a commit message ready in Markdown

	* Include the file/project type in the commit title.
	* Highlight what was improved, added, or refactored (metadata, comments, variable usage, media queries, renamed files, etc.)
	* Format the message for easy copy/paste in Markdown, e.g.:

		```md
		Refactor [short project description] HTML/CSS

		- [First change/improvement]
		- [Second change/improvement]
		- ...
		```

Important Notes:

* Always include the “Revisited” note in the status.
* Keep metadata consistent with previous projects.
* Ensure commit messages are short, clear, and actionable.
* If any field (like old file name or series) is missing, leave it blank but keep the structure.
```