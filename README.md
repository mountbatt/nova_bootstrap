# nova_bootstrap
 This Nova Extension adds Bootstrap 5 auto-completion

### Just a note for future updates how to get the current classnames from Bootstrap CSS:
 
1. Copy the text from https://getbootstrap.com/docs/5.3/dist/css/bootstrap.css or any other version
2. Isolate class names by replacing `\s\.([-a-z0-9]+)` with `\n©\1©\n` thus placing each class name on a line of its own with unique delimiters
3. Removing all content except the isolated classes by replacing
`(?<!©)(?:(?!©).)*(?!©)` with nothing
4. Removing the delimiters by replacing `©(.+)©` with `\1`
5. Paste all lines in https://dedupelist.com/ and check "Sort result" to remove duplicates and sort the classnames in alphabetical order
6. Copy back to your editor and remove some junk at the start of the file (Numbers)
7. Use `^(.+)$` and replace it with `"\1",`
8. For minification you can replace the linebreak, if you wish.
9. Copy paste it into `/Scripts/main.js` between `let tags = [ ... ]`

Thanks to https://github.com/zkarj735 for your inspiration!