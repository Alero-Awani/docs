---
title: Validating Designs
description: >
  Prior to deploying a design, you can validate the configuration that it contains in accordance with the target platform.
weight: 2
categories: [Designer]
tags: [designs]
---

Validation is the first step in deploying designs with Meshery. While optional, it is highly recommended as it helps identify and resolve possible misconfigurations upfront.

## How Validation Works

Meshery uses static analysis to verify your design. It checks all components within your design and all configured and unconfigured properties of your components against well-defined schemas based on [Meshery Models](https://docs.meshery.io/concepts/logical/models).

This comprehensive validation ensures that:

1. The design adheres to the expected structure and format.
1. All components are valid and recognized by Meshery.
1. There are no missing required configurations.

## Performing Validation

1. To validate your design, navigate to the Actions button at the top of the Design canvas.

1. Click on the **Validate** Icon.

    ![Performing Validation](/meshmap/getting-started/images/performing-validation.png)

    If the validation is successful, you will see a modal displaying the number of components validated and the number of annotations, similar to the one shown below:

    ![Successful Validation](/meshmap/getting-started/images/successful-validation.png)

## Handling Validation Errors

If your design fails validation checks, the modal will indicate the number of errors detected. Each error will provide specific information about the component or annotation that caused the failure. Use this detailed feedback to identify and correct the issues in your design before proceeding with the deployment.

### Validation Errors

A common validation error is:

1. **Missing Required Field**: This happens when a required field is not provided. For example, in the image below, the first error indicates that the field ".spec.template.spec.containers.0.env.0" must have a value.

    ![Validation Errors](/meshmap/getting-started/images/validation-error.png)

To troubleshoot and remediate validation issues:

1. Click on the error on the modal.
1. This will open the configuration tab of the component that has that error.
1. Fix the configuration using the error details provided.
1. Re-run validation after any significant changes to your design to ensure all issues are resolved.

The validation process is confined to schema-based checks within Meshery and does not require communication with your target environment. The Dry Run step, however, does involve this communication. Let’s explore the Dry Run step next.
