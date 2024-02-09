---
title: "DT Engine & DT Instance"
description: ""
summary: ""
date: 2024-02-09T12:16:36+01:00
lastmod: 2024-02-09T12:16:36+01:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "dt-process-25c302e3857da3aacdcb030addaf52a8"
weight: 804
toc: true
---


Now that we have created the main fundamental element of a DT (Physical Adapter, Shadowing Function and Digital Adapter) we can create Class file with a main to create the WLDT Engine
with the created components and start the DT. 

Create a new Java file called ```DemoDigitalTwin``` adding the following code: 

With the following code we now create a new Digital Twin Instance

```java
// Create the new Digital Twin with its Shadowing Function  
DigitalTwin digitalTwin = new DigitalTwin(digitalTwinId, new DemoShadowingFunction());  
  
// Physical Adapter with Configuration  
digitalTwin.addPhysicalAdapter(  
        new DemoPhysicalAdapter(  
                String.format("%s-%s", digitalTwinId, "test-physical-adapter"),  
                new DemoPhysicalAdapterConfiguration(),  
                true));  
  
// Digital Adapter with Configuration  
digitalTwin.addDigitalAdapter(  
        new DemoDigitalAdapter(  
                String.format("%s-%s", digitalTwinId, "test-digital-adapter"),  
                new DemoDigitalAdapterConfiguration())  
);
```

DTs cannot be directly run but it should be added to the `DigitalTwinEngine` in order to be executed through the WLDT Library

```java
// Create the Digital Twin Engine
DigitalTwinEngine digitalTwinEngine = new DigitalTwinEngine();  

// Add the Digital Twin to the Engine
digitalTwinEngine.addDigitalTwin(digitalTwin);
```

In order to start a DT from the Engine you can:

```java
// Directly start when you add it passing a second boolean value = true
digitalTwinEngine.addDigitalTwin(digitalTwin. true);

// Starting the single DT on the engine through its id
digitalTwinEngine.startDigitalTwin(DIGITAL_TWIN_ID);

// Start all the DTs registered on the engine
digitalTwinEngine.startAll();
```

To stop a single twin or all the twin registered on the engine:

```java
// Stop a single DT on the engine through its id
digitalTwinEngine.stopDigitalTwin(DIGITAL_TWIN_ID);

// Stop all the DTs registered on the engine
digitalTwinEngine.stopAll();
```

It is also possible to remove a DT from the Engine with a consequent stop if it is active and the deletion of its reference from the engine:

```java
// Remove a single DT on the engine through its id
digitalTwinEngine.removeDigitalTwin(DIGITAL_TWIN_ID);

// Remove all the DTs registered on the engine
digitalTwinEngine.removeAll();
```

The resulting code in our case is: 

```java
public class DemoDigitalTwin {

    public static void main(String[] args)  {
        try{

            // Create the new Digital Twin
            DigitalTwin digitalTwin = new DigitalTwin(
                    "test-dt-id",
                    new DemoShadowingFunction("test-shadowing-function")
            );

            //Default Physical and Digital Adapter
            //digitalTwin.addPhysicalAdapter(new DemoPhysicalAdapter("test-physical-adapter"));
            //digitalTwin.addDigitalAdapter(new DemoDigitalAdapter("test-digital-adapter"));

            //Physical and Digital Adapters with Configuration
            digitalTwin.addPhysicalAdapter(new DemoConfPhysicalAdapter("test-physical-adapter", new DemoPhysicalAdapterConfiguration()));
            digitalTwin.addDigitalAdapter(new DemoConfDigitalAdapter("test-digital-adapter", new DemoDigitalAdapterConfiguration()));

            // Create the Digital Twin Engine
            DigitalTwinEngine digitalTwinEngine = new DigitalTwinEngine();

            // Add the Digital Twin to the Engine
            digitalTwinEngine.addDigitalTwin(digitalTwin);

            // Set a new Event-Logger to a Custom One that we created with the class 'DemoEventLogger'
            WldtEventBus.getInstance().setEventLogger(new DemoEventLogger());

            // Start all the DTs registered on the engine
            digitalTwinEngine.startAll();

        }catch (Exception e){
            e.printStackTrace();
        }
    }
}
```