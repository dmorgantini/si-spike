# Overview

The test hub is a service, supported by the Ida Delivery Team, that supports saml interoperability testing with all integrating partners for the GDS Hub.  This document is focused on the functionality and operating of the test hub for rps.

The Test Hub relying party functionality has a fundamentally different approach than the Test Hub identity provider functionality.  As the testing is meant to focus on SAML integration, the Test Hub provides a mechanism for the RPs to send a number of different canned responses to their service.  The Test Hub ignores all interactions with the Matching Service and instead, using the information provided in the initial post, generates the assertion that would be provided by the matching service. There will be a separate bit of Test Hub functionality that will support the Matching Service SAML integration.

In order to support this, the RP needs to send all the pieces of information required to generate a response to the Test Hub via a JSON post.  These details include: entity id, assertion consumer service url, signing public certificate, encryption public cert, expected pid, matching service entity id and matching service signing private certificate.  Note that this data is persisted in memory which means that until the next deployment, you don't need to resubmit this data.  I'd suggest that you consider resubmitting the data for each test run, but not between each test case.

## Introduction

The test hub is a service, supported by the Ida Delivery Team, that supports saml interoperability testing with all integrating partners for the GDS Hub.  This document is focused on the functionality and operating of the test hub for rps.

[More reading](https://github.com/dmorgantini/blog-post/blob/master/test-hub-for-rp.md)
