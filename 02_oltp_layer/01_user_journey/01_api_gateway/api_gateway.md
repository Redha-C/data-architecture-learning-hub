# API Gateway

An **API Gateway** is a service that acts as an intermediary between the frontend of an application and its backend services[1]. The concept emerged from the shift toward **microservice architectures**, where backends are composed of modular, independent services rather than a single monolithic application[3].

Let's consider the schema below: 

<p align="center">
<img src="../../../images/architecture_diagram_website_front_and_back.png" alt="Alt text" width="1000">
</p>

Without an API Gateway, when a user interacts with the website (e.g., clicking a button), the frontend would need to send **multiple requests** to various backend microservices to gather the necessary data and render the UI.  

Instead, by **centralizing frontend requests through an API Gateway**, only **one request** is sent to the Gateway. The Gateway then communicates with the appropriate microservices, aggregates the responses, and returns a single result to the frontend.


If no API Gateway was used, if a user clicks on a specific functionality of a the website, the frontend would have to send several requests to different microservices to gather the information and send it back to the use. Instead, centralising requests from frontend (users) into the API Gateway is a powerful move as solely the API Gateway will communicate with the different microservices to gather necessary information. 

This approach brings **four key benefits**[2]: 
1. **Abstraction:** "API Gateways provide a unified entry point for external consumers to access a set of microservices, abstracting the underlying implementation details and allowing the microservices to evolve independently."

2. **Improved client performance:** implementing an API Gateway allows to gain in performance on the frontend for the user and the frontend will only have to request from the API Gateway and not from the multitude of microservices.

3. **Enhanced security:** The Gateway serves as a **security layer**, handling authentication, authorization, rate limiting, IP allowlisting, and more — reducing exposure of internal microservices.

4. **Better consumer experience:** "API Gateways make it easier for consumers to discover and use the APIs provided by the microservices, improving the overall ease of use and user experience."

# Bibliography
[1] [What is an API Gateway ?](https://www.youtube.com/watch?v=hWRRdICvMNs)

[2] [Cloudflare article](https://www.cloudflare.com/learning/security/api/what-is-an-api-gateway/)

[3] [Talend article](https://www.talend.com/fr/resources/api-gateway/)
