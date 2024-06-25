# NHS-England-FHIR-Examples
This repository is maintained by [Interoperability Team](https://nhsd-confluence.digital.nhs.uk/pages/viewpage.action?spaceKey=IOPS&title=Interoperability+Standards). Any queries contact us via [email](interoperabilityteam@nhs.net).

This repository will be used to contain FHIR assets and examples for NHS England Programme Implementation Guides [Simplifier project](https://simplifier.net/NHS-England-Programme-Implementation-Guides/~guides).

## Programmes Information

Ths repository contains the FHIR Assets and examples for multiple programmes and any ammendments to this repo can be done via Pull Requests.  

To create a Pull Request, first [fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo) this repo, make the changes necessary and create a [Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) with the base being this repository.
All PRs will be validated, and approved by the Interoperability team before merging.
- Changes to ValueSets and CodeSystems and examples will be approved by a member of the Interoperability team.
- Changes any other asset will be taken to the Interoperability Standards team Design Authority meeting to be discussed before approving.

## CapabilityStatement
The CapabilityStatement is used by the validation tool to check which profile to validate against. If no Profile is stated then the base FHIR resource will be used.

## FHIR Validation

This repo uses the customised HAPI FHIR Validation to ensure all assets and examples are valida FHIR, including any codes held within the ontoology server.  

More information on FHIR validation can be found on the Interoperability Standards team [Confluence page](https://nhsd-confluence.digital.nhs.uk/display/IOPS/FHIR+Conformance+and+Testing)  
More information on the FHIR validation service can be found within the Interoperability Standards team [IOPS-Test-Scripts](https://github.com/NHSDigital/IOPS-FHIR-Test-Scripts) repository.  

To set up the validation service within a fork add the following secrets:
- ONTO_CLIENT_ID
- ONTO_CLIENT_SECRET

## Package Creation (in development)
- Create a new branch named package-*[programme]*
- Within the branch remove any unneccessary assets
- amend the package.json (mandatory)
  - name: uk.nhsengland.r4*[programme]*
  - description: NHS England *[programme]* FHIR Implementation Guide. *[Optional: More information, such as "for validation purposes only"]*
  - version: semantic versioning, e.g. 0.0.1 
- Go to Actions and within the left hand pane named "Actions" "All Worflows" select [Create FHIR Package](https://github.com/NHSDigital/NHSEngland-FHIR-Examples/actions/workflows/createPackage.yml).
  - Click Run workflow button (right hand side)
  - Choose your branch
  - Click Run workflow (green button).
- If successful, go to the [main page](https://github.com/NHSDigital/NHSEngland-FHIR-Examples) and choose your branch
- download the package file [filename].tar.gz and upload to your server, e.g. AWS S3

More information on package creation, along with optional attributes for package.json, see [https://hl7.org/fhir/packages.html](https://hl7.org/fhir/packages.html).
