---
title: "DT Model"
description: ""
summary: ""
date: 2024-02-09T11:44:11+01:00
lastmod: 2024-02-09T11:44:11+01:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "dt-model-122cfb3ade1105ebc3cbd884b821be68"
weight: 997
toc: true
---

---

With respect to the element present in the real world, 
it is defined as a Physical Asset (PA) with the intention of referring to any entity 
that has a manifestation or relevance in the physical world and a well-defined lifespan.

<!-- ![Abstract DT Structure](abstract_dt_structure.jpeg) -->

The previous Figure schematically illustrates the main component of an abstract Digital Twin and clarifies its 
responsibility to be a bridge between the cyber and the physical world. 
The blueprint components (then mapped into the WLDT Library) are:

- **Physical Interface** The entity in charge of both the initial *digitalization* o *shadowing* process and the perpetual responsibility
to keep the DT and PA in synch during its life cycle. It can execute multiple **Physical Asset Adapters** to interact with the PA and detect and
digitalize the physical event coming from the physical entity according to its nature and the supported protocols and data formats (e.g., through HTTP and JSON).
- **Digital Interface** The component complementary to the Physical Interface and in charge of handling DT's internal variations and events 
towards external digital entities and consumers.  It executes multiple and reusable **Digital Adapters** in charge of handling digital interactions and events 
and responsible for making the DT interoperable with external applications.
- **DT's Model** The module defining the DT's behaviour and its augmented functionalities. It supports the execution of different configurable
and reusable modules and functionalities handling both physical and digial events according to the implemented behaviour.
Furthermore, the Model is the component responsible to handle and keep updated the Digital Twin State as described in the following sections.

The Digital Twin ``Model``(M) allows capturing and representing the PA at an appropriate level of abstraction, 
i.e., avoiding irrelevant aspects for its purpose and modeling only domain-level information rather than technological ones. 
Finally, the link between the physical and digital copy is defined as shadowing. Specifically, 
the term defines the process that enables continuous and (almost) real-time updating of the internal state of the DT in relation to changes 
that occur in the PA.

Each DT is thus equipped with an internal model, which defines how the PA is represented in the digital level. 
The DT's representation denoted as **Digital Twin State** supported and defined through M is defined in terms of:

- **Properties**: represent the observable attributes of the corresponding PA as labeled data 
whose values can dynamically change over time, in accordance with the evolution of the PA's state.
- **Events**: represent the domain-level events that can be observed in the PA.
- **Relationships**: represent the links that exist between the modeled PA and other physical
assets of the organizations through links to their corresponding Digital Twins. 
Like properties, relationships can be observed, dynamically created, and change over time, 
but unlike properties, they are not properly part of the PA's state but of its operational context 
(e.g., a DT of a robot within a production line).
- **Actions**: represent the actions that can be invoked on the PA through interaction with the DT or directly 
on the DT if they are not directly available on the PA (the DT is augmenting the physical capabilities).

Once the model M is defined, the dynamic state of the DT (SDT) can be defined by through the combination of 
its *properties*, *events*, *relationships* and *actions* associated to the DT *timestamp* that represents the current time of
synchronization between the physical and digital counterparts.


### The Shadowing Process

The *shadowing* process (also known as replication of digitalization) allows to keep the 
Digital Twin State synchronized with that of the corresponding physical resource 
according to what is defined by the model M. Specifically, each relevant update of the PA state (SPA) 
is translated into a sequence of 3 main steps:

- each relevant change in physical asset state is modeled by a ``physical_event`` (``e_pa``);
- the event is propagated to the DT;
- given the new ``physical_event``, the DT's is updated through the application of a *shadowing function*, 
which depends on the model M

The shadowing process allows also the DT to reflect and invoke possible actions of the PA.
The DT receives an action request (denoted as ``digital_action``) on its digital interface, applies the shadowing function to validate it and then 
propagates the request through its physical interface. 
An important aspect to emphasize is that the request for a ``digital_action`` does not 
directly change the state of the DT since any changes can only occur as a result of the 
shadowing function from the PA to the DT, as described earlier.