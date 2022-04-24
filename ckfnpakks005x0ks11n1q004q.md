## Debouncing v/s Throttling: What's the difference?

Website performance plays a huge role in enhancing the user experience of our websites. In this article, we will learn about performance optimization techniques like Debouncing and Throttling and the key difference between them.

Debouncing and Throttling are widely-used techniques that help us in limiting the rate at which a function fires off. These two techniques give us a layer of control between the event and the execution of the functions attached to them. API servers often implement either of these two techniques to prevent the application from being overloaded. 

These function calls could be anything from a simple scroll event to an API call to the server. Both these techniques are almost identical and help us reduce the number of function calls being made but they have one small, but significant difference among them. 

Before we get into the difference, let's understand how they work individually -
### What is Debouncing? 

Debouncing is a technique in which no matter how many times a user fires an event, 
the call will be made only after a specific amount of time has passed **after the user stops firing the event.**

For example, let's say a user is typing something in a search box. This search box makes API calls and has a debounce function attached to it with a specified time duration of 400ms. So now, unless 400ms have passed after the user stopped typing, the API call wouldn't be made. 

![debouncing.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1601131218693/oxlreiYn1.gif)

I wrote a detailed article on Debouncing in Javascript, a couple of months ago. If the concept of debouncing is completely new to you, I strongly suggest you go to the link below and read the post before moving ahead with this one.

%[https://blog.afrazmomin.com/debouncing-in-javascript]


### What is Throttling?

Throttling is a technique that makes the next function call strictly after a certain period of time. No matter how many times the user fires an event, the function attached will be **executed only once in the given time period.** 

#### Let's understand this by coding a simple throttle function ourselves - 

We will start by taking a simple Button. Let's say this button calls some API. The `onclick` attribute on this button will call two functions - `normalFunc()` and `apiWithThrottle()`

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1601304916777/IXISBvKc2.png)

In our Javascript file, we'll define the functions -

![carbon.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1601198395398/VEnG_lef1.png)

The `normalFunc()` keeps track of the number of clicks made on the button, and `apiCallFunc()` keeps track of the number of API calls being made. The function `apiWithThrottle()` when triggered by the button, will call the `throttle()` function in which the function to be throttled and the time limit are given as parameters.

#### After running this code, we see something like this -

![second.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1601302138430/2VOWXDLv1.gif)

Here, we have set the time limit to 1 second (1000ms). Notice how the user clicks the button multiple times but the call to the API is only made 3 times, each after an interval of 1 second. To sum it up in simple words - even if the user clicks the button 15 times in 3 seconds, the number of times the API call will be made is 3 only. 

> Here's the link to the [CodePen](https://codepen.io/afrazchelsea/pen/ZEWZZzP?__cf_chl_jschl_tk__=0179b83d2f4126274a036af65c94852eb166cd86-1601352909-0-AXFNLTphxkHBsmCGyeIIV4X53_DUqUBsuUqwuDJo2hEXdw_PljihEnXNP-F7czffsK8uEmpyESR3J4i3DaiMUK-Ud_I3r0fZV8SN4K91Wq6E1_dyGaKA-BQrU2MeI_wl_SubktUz2xPIf-BV7SQqXSLI9mBgRQYmkff0xGVEor8jZYWXV4xxMImy6zjOgkMAK5vMgxE63fpldBX5DUbfrgJNKOe1qRIotDd9GL2g-vX5ooy4ztqTEombA1an1Hg7WEy6gCWAJN9wOm2YzsWmeROuN_aYeC7KzZ1iA7KG_vi-uDY2_onbDJIgvjazYnyDuD3MExodeSq6AYUWeQcH6E8), if you want to try this out yourself.

### Debouncing vs Throttling

The difference between the two can be understood by taking a simple real-life example - 

- Debouncing

Imagine you're a 7-year toddler who loves chocolates. You persistently keep asking your mom for some chocolates. She gives you some but then you start asking for some more. You ask her so many times that she gets annoyed and tells you that you can have it only if you don't bother her and remain silent for the next one hour. This means if you keep asking her, you will only get it one hour after the last time you asked her. 

This is debouncing.

- Throttling

Consider the same example - You ask your mom for chocolates despite having them a few minutes ago. You persistently keep asking her, she gets annoyed and finally decides to give you some. But she, being your mom, knows that you will ask for some more in a few minutes. So she gives you the chocolates with a condition that you won't get any more for the next one hour. You still keep bothering her for more but now she ignores you. Finally, after an hour has passed, she gives you the chocolates. If you ask for more, you will get it only after an hour, no matter how many times you ask her.

This is what throttling is!

#### Use-cases

Both these techniques have their own set of use-cases. 

Debouncing can be used when the result of the most recent event occurrence is what is important. For example, a search query on an e-commerce website. 

Throttling can be used when the input provided to the function call doesn't matter or is the same each time. For example, infinite scrolling on a webpage. Here, we need to check how far the user is from the bottom of the page. If they're too close, we request more data and append it to the page. Here debouncing wouldn't work as it would only trigger the event when the user has stopped scrolling but we need to start fetching the content before the user reaches the bottom.

Another example would be a multiplayer fighting game where your character has to punch to defeat its opponent. Throttling can be applied to this punching ability of the character such that it can punch only once per second. Now even if the player gives the command to punch 10 times in 5 seconds, the number of punches thrown would be 5 only.

### Wrapping Up

Techniques like debouncing and throttling give us control over the execution of events in our websites, helping us reduce the number of high computational tasks that may hamper the performance of our website. They might have different use-cases but the end goal remains the same i.e better performance. So if you're a developer looking to optimize your website, you know what to do!

<hr/>

**If you liked what you read, share the article with a friend and connect with me on Twitter - [@afraz_momin](https://twitter.com/afraz_momin). Also, subscribe to my newsletter and stay up-to-date with my latest blog posts. I plan to write similar articles on Javascript in the coming days!**








