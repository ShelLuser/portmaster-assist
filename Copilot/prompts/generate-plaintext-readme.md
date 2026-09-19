Prompt version: 1.3

Task:

Create a plaintext version of the projects README.md file which doesn't use any Markup.

Requirements:

- Do **not** make *any* changes to the original README.md file.
- Name the new file README.txt, overwrite the file if it already exists.
- Wrap lines at 78 columns to ensure readability on (FreeBSD) consoles.
- Format the new document for comfortable reading on a (FreeBSD) console.
- Make sure to use * characters when you're copying bullet lists.
- Don't copy any lines which have been ~~crossed out~~ using markup.
- Also don't include any links within the text of the README itself.
- There are one (or more) image links used in the README, don't include these in the new file.
  - Check for any text which specifically refers to the image(s), omit those line(s) from the new file.
- Use double quotes for codeblocks. For example: "devel/git" instead of `devel/git`.
- Use // for the header sections (example: "// About").
- Add a new "References" section at the end of the new document with a summary of all the used links.
  - Only include links which are relevant to the project.
