# Analytics as Secret Glue for Microservice Architecture

Usually analytics is overlooked as something don't have direct releation with system design. However heterogeneous nature of microservice has made perfect use case for analytics. 

Datawarehouse is a central repository/storage integreate with one or more disparate data sources. While designing a feature or integrating with microservice, KPI or success metrics to be figured out. 

Here is type of metrics to follow:
1. **Company's high-level metrics:**
The metrics usually don't move at once. They don't move by a single feature or iteration. They alter by compound affect of many iterations. 

2. **Team metrics:**
You do want to drive up your team metrics, but the important factor here is to look at them in the context of being a part of a system.

3. **More-granular experiments or project-related metrics:**
These usually come to mind when designing a feature. They should be as detailed as possible so you can measure the direct and isolated impact.
