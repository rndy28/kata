# Introduction

Big 0 = time & space

What is Big O Big O is a way to categorize your algorithms time or memory requirements based on input. It is not meant to be an exact measurement. It will not tell you how many CPU cycles it takes, instead it is meant to generalize the growth of your algorithm.

In the real world obviously memory growing is not computationally free, but in the matter of thinking about algorithms, we don't necessarily think about that.

Simplest trick for complexity Look for loops

```ts
// example of O(n)
function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; ++i) {
        sum += n.charCodeAt(i);
    }

    return sum;
}
```

## Important concepts

-   growth is with respect to the input
-   Constants are dropped

```ts
function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; ++i) {
        sum += n.charCodeAt(i);
    }

    for (let i = 0; i < n.length; ++i) {
        sum += n.charCodeAt(i);
    }

    return sum;
}
```

O(2N) -> O(N) and this makes sense. That is because Big O is meant to describe the upper bound of the algorithm (the growth of the algorithm). The constant eventually becomes irrelevant.

## There is practical vs theoretical differences

Just because N is faster than N^2, doesn't mean practically its always faster for smaller input.

Remember, we drop constants. Therefore O(100N) is faster than O(N^2) but practically speaking, you would probably win for some small set of input.

### Another example

```ts
function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; ++i) {
        const charCode = n.charCodeAt(i);
        // Capital E
        if (charCode === 69) {
            return sum;
        }

        sum += charCode;
    }

    return sum;
}
```

### In BigO we often consider the worst case

Especially in interviews (i have never been asked for best, average, and worst case, just worst case).

<b>E = 69</b>

Therefore any string with E in it will terminate early (unless E is the last item in the list).

<b>ITS STILL O(N)</b>

## Important concepts

-   growth is with respect to the input
-   Constants are dropped
-   Worst case is usually the way we measure,

<br/>

## Some Examples

<br/>

### <b>O(n^2)</b>

<br/>

```ts
function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; ++i) {
        for (let j = 0; j < n.length; ++j) {
            sum += charCode;
        }
    }

    return sum;

}
```

<br/>

### <b>O(n^3)</b>

<br/>

```ts
function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; ++i) {
        for (let j = 0; j < n.length; ++j) {
            for (let k = 0; k < n.length; ++k) {
                sum += charCode;
            }
        }
    }
    return sum;
}
```

