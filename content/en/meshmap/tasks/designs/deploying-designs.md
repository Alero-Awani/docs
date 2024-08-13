---
title: Deploying Designs
description: >
    Each Meshery design is deployable to one or more Kubernetes clusters.
weight: 4
categories: [Designer]
tags: [designs]
---

At this stage, you deploy your resources to your available Kubernetes cluster connection(s) managed by Meshery.
First, ensure the connections to your clusters are established and configured correctly, placing them in the appropriate environments. This ensures you have control over your deployment strategy.

## Kubernetes Cluster Management using Meshery

Meshery Server [deploys](https://docs.meshery.io/installation) as a single container. Whether the Meshery Server container is deployed in a stand-alone Docker host or inside a Kubernetes cluster, Meshery Server is fully capable of **managing multiple Kubernetes clusters**. For more information on how Meshery Server connects to and continually synchronizes with your Kubernetes cluster(s), see [Meshery Operator](https://docs.meshery.io/concepts/architecture/operator) and [MeshSync](https://docs.meshery.io/concepts/architecture/meshsync).

{{% pageinfo %}}

## Understanding Meshery Operator and Kubernetes Cluster Relationships

**One-to-One Relationship**: There is a one-to-one relationship between a Meshery Operator and a Kubernetes cluster. This means each Meshery Operator is associated with exactly one Kubernetes cluster. This applies whether the cluster is a managed cluster (like the one you’re adding as a connection) or the cluster where the Meshery Server is deployed.

**Many-to-One Relationship**: There is a many-to-one relationship between Meshery Operator and Meshery Server. Multiple Meshery Operators can be associated with a single Meshery Server. This means a single Meshery Server can manage several Kubernetes clusters through different Meshery Operators.

In summary, while each Kubernetes cluster has its own Meshery Operator, a single Meshery Server can interact with multiple Kubernetes clusters through these Operators.
{{% /pageinfo %}}

## Available Clusters

{{% pageinfo %}}
Users of Meshery Playground should see a pre-registered Kubernetes connection, representing the sandbox cluster available with the playground environment.
{{% /pageinfo %}}

You have the option of using the live cluster provided by Meshery Playground or connecting your own Kubernetes cluster using your kubeconfig file. During deployment, these clusters will be available as connections for you to select.

## Deploying Designs

1. To deploy a design, navigate to the Actions button at the top of the Design canvas.
1. Click on the **Deploy** icon.
1. This opens a modal that will take you through all the steps before the final deployment.
1. Click on **Open In Visualizer** to see the pre-filtered view of the deployed resources in the cluster.
1. Click **Finish**.

    ![Success](/meshmap/getting-started/images/success-deploy.png)

## Deployment Errors

1. **Missing Namespace**: This error occurs when you attempt to create a Kubernetes resource without specifying a namespace. Kubernetes requires that all resources have an associated namespace.

    ![Missing Namespace](/meshmap/getting-started/images/missing-ns.png)

1. **Empty Label Selector**: This error indicates an empty label selector.

    ![Empty Label Selector](/meshmap/getting-started/images/empty-ls.png)

## Troubleshooting Errors

When reviewing validation, dry run, or deployment issues, you’ll notice specific error codes denoted from time to time.

As a system, Meshery itemizes different errors that occur and assigns a unique error code to each along with details on how to remediate the issue at hand.

For the comprehensive list of error codes refer to [Error Code Reference](https://docs.meshery.io/reference/error-codes) in the Meshery documentation.

If you encounter persistent issues consider consulting the [Meshery Community forum](https://discuss.layer5.io/c/meshery/5).

  ![Empty Label Selector](/meshmap/getting-started/images/error-code.png)

## Using the Notification Center for Troubleshooting

The Notification Center in Meshery helps manage events during the deployment process. It provides real-time updates and alerts on the status of the deployment. This feature can be particularly useful for troubleshooting, as it:

1. Displays immediate feedback on the success or failure of each deployment step.

1. Highlights specific error messages and codes, helping you quickly identify and understand issues.

1. Offers links to detailed documentation and guides for resolving common problems.

1. Keeps a log of past notifications, allowing you to track and review previous errors and their resolutions.

    ![Notification Center](/meshmap/getting-started/images/notification.png)

    ![Notification Center](/meshmap/getting-started/images/notification-center.png)

By actively monitoring the Notification Center, you can promptly address issues as they arise, ensuring a smoother deployment process. Learn more about [Managing Events with the Notification Center](https://docs.meshery.io/guides/events-management).
