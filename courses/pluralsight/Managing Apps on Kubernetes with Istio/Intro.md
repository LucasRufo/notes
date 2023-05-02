## What is Service Mesh

Service mesh is a layer in the infrastructure that handles all the communication through the network between your apps. It can apply different rules to different services and this can be achieved without having to change application code.

Istio comes with a price: computation cost. This happens because some features from Istio can be pretty CPU heavy, so when you are considering the use of a solution like Istio, you need to have this in mind.

Istio uses a sidecar model in Kubernetes, so all Pods have a separate container that acts as a proxy in every network call to apply rules. Istio uses the Envoy proxy [Envoy Proxy - Home](https://www.envoyproxy.io/). 



