https://youtu.be/wrURmYwqYb4?si=esJH2K6CNSdqKHc5

## What is HTTP streaming ?

## When we do it ?

## How airbnb used it ?

## Reverse proxies with HTTP streaming behaviour ?

## My code -

The video titled "Everything about HTTP Streaming and how Airbnb leverages it in production" explains HTTP streaming, its implementation, and how Airbnb uses it to enhance user experience. Here’s a summary with key points:

Introduction to HTTP Streaming:

HTTP is the language of the internet, and we typically send responses to clients all at once. However, there’s an alternative: HTTP streaming, where the server sends the response in chunks.
Streaming is beneficial when the response size is unknown, such as in applications like ChatGPT.
Unlike WebSocket, HTTP streaming operates within the HTTP protocol by sending chunks of data progressively.
Use Cases and Trade-offs:

Streaming is helpful for large or lengthy responses but not for small responses (e.g., 1–2 KB).
Ideal for applications that benefit from receiving partial data, such as LLMs (Large Language Models), where clients can process chunks as they arrive.
How It Works:

Servers send chunks of data without specifying the total response size (using "chunked transfer encoding" instead of "content-length" headers).
This allows clients to start processing chunks immediately, improving performance and memory efficiency on both sides.
Example Implementations:

Airbnb’s Use Case:

Airbnb uses HTTP streaming to optimize first contentful paint (the time it takes for something to appear on a webpage).
They split the response into an early flush (head tag, JS, CSS) and a late flush (body content).
By doing this, critical resources load early, improving user experience.
Challenges:

Reverse proxies (like Nginx) may buffer the responses, which can disable streaming if not properly configured.