# AsciiArtify Minimum Viable Product

## About the product

AsciiArtify application allows to convert any image into Ascii graphics using web-interface. User uploads image to service, where it's processed and output is provided in form of ASCII text.

## Technical realisation

Solution is built using Kubernetes (k3d is used for MVP) and ArgoCD. ArgoCD is responsible for continuous delivery of AsciiArtify's code into Kubernetes cluster.

Installation details can be found in [POC](POC.md), just MVP will have AutoSync option enabled. 


## Implementation and testing 

Implementaiton session is recorded using asciinema and can be seen here:

![Rollout](rec1.gif)

It also includes small test to demonstrate application's functionality.


## Scaling a deployment

Scaling can be done manually by changing required number of replicas in file `helm/values.yaml`

For example, let's change value from 1 to 2 for service front. ArgoCD after some time discovers change in repository, downloads latest version and applies new configuration:

![Scaling](rec2.gif)