## How Many Words Are There In English

> I use English as my second language. However, it does not come as my natural instinct, especially so when I watch English movies without subtitles in cinemas.

### Test your vacabularies

- Here is a useful site to get a general idea of your current vocabulary: [Test Your Vocab](http://testyourvocab.com).
  - And here is my level as an English learner for over 15 years: [Just over 10,000 words](http://testyourvocab.com/result?user=15490663)

As is shown in this website, "Most _native_ English adult speakers who have taken the test fall in the range 20,000–35,000 words." And "for _foreign_ learners of English, we've found that the most common vocabulary size is from 2,500–9,000 words."

### Make use of the [words file](<https://en.wikipedia.org/wiki/Words_(Unix)>) on Unix/Unix-like systems

- For mac, the path is `/usr/share/dict/words`
- To get a closer look at this file, use `cat /usr/share/dict/words` to show the whole file, or `head -n 100 /usr/share/dict/words` or `tail -n 100 /usr/share/dict/words` to get a sneek peak.
- To count the words in this newline-dilimited file, use `wc -l /usr/shar/dict/words`, which gives back the number of over **200,000**.
  - For a more compact word dictionary, there maybe another file under the same path yielding the result of about **70,000** words.

### Little relevance

- Use `tree` command to show the folder structures, and it even shows the symlink file path. Or just use the `readlink` to get the actual path.
- Have to figure out a way to add words easily for me to store them locally.
