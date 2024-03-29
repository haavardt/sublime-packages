# HTMLBeautify v0.81
## SublimeText (version 2 & 3)
- (Inspired by fhtml.pl by John Watson)
- by Ross A. Reyman
- 14 April 2014
- url:			[http://reyman.name/](http://reyman.name/)
- e-mail:		ross[at]reyman[dot]name

---

A plugin for [Sublime Text ](http://sublimetext.com/), that formats (indents) HTML source code.
It makes code easier for humans to read.

---

## Back to Version 0.7
An error in the indentation logic occurred when updating to version 0.8. I am rolling this back to 0.7 (and renaming this to 0.81 until I have time to investigate this further.

## Notes
- This script assumes an effort has been made by the user to expand tags to different lines. This script will **not**  automatically expand minimized/compressed code—it will only try to “clean-up” code that needs to be re-indented
- Currently, this script chokes a bit with inline comments.
	- For example:

		`<div class="something"> <!-- HTMLBeautify will ignore this line since it is inline -->`
	- So, a workaround is to keep comments on their own lines:

		`<!-- this comment is ok -->`
    
        `<div class="something">`

        `<!-- this comment is ok too -->`
	- (TODO: Fix this!)

- This script uses `\t` characters to create indentation levels and spacing—ST appears to honor whether the user prefers spaces or tabs in ST settings and adjusts accordingly.
- Use `tag_pos_inline` setting to define tags that _might_ appear on one line.
- Windows Users: You **must** restart Sublime Text to complete the installation.

## Installation (Package Control)
If you have [Package Control](http://wbond.net/sublime_packages/package_control/installation) installed in Sublime Text:

- Open the Command Palette (Tools > Command Palette…)
- Search for and choose "Package Control: Install Package" (give it a few seconds to return a list of available packages)
- Search for "HTMLBeautify" and install.
- Windows users will **need** to restart Sublime Text to finish the installation.

## Installation (Manual)
- Download the zip, re-name resulting folder to: `HTMLBeautify`, then put the folder into your Sublime Text Packages folder.

## Usage
- Open a file containing HTML.
- Select HTML code you want to beautify. (If no selection is made the plugin will run on the whole file.)
- Use `super+alt+f` on OS X (`ctrl+alt+f` on Windows) to run HTMLBeautify—or use HTMLBeautify from the Edit menu.
- You can test the script with `HTMLBeautifyTest.html`: an HTML file with wacky indenting so you to see how this script works.

## Settings
You can configure which tags should be processed with this script:

- `ignored_tag_opening` : What are the opening tags that tell the script to ignore HTMLBeautify formatting?
- `ignored_tag_closing` : What are the closing tags that tell the script to resume HTMLBeautify formatting?

- `tag_indent` : If one of these opening tags is encountered, the contents (next line) will be indented by one level.
- `tag_unindent` : If one of these closing tags is encountered, the next line will be un-indented one level.
- `tag_unindent_line` : If one of these closing tags is encountered, this line is un-indented one level.

- `tag_pos_inline` : These are special “one line” tags that open and close on the same line, so indenting should be ignored.

- `remove_extraline` : Set true to remove empty line.

## Disclaimer
This script has been tested for basic HTML coding situations, but your mileage may vary—use with caution if using this in a production environment. (Please report bugs or contribute corrections to the script!) Although the script does not remove or modify code directly (it only attempts to adjust indentation levels), be sure to test this script throughly to make sure it works as expected! The author is not responsible for any bugs that might be introduced to your HTML. :)

