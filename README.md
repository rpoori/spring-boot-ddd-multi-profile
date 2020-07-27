# spring-boot-ddd-multi-profile

Same spring boot app can be deployed with multiple profiles.  
For example, there can be a regular profile and a "demo" profile.  
In the demo profile the store and service interfaces are injected with a demo implementation with stubbed data instead of the regular implementation.  
Domain driven design makes this possible.  
So in this way, a whole site can be brought up with stubbed data by running the backend services on demo profile 
and making the UI point to these demo backend services.

This can be achieved through different means:

Instead of deploying the same app with multiple profiles,
different implementations can be injected for the same bean at runtime using qualifiers and spring plugin registry.
So a single deployment of the app will provide different implementations based on some differentiator variable (in request header for example).
This approach is implemented in the repo spring-boot-bean-injection-runtime.
