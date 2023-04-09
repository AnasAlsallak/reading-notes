# Table of Contents

- [Pain vs. Suffering](#pain-vs-suffering)
- [A beginner's guide to Big O Notation](#a-beginners-guide-to-big-o-notation)
- [Python Names and Values](#python-names-and-values)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## ***Pain vs. Suffering***

No pain No gain, this article talks about The nature of this courses learning environment which is concentrated but also is great to reach our goals, but it does come at a price that is felt in all levels; physically, mentally, and emotionally for us.

When necessary discomfort comes from it reaching goals and growing to adapt and learn it's called **pain** and the relation between them are proportionally whereas when there is no value from it that is **suffering**; it's a big difference.

That pain is only temporary but the seed of it will last. And it will all pays off at the end inshallah.

- We will Constantly be thrust far out of our comfort zone.
- We will be pushed physically, sitting in a chair and staring at your screen for long hours isn't the healthiest thing.

To help avoid the suffering you need to communicate, ask questions and research, don't experience the pain alone, so it doesn't turn in to suffering.

Keep reminding your self why are you here and what you come to achieve.

___

## ***A beginner's guide to Big O Notation***

The **Big O Notation** describes the complexity or performance of an algorithm in terms of the worst case senario to estimate *time taken* or *space used* for the machine to execute.

How can we use Big O?

    1. Dealing with algorithms that need to operate at scale.
    2. help you make the correct choices and acknowledge trade-offs
    when working with different data sets.

What does the notation mean?

        1. O(1): this algorithm takes the same time/space each time regardless of the size of the input.
        2. O(N): this algorithm takes different time/space each time depending linearly and directly on the size of the input.
        3. O(N²): this algorithm takes different time/space each time depending directly on the square size of the input.
        4. O(2^N): this algorithm takes different time/space each time depending exponentially and directly on the size of the input doubling with each change.

___

## ***Python Names and Values***

The idea is that the syntax to Python doesn't work just like any other language it can be a bit confusing.

- How assignment works: x is assigned a value of 23

        x =23

- Re-assignment happens independently: here y is still 23 despite x changing its value to 12

        x =23
        y = x
        x =12

- Assignments never copies data: here both nums and others are pointing at the same list, not copying it

        nums =[1,2,3]
        other = nums

- Lots of things are references, like objects attributes, list elements, dictionary values, basically anything to the left of an assignment.

___

## Things I want to know more about

- How to conceive big o notation for an algorithm and how to utilize it.

[Move to Class 02](./Class02.md) | [Previous](./README.md)
