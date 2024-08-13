---
title: Design Dry Run
description: >
  Simulate the deployment of your design in a selected target environment _without_ making any actual changes.
weight: 3
categories: [Designer]
tags: [designs]
---

## Design Dry Run

A dry run in Meshery simulates the deployment of your design in the selected target environment _without_ making any actual changes. This step is highly beneficial as it helps identify potential issues before they occur, ensuring a smoother and more reliable deployment process.

## Performing Dry Run

1. Navigate to the **Actions** button at the top of the Design canvas.
1. Click on the **Dry Run** icon.
1. Review the results to identify any potential issues.
1. Make necessary adjustments to your configuration based on the feedback provided by the dry run.
1. Re-run the dry run to ensure all issues have been resolved.

    ![successful Dry Run](/meshmap/getting-started/images/successful-dry-run.png)

## Examples of Dry Run Errors

Some examples of dry run errors are:

1. **Invalid Field Value**: The error message indicates that a field has an invalid value. For instance, in the image below, the fields "spec > ports[0] > port" and "spec > ports[0] > targetPort" have invalid values of 0. These values must be between 1 and 65535, inclusive.

    ![Invalid Field Value](/meshmap/getting-started/images/dr-invalid-field1.png)

    ![Invalid Field Value](/meshmap/getting-started/images/dr-invalid-field2.png)

1. **Missing Required Field**

    ![Missing Required Field](/meshmap/getting-started/images/missing-field.png)

1. **Missing Dependencies**: In this case, the error occurs because a Kubernetes [Custom Resource Definition](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/) (CRD) should have been deployed first before attempting to deploy this component.

    To resolve this, ensure that all necessary dependencies, such as CRDs, are deployed before deploying the components that rely on them.

    ![Missing Resource](/meshmap/getting-started/images/missing-resource.png)