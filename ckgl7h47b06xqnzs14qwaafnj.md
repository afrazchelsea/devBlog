## React vs Vanilla JS - When to use what?

Web apps can be complex and may require a lot of dynamic functionalities. One can opt for Vanilla JS to build their applications but if you have worked with Vanilla JS before, you know how messy it can get. Here's when JS frameworks like, React, Angular and Vue, come into the picture.

In this article, I'll walk you through the main differences between a JS library like React and plain Javascript - when to choose which and why?

![joke.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1598701832347/nU1hNGz_w.jpeg)

Let's start by answering two simple questions.

### What is Vanilla JS?

Vanilla JS is nothing but plain JS without any external libraries or frameworks. Using this we can build powerful and cross-platform applications.

### What is React?

React is a Javascript library used for building user interfaces. It allows us to make complex UIs from isolated pieces of code called "components".

React has quickly become one of the most popular Javascript libraries. This is entirely because of its flexibility and the improvement it brings in the performance. React breaks down the UI into smaller and reusable components that can move around data amongst each other. This breaking down of the UI is what gives React an edge over Vanilla JS.

In Vanilla JS, the code becomes very difficult to maintain if the application is large because in such cases the UI needs to be updated regularly. Here, to change a UI element you need to first find the element in the DOM and then update it. This is fine when you have to update only a single element but imagine doing this on long-form which a user needs to fill. This could be very memory and browser intensive.

This is where React comes in with a great feature i.e its own virtual DOM. The virtual DOM is a shortcut to bypass the manual work. It is a lightweight copy of the actual DOM. It has the same properties as the real DOM but lacks the power to make changes on the screen.

The most important and fundamental reason why modern frameworks are used is that, **with Vanilla JS, keeping the UI in sync with the state is hard**.

### Let's understand this by taking an example

_Consider Facebook. Say at a given time, your friends comment on a picture of yours and you want to see it immediately. You'd want to shift from liking posts to commenting or sharing without being slowed down._

Now, this can be done in Vanilla JS too, but the number of changes you'd have to do in the code would be very tedious. All this tiresome work can be avoided by using something like React.

Basically, with React, we can manage to keep **the UI and the state synchronized with each other**. In Vanilla JS, if you have to change the state, you would need to update the UI. One small mistake and your UI could be out of sync with your data.

Code organization and re-use is another important aspect of React. A component created only once can be used multiple times with different data.

## Conclusion

Whether you should use Vanilla JS or React depends very much on your use case.

Vanilla JS is awesome but it's not a great alternative when it comes to building huge applications with complex dynamic functionalities. Besides, it cannot create complex and efficient UIs. So if you have an app that changes frequently and drastically with thousands of pages, it is better to use a modern Javascript framework.

On the other hand, React which allows us to use reusable components and is capable of keeping the UI in sync with the state, can definitely solve this problem.

If you liked this post, consider subscribing to my newsletter.

Thanks for reading!