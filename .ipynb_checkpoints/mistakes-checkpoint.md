###Mistake1:
Used set() when creating an anagram key.

Why wrong:
set removes duplicate letters.

Correct:
"".join(sorted(word))


###Mistake2:
Compared dictionary keys instead of values.

Lesson:
Always ask:
Am I comparing the key or the value?

