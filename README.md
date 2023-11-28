# python-text-justification
Problem Statement:

Develop a function that takes a paragraph of text and a page width as input and returns an array of left- and right-justified strings. The function should ensure that no words are broken and that the output is formatted to fit the specified page width.

Solution Approach:

To justify text within a specified page width, follow these steps:

1.Split the Paragraph into Words: Divide the paragraph string into individual words using the split() method.

words = paragraph.split()

2.Initialize Temporary Variables: Create a temporary line string to hold the current line being justified and a temporary width integer to track its length.

temp_line = ""
temp_width = 0


3.Iterate through Words: Traverse the list of words one by one.

for word in words:

4.Check Word Fit: Evaluate whether the current word can fit in the temporary line without exceeding the page width.

if temp_width + len(word) + 1 <= page_width:

5.Append Word if Fits: If the word fits, append it to the temporary line and update the temporary width.

temp_line += word + " "
temp_width += len(word) + 1

6.Handle Overflow: If the word doesn't fit, add the current temporary line to the justified lines array, start a new temporary line with the current word, and reset the temporary width.

else:
    justified_lines.append(temp_line.strip())
    temp_line = word + " "
    temp_width = len(word) + 1

7.Handle Last Line: After processing all words, append the final temporary line to the justified lines array.

justified_lines.append(temp_line.strip())

8.Return Justified Lines: Return the array of justified lines.

return justified_lines

This approach ensures that words are not broken and that the output fits the specified page width.
