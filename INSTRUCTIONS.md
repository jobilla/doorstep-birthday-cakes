# Doorstep Birthday Cakes, Inc

Ever had to send someone an awkward "Happy birthday" email? Do you know the pain of having to deliver a cake to someone in the dead of the morning?

No more! Doorstop birthday cakes is here for you. **Simply tell us your loved one's name, birthday and address, pick a cake, and we'll get it straight to their doorstep first thing in the morning**!

What's more, you can add a super spiffy message along with your cake! We'll **add in an iPad** with the cake, so you can give add a personalized message — even with **tweets, youtube videos, and images** — embedded straight on the tablet's screen, so your surprised loved one can read a heartwarming rich message AND eat their cake, too!

### Implementation notes

One small catch — we'll be working with a third party bakery to supply the cakes. They have a limited inventory, so make sure to check and reserve stock before accepting orders! As such, **we'll also only support customers in the Greater Helsinki area**, starting with **Vantaa, Espoo, and Helsinki**.

We also need a way to retrieve a list of cakes we need to deliver every morning, to fulfill customers' orders.

## 👉 What you need to build

You're responsible for building a HTTP API for Doorstep Birthday Cakes, Inc. Another team will build a mobile app frontend for your API.

The **proposed** API for the service you build has the following endpoints:

-   GET `/cake-stock`
    -   Returns what stocks are available, so the frontend can show what cakes to offer for purchase.
    -   Query the bakery's API to get stock!
    
-   POST `/reserve`
    -   Accepts a cake type, recipient name, recipient's birthday, recipient's street address, city of residence, and a rich message.
    -   Place an order to the bakery's API when reserving!
    -   The message may include simple safe HTML, youtube embeds, and twitter embeds. Make it safe to display in a user's browser, as we may also display it on the web.
    
-   GET `/deliveries-today?city=Helsinki`
    -   Should return a list of deliveries to make today. Include a name, address, message, and cake type.
    -   Deliveries are made on a recipient's next birthday.
    -   Deliveries are only done once per order.

You can see a [**proposed complete documentation of the API you need to build here**](https://doorstepbirthdaycakes.docs.apiary.io/#reference "https://doorstepbirthdaycakes.docs.apiary.io/#reference")**.** You may deviate from this; it is merely a proposal.

## What you don't need to build

Don't worry about:

- Authentication
- Payments
- Basically anything else that isn't part of the spec, unless you think it's mission-critical!

## 💡 The bakery's API

You can consult the [**bakery's API documentation here**](https://cakery.docs.apiary.io/#reference/0/orders/list-all-cakes "https://cakery.docs.apiary.io/#reference/0/orders/list-all-cakes"). 

(You **do not need to build this API; assume it already exists.** It's just here so your code has another API to talk to!)

**Note**: This third party API is kind of flakey—we've seen it return HTTP 429 errors whenever we hit it with more than 60 requests a second. Make sure our API remains robust regardless!

## But first, a request from marketing... (Bonus points... Maybe?)

In addition, the marketing team also wants a marketing tool that **lists out all recipients & addresses whose birthdays fall on this day**, including those from past years, so we can send them marketing brochures.

<p align="center">
    <br>
    <br>
    <br>
    <em>This concludes the code test segment of this document.</em>
</p>
   
<p align="center">
  <img  src="https://user-images.githubusercontent.com/1274731/147037683-7907f7e9-731c-4123-8c0b-2090431475f6.png">
</p>

---



## 💡 What we're looking for

We expect you to spend **two hours or less** on this code test, from start to finish.

This code test is built to help us learn your skills with:

-   Backend project management
-   Project documentation
-   HTTP API service design
-   Data persistence
-   Validation
-   Testing, robustness & error reporting
-   Tolerance for large bursts of traffic (without overloading the third party bakery API)
-   Ethical-minded engineering

Our back-end tech stack at Jobilla is mostly written in PHP with Laravel, supported by some NodeJS and Golang services.
However, **we will accept submissions in any language and framework**, provided we can follow your work — we want you to
write your code in a comfortable environment. We *do* encourage using Laravel if you're able to, as that is what you're
likely to work with day-to-day at Jobilla.

---

Bear in mind, this test is **deliberately open to interpretation**. We at Jobilla are a very autonomous team of 
engineers who are very critical of our own workflow, specifications and practices. If you disagree to any part 
of the test specification or think there's a better way to do things, *do so*—and tell us about your decisions and why.

We recommend leaving a text file in your repository with a compilation of your thought process, concerns, and opinions
about **both** the code you wrote and the specification you received. 

It can also include:
- Anything you raised your eyebrows at
- Things you would have done differently if you had more time or context
- Anything you found epecially challenging
- Thoughts on Doorstep Birthday Cakes, Inc as a company
