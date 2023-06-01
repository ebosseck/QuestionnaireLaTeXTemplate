# QuestionnaireLaTeXTemplate
LaTeX template for (interactive) questionnaires

## Usage

Clone this repository and edit the questionnaire to your liking.

### Print mode & Interactive mode

In order to toggle whether it should be possible to fill out the from on your computer before printing is currently done by switching the input in lines 26 and 27.

In order to create a print-only questionnaire, use ```\input{res/definitions.tex}```, if you want to edit fields on the computer, replace this line with ```\input{res/definitions_interactive.tex}```

### Title, Subtitle and Watermark

In order to set the title of your questionaire, use the following command:

```
\setTitle{Your Study Title Here}
```

In order to set the watermark, use the following on the first page the new watermark should appear:

```
\SetWatermarkText{\textbf{YOUR WATERMARK}}
```

Finally, to set the subtitle of the part of the study, use the following on the first page of each part:

```
\setPart{Your Subtitle Here}
```

### Checkbox Questions

Checkbox questions are usually either simple yes / no questions or multiple choice questions

#### Compact
``` 
\begin{checkboxQuestionsCompact}{\parbox[c][7.5mm]{\textwidth}{My choice is:}}{12cm}{3}
	\checkboxQuestion{Option 1}
	\checkboxQuestion{Option 2}
	\checkboxQuestion{Option 3}
\end{checkboxQuestionsCompact}
```
#### Expanded

```
\begin{checkboxQuestions}{Your Question}
	\checkboxQuestion{Option 1}
	\checkboxQuestion{Option 2}
	\checkboxQuestion{Option 3}
\end{checkboxQuestions}
```

### Free-Text Questions

Freetext questions are any questions that can be answered by a written respone in free text form

#### Inline
The Question and response fields are in the same line. This necessitates that the response is a single line response.

```
\freetextQuestionInLine{Your Question}{12cm}
```

Where the first parameter is your question, and the second parameter is the length of your input field

#### Single Line

The Question is in the first line, with a single-line response field in the second line.

```
\freetextQuestionSingle{Your Question}
```

#### Multi-Line
The Question is in the first line, with a multi-line response field starting in the second line.

```
\freetextQuestion{Your Question}{14mm}
```

Where the first parameter is your question, and the second parameter is the height of your input field


### Likert Scale Questions

Likert-Scale questions are questions asking if the participant agrees with a statement. Options range from strongly agree to strongly disagree in five steps.

```
\begin{agreeQuestions}
	\agreeQuestion{Your first question here}
	...
	\agreeQuestion{Your last question here}
\end{agreeQuestions}

```

## Contributing

If you have interesting sets of questions, that could be of use in general (for example standardized question blocks such as the System Usability Scale), feel free to open a pull request.
Likewise, if you spot any errors, feel free to open an Issue or even better a pull request fixing the issue.
