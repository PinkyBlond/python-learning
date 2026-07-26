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



You wrote:

del key

It should be

del dictionary[key]



You wrote

for index, num in (nums):

I know exactly what you meant.

The missing piece is:

for index, num in enumerate(nums):
    print(index, num)


Binary search is

O(log n)


