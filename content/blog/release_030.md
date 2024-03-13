---
title: "WLDT Library Version 0.3.0"
description: "Introducing WLDT Library Version 0.3.0"
summary: ""
date: 2024-03-13T16:27:22+02:00
lastmod: 2024-03-13T16:27:22+02:00
draft: false
weight: 50
images: []
categories: []
tags: []
contributors: []
pinned: false
homepage: false
---

:mega: We're thrilled to announce the release of version 0.3.0 of the White Label Digital Twins (WLDT) library! 
This release brings significant enhancements, improvements, and new features to further empower developers in designing, developing, and deploying Digital Twins within Internet of Things (IoT) ecosystems.

For detailed information about these changes and their impact, please refer to the information provided: 

- [Official Changelog](/docs/change-logs/change-log-0.3.0/)
- [Official Documentation](/docs/introduction/library-structure-basic-concepts/)

Let's dive into the key changes and updates included in this release:

## Migration Digital Adapters

In version 0.3.0, we've made several enhancements and adjustments to the Digital Adapter class to improve its functionality and usability. Notable changes include:

- Discontinued Methods: Several methods have been discontinued and removed from the DigitalAdapter class to streamline its interface and improve clarity.
Method Signature Changes: The signatures of certain methods have been updated for consistency and clarity, ensuring a more intuitive developer experience.
- New Methods: We've introduced new methods to provide additional functionality and flexibility for handling state updates and event notifications.

## Migration Shadowing Function

We've made significant improvements to the ShadowingModelFunction, which is now renamed to ShadowingFunction. Additionally, we've introduced changes to how the DigitalTwinState is managed within the Shadowing Function, providing developers with more control and flexibility.

## Migrating WLDT Engine & DT Creation

In version 0.3.0, the WldtEngine class has been renamed to DigitalTwin, offering improved clarity and consistency. We've also made adjustments to the lifecycle management of Digital Twins, streamlining the process and enhancing usability.

## Digital Twin & Digital Twin Engine

We've introduced enhancements to the Digital Twin and Digital Twin Engine classes, providing developers with improved functionality and ease of use. Notable updates include:

- Simplified Digital Twin Creation: Creating and managing Digital Twins is now more intuitive and streamlined.
- Lifecycle Management: We've enhanced the lifecycle management of Digital Twins, making it easier to start, stop, and manage multiple instances.

## Digital Twin State Manager

The DigitalTwinStateManager class has been improved to provide better support for managing the state of Digital Twins. With features such as transaction support and event notification, developers can more effectively manage changes to Digital Twin states and respond to events.

To learn more about the capabilities of the DigitalTwinStateManager, please refer to the Digital Twin State Manager section.

## Digital Adapter

We've extended and improved the Digital Adapter base class to provide enhanced support for handling Digital Twin state updates and event notifications. With the introduction of the onStateUpdate and onEventNotificationReceived methods, developers can more effectively respond to changes in Digital Twin states and events.

## Get Started with WLDT 0.3.0

To get started with version 0.3.0 of the WLDT library, simply update your dependencies to include the latest release. Detailed documentation and usage examples are available in the project repository, providing comprehensive guidance on leveraging the new features and enhancements.

We're excited about the improvements and new capabilities introduced in WLDT 0.3.0, and we can't wait to see how developers utilize them to create innovative IoT solutions powered by Digital Twins. As always, we welcome your feedback and contributions to help us further improve the library and empower the community.

Happy coding with WLDT 0.3.0! :rocket: