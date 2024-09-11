---
title: 2024-08-22-generate-audiobooks
tags:
  - blog
  - idea
---
First, get proper licensing, so you can license/sell/rent the book to libraries or people or Audible or whoever.

Huh, that's an even smarter way to do it than what I had imagined.
1. Take the text of the book
2. Run it through an LLM and ask it to extract a list of everyone who speaks, be they man, beast, or machine
3. Now run the list and the text through the LLM. For each person in the list, have it take all the words this person says and generate a dict (hash map) for this person. The key is the person's name, the value is an object, with each of their quotes.
4. Given the list of characters and the text of the book, have an LLM generate a dict containing all of the descriptions given for the character within the book. If the book mentions he is scrawny, you note that. If it mentions his height or where he's from, you note that. etc. You keep this list to only facts, and do not hallucinate or add anything that was not explicitly mentioned in the book.
5. Combine the two dicts for each person, using either SQL or Python or an LLM, into one dict with the key = person's name and value = an object containing a list of all his/her quotes, his gender if this is given, his age if this is given, and a list of descriptions about him.
6. Use an LLM to generate a complete description of each character.
7. Use ElevenLabs or another speech synthesizer to generate a voice based on this description for each character.
8. Add one more item to the list, the narrator. Use the Wikipedia entry and any other research you can find from the publisher or the person's Twitter, etc. to generate this bio/description. In this case, you don't want to be too precise. You want to focus on having the voice be easy to understand. If the author is 67, you don't want to say that the author is old or a senior. You want the narrator's age to be 30 years old no matter what.
9. Run through the book and have an LLM (e.g. Claude Sonnet or GPT-4o or Ollama (more complicated but probably cheaper)) label all text with a speaker, from the list above containing characters + the narrator.
10. Now have ElevenLabs or similar software speak the entire book.
11. Combine the audio together and edit it (clearly, based on *Tomorrow, Tomorrow, and Tomorrow*, we can see that it's okay if some things get through—Dov might say "dude" the exact same way twice just under 01h00m into the book, and it's fine. Most people don't notice, and those who notice don't care)