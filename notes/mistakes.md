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


###Mistake (squares of sorted array, attempt 1):
Passing the given tests does not mean the solution is correct.
My insert-position counter worked for the test inputs by coincidence
and broke on [-2, 5].

Lesson:
Before saying "done", invent my own edge cases:
mixed negatives/positives, all negatives, single element.


###Hidden cost of list operations:
list.insert(0, x) and list.pop(0) are O(n) — every element shifts.
list.append(x) and list.pop() are O(1).
Building a list with insert(0, ...) in a loop makes the whole thing O(n^2).

To reverse: squares.reverse() or squares[::-1] instead of a pop loop.


###Two pointers takeaway:
In a sorted array with negatives, the LARGEST squares are at the EDGES.
Compare both ends, take the bigger square, move that pointer inward.
With while left <= right and if/else (>=), no special case is needed
for equal squares or for the middle element.


###reverse() complexity:
list.reverse() is O(n), NOT O(1) — it swaps elements pairwise.
Same for the [::-1] slice (which also creates a new copy).
That is fine: one O(n) reversal at the end keeps the algorithm O(n).
The trap is reversing AS YOU GO with insert(0, ...) — that is O(n^2).


