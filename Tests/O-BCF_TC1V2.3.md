## Basic Call

### Test Case: 1

### Variation: 2

Mutual TLS with good server-side certificate bad client-side certificate


#### Description:
This use case tests the OSP-Facing BCF (O-BCF) when providing a basic call.

-   The test system sends messages to and receives responses from the O-BCF's OSP interfaces.

-   The test system receives messages from and sends responses to the O-BCF's ESRP interfaces.

-   The tool will simulate elements on both sides of the O-BCF.

-   The base flow is a call with early media.

#### Interfaces/Functional Elements:

-   OSP-Facing BCF

#### Advance Pre-Conditions:

-   No active calls

-   Configure the BCF to route calls to the corresponding test endpoint.

-   O-BCF TCP port 5061

-   Operator of the device under test to specify what a legal uri for the route header field that will work in the environment.

-   O-BCF System Under Test has been provisioned with a cert traceable to the PCA.

-   I-BCF Side of Test has been provisioned with a cert that is traceable to a CA acceptable to the O-BCF System Under Test and is not expired but is invalid (TBD)  (Left off here on 12/13/2023, someone will need to go back and research this TLS mechanism to finalize the details of this particular pre-condition.


#### Pre-Test Sequence:

-   911 call is sent to an O-BCF by an OSP

-   Fixed origination call

#### Variations:

Variations are described in O-BCF TC1

## Test Message Sequence:

A. I-BCF Side of Test attempts to establish a TLS connection to O-BCF System Under Test on port 5061, using mutual authentication.

B. I-BCF Side of Test verifies that it does not have a TCP connection or the TLS negotiation failed.


#### Test Evaluation Steps:

-   Test evaluation steps are covered within the Test Message Sequence section of this document.

#### Post-Conditions:

-   No call in progress

-   Check logs, errors should be observed

#### Notes:

To do later (agreed 11/29/2023): Add verbs that verify that the system under test outputs the correct log events. This assumes that the test bed will have an interface for capturing log events from the system under test (i.e. Logger Side of Test). Use a unique number for each test verb to show other types of interactions so that we don't make a mess of the diagram.
