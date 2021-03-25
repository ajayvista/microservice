**API gateway**
Manages all ingress (north-south) traffic into a cluster, and provides additional. It acts as the single entry point into a system and enables multiple APIs or services to act cohesively and provide a uniform experience to the user.

Consul: A Go-based service mesh from HashiCorp.

Control plane: Takes all the individual instances of the data plane (proxies) and turns them into a distributed system that can be visualized and controlled by an operator.

Data plane: A proxy that conditionally translates, forwards, and observes every network packet that flows to and from a service network endpoint.

East-West traffic: Network traffic within a data center, network, or Kubernetes cluster. Traditional network diagrams were drawn with the service-to-service (inter-data center) traffic flowing from left to right (east to west) in the diagrams.

Envoy Proxy: An open-source edge and service proxy, designed for cloud-native applications. Envoy is often used as the data plane within a service mesh implementation.

Ingress traffic: Network traffic that originates from outside the data center, network, or Kubernetes cluster.

Istio: C++ (data plane) and Go (control plane)-based service mesh that was originally created by Google and IBM in partnership with the Envoy team from Lyft.

Kubernetes: A CNCF-hosted container orchestration and scheduling framework that originated from Google.

Kuma: A Go-based service mesh from Kong.

Linkerd: A Rust (data plane) and Go (control plane) powered service mesh that was derived from an early JVM-based communication framework at Twitter.

Maesh: A Go-based service mesh from Containous, the maintainers of the Traefik API gateway.

MOSN: A Go-based proxy from the Ant Financial team that implements the (Envoy) xDS APIs.

North-South traffic: Network traffic entering (or ingressing) into a data center, network, or Kubernetes cluster. Traditional network diagrams were drawn with the ingress traffic entering the data center at the top of the page and flowing down (north to south) into the network.

Proxy: A software system that acts as an intermediary between endpoint components.

Segmentation: Dividing a network or cluster into multiple sub-networks.

Service mesh: Manages all service-to-service (east-west) traffic within a distributed (potentially microservice-based) software system. It provides both functional operations, such as routing, and nonfunctional support, for example, enforcing security policies, quality of service, and rate limiting.

Service Mesh Interface (SMI): A work-in-progress standard interface for service meshes deployed onto Kubernetes.

Service mesh policy: A specification of how a collection of services/endpoints are allowed to communicate with each other and other network endpoints.

Sidecar: A deployment pattern, in which an additional process, service, or container is deployed alongside an existing service (think motorcycle sidecar).

Single pane of glass: A UI or management console that presents data from multiple sources in a unified display.

Traffic shaping: Modifying the flow of traffic across a network, for example, rate limiting or load shedding.

Traffic shifting: Migrating traffic from one location to another.
