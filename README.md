# Prompt-engineering

## General Guidelines

#### Principle 1: Write clear and specific instructions

Tactic 1: Use delimiters to clearly indicate distinct parts of the input

Delimiters can be anything like: """, < >, <tag> </tag>, 

Tactic 2: Ask for a structured output

e.g. Provide them in JSON format with the following keys: 
book_id, title, author, genre.

Tactic 3: Ask the model to check whether conditions are satisfied
e.g.
```
If it contains a sequence of instructions, \ 
re-write those instructions in the following format:

Step 1 - ...
Step 2 - …
…
Step N - …

If the text does not contain a sequence of instructions, \ 
then simply write \"No steps provided.\
```

Tactic 4: "Few-shot" prompting

```
Your task is to answer in a consistent style.

<child>: Teach me about patience.

<grandparent>: The river that carves the deepest \ 
valley flows from a modest spring; the \ 
grandest symphony originates from a single note; \ 
the most intricate tapestry begins with a solitary thread.

<child>: Teach me about resilience.
```

#### Principle 2: Give the model time to “think”

Tactic 1: Specify the steps required to complete a task

```
Perform the following actions: 
1 - Summarize the following text delimited by triple \
backticks with 1 sentence.
2 - Translate the summary into French.
3 - List each name in the French summary.
4 - Output a json object that contains the following \
keys: french_summary, num_names.

Separate your answers with line breaks.
```
More better way -

```
Your task is to perform the following actions: 
1 - Summarize the following text delimited by 
  <> with 1 sentence.
2 - Translate the summary into French.
3 - List each name in the French summary.
4 - Output a json object that contains the 
  following keys: french_summary, num_names.

Use the following format:
Text: <text to summarize>
Summary: <summary>
Translation: <summary translation>
Names: <list of names in Italian summary>
Output JSON: <json with summary and num_names>
```
Tactic 2: Instruct the model to work out its own solution before rushing to a conclusion

e.g. instructing the model to work out its own solution first!


#### Model Limitations: Hallucinations

## Iterative Prompt Develelopment

e.g. 
- The text is too long
- Text focuses on the wrong details
- Description needs a table of dimensions


## Summarizing
- Limit words/sentences/characters 
- Summarize with focus on topics e.g. from e commerse customer feedback - focus on shipping or product usage.
- ```Extract``` versus ```Summarize```

## Inferring

- Binary Classification : 
- Mlticlass, Multi label classification ( even unsupervised e.g. list top 3 emotions of author by reading the text)
- Topic modeling

## Transforming

For tasks such as language translation, spelling and grammar checking, tone adjustment, and format conversion.
- Translation to another language
- Tone conversion : formal to informal, english pirate etc
- Spell check , Punctuations, Grammar check : Proof read and rewrite

## Expanding
- Customize the automated reply to a customer email
- Remind the model to use details from the customer's email

## Chatbot
- Setup, Order Bot

