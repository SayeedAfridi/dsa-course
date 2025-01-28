# The second data structure

This should be a time filled with exuberance!


# I said something weird

I said that Javascript arrays, `const a = [];` is not an array.
We know have a solid definition of an array,
is it an array? And why not?

# So lets go to our real first data structure

Its hard to call Array a data structure because its so fundamental. Its something that is
available in every language except the one in this course because...Javascript.

# So what sucks about an array?

- Deletion (Why?)
- Insertion (Why?)
- Its ungrowable (Why?)


# Lets talk LinkedList

So how does it work? (Whiteboard)

- Singly Linked
- Double Linked

# Lets talk time / space complexity

- prepend / append
- Insertion in the middle
- Deletion from ends
- Deletion in the middle
- Get head / tail
- Get in general

# Lets implement linked list

```typescript

interface LinkedList<T> {
    get length(): number;
    insertAt(item: T, index: number): void;
    remove(item: T): T | undefined;
    removeAt(index: number): T | undefined;
    append(item: T): void;
    prepend(item: T): void;
    get(index: number): T | undefined;
}

```

