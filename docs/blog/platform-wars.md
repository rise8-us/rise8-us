# PaaS vs DIY Kubernetes

In the current landscape of Kubernetes (k8s), there's a common misconception about whether Kubernetes is a Platform-as-a-Service (PaaS). Kubernetes' own documentation clarifies that it is not a traditional, all-inclusive PaaS system. However, this nuance doesn't make it a drawback; rather, it highlights an important distinction. As Kelsey Hightower puts it, "Kubernetes is for people building platforms."

## Kubernetes Overview

Kubernetes is an open-source platform that offers shared services across clusters or nodes, such as scaling, load balancing, or monitoring. Unlike traditional PaaS systems, Kubernetes operates at the container level, providing developers with flexibility in choosing services, resources, and tools. If an application can be containerized, it can run on k8s.

### What Kubernetes Does

- Provides flexibility for app developers.
- Operates at the container level, allowing a diverse set of workflows.
- Does not limit the types of applications supported.

### What Kubernetes Doesn't Do

- Does not provide services across applications, like databases or storage systems.
- Does not dictate a configuration language, leaving it open for diverse workflows.

### DIY Kubernetes Pros

- More out-of-the-box solutions available.
- More flexibility for app developers.
- Ease of containerized application migration.

### DIY Kubernetes Cons

- More required of app teams.
- More complex for simple applications.
- Challenges converting legacy applications.
- Flexibility drives compliance complexities.

## Platform-as-a-Service (PaaS)

A good PaaS decouples application development and deployment from platform operations, allowing for increased focus on Day 2 operations, improved performance capabilities, and streamlined billing. Cloud Foundry is an example of an open-source PaaS project that, while no longer recommended, provides a frame of reference for what a PaaS should be.

### PaaS Pros

- Provides cross-app services.
- Decouples platform and app development.
- Ease of multi-cloud and hybrid approach.
- Structure and opinionation drive simplified controls compliance.

### PaaS Cons

- More upfront cost.
- Less flexibility for app teams.
- Larger infrastructure resource requirements.

## PaaS or K8s?

Choosing between PaaS and raw Kubernetes depends on organizational needs, infrastructure ownership, and technical competence. Over time, teams using raw k8s tend to build internal structures and opinionation, resembling an internal PaaS. The decision may involve weighing the cost-effectiveness of building in-house solutions versus adopting vendor solutions.

### Considerations

- **Lock-in:** In-house solutions also exhibit lock-in, and it's essential to evaluate various forms of lock-in.
- **Costs:** Upfront costs for PaaS may be higher, but it alleviates the burden on application developers.
- **Flexibility:** Kubernetes provides more flexibility but also more responsibility.

There's no definitive answer; the choice depends on the organization's goals and capabilities. Whether PaaS or DIY Kubernetes, the key is to achieve the desired capabilities for successful application deployment.