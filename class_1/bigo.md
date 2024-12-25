# Introduction

The very first thing we tackle
`Time and Space`. Big O as the call it.


# What is Big O?

Big O is a way to categorize you algorithms' time or memory requirements based on input.

It is not meant to be an exact measurement. 
It will not tell you how many CPU cycles it takes, 
instead it is meant to generalize the growth of you algorithm.


Example

So When someone says O(h) of N, they mean your algorithm will grow linearily based on input.


# Why do we use it?

Often it will help us make decision about what data structures and algorithms to use.
Knowing how they will perform, can greatly help create the best possible program out there.


# Lets do a small example

First, Lets consider the following code.

```typescript

function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; i++) {
        sum += n.charCodeAt(i);
    }
    return sum;
}

```

For those that knows big o, this is easy.

# Big O, said differently

As your input grows, how fast does computation or memory grow?

# Important concept 1

> 1. growth is with respect to the input

In the real world
obviously memory growing is not computationally free, but in the matter of thinking about algorithms,
we don't necessarily think about that.

In languages like Go or Javascript you pay even heavier penalties because the memory can be kept
around, grows faster and causes complete halts in your program for cleanup.

# Let's go back to our example

Lets look at input. How does our program's execution time grow with respect to input?

```typescript

function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; i++) {
        sum += n.charCodeAt(i);
    }
    return sum;
}

```

How can you tell?

# The simplest trick

For complexity,

> Look for loopls

```typescript

function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; i++) {
        sum += n.charCodeAt(i);
    }
    return sum;
}

```

# What's the running time?

If the previous was O(N), what's this?


```typescript

function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; i++) {
        sum += n.charcodeat(i);
    }

    for (let i = 0; i < n.length; i++) {
        sum += n.charcodeat(i);
    }

    return sum;
}

```

# Important concept 2

> 2. Constants are dropped

O(2N) -> O(N) and this makes sense. That is because Big O is meant to describe the upper bound of the algorithm.
The constants eventually becomes irrelevant.

Take The following:

> N = 1, O(10N) = 10, O(N^2) = 1
> N = 5, O(10N) = 50, O(N^2) = 25
> N = 100, O(10N) = 1,000, O(N^2) = 10,000 // 10x bigger
> N = 1,000, O(10N) = 10,000, O(N^2) = 1,000,000 // 100x bigger
> N = 10,000, O(10N) = 100,00, O(N^2) = 100,000,000 // 1000x bigger


# Practical VS Theoretical

Just because N is faster then N^2, doesn't mean practically its always faster for smaller input.

Remember, we drop constants.
Therefore O(100N) is faster than O(N^2) but practically speaking, 
you would probabily win for some small set of input.


# Let's do another example

```typescript

function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; i++) {
        const charCode = n.charCodeAt(i);
        // Capital A
        if(charCode === 65) {
            return sum;
        }
        sum += charCode;
    }
    return sum;
}

```

# Important concept 3

> We often consider the worst case

Especially in interviews 
Therefore any string with E in it will terminate early.
Its still O(N)

# Important concepts

> 1. Growth is with respect to the input.
> 2. Constants are dropped.
> 3. Worst case is usually the way we measure.


# Common complexities

(Complexity Chart)[https://miro.medium.com/v2/resize:fit:720/format:webp/0*P5FlnSY6h2Y7hAE5.png]

# Some Example

> O(N^2)

```typescript

function sum_char_codes(n: string) {
    let sum = 0;
    for(let i = 0; i < n.length; i++) {
        for(let j = 0; j < n.length; j++) {
            sum += charCode;
        }
    }

    return sum;
}

```

> O(N^3)

```typescript

function sum_char_codes(n: string) {
    let sum = 0;
    for(let i = 0; i < n.length; i++) {
        for(let j = 0; j < n.length; j++) {
            for(let k = 0; k < n.length; k++) {
                sum += charCode;
            }
        }
    }

    return sum;
}

```

> O(n log n)

- We will implement and explain later ( ex: Quicksort )

> O(log n)

- Binary search trees

> Hint: There is a special one we will look into


# Why so obviated?

There are other resources out there to dive deep into big o notation. I just don't think we need yet another Big O explanation.
Instead I am going to focus on actively looking at running times and we will determine things together.


# Takeaways

> 1. Growth is with respect to the input.
> 2. Constants are dropped.
> 3. Worst case is usually the way we measure.


> One more note

Is there anything else besides Big O? Well, there is technically a bunch of different ways to measure
the complexity of algorithms, but in general the easiest one to use the "Upper Bound"


# Space the final frontier

we pretty much wont be going over space in this course. Just not something we will be discussing.
I find this less consequential in daily life considering I see things like this.

# Before we finish

> Questions?
