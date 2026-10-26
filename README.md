openmrs-distro-bahmni
==================

## Rama `release/chile`

Imagen OpenMRS de Bahmni para Chile. Todo sale de juanjortega: los modulos de Chile (bahmnicore, appointments,
oauth2login, eis-identity, interconsulta, provider-signature) se resuelven desde GitHub Packages de
juanjortega (`distro/pom.xml`, `<repositories>`), y el workflow publica la imagen en
`ghcr.io/juanjortega/openmrs-chile` (etiquetas: la version del artefacto y `latest`). El workflow necesita el secreto `GH_PACKAGES_TOKEN` (token de solo
`read:packages`) para leer los paquetes de los otros repositorios.

`./mvnw clean deploy` command to create artifacts.

This command will attempt to upload & publish artifacts to https://bahmnirepo.thoughtworks.com (maven repository). You will need authorization to upload (your public key needs to be on the server). 

This distribution also includes [FHIR CDSS module](https://github.com/Bahmni/openmrs-module-cdss) and [FHIR Terminology Service Module](https://github.com/Bahmni/openmrs-module-snomed) along with other modules bundled with standard Bahmni.
More details can be found [here](https://bahmni.atlassian.net/wiki/spaces/BAH/pages/3132686337/SNOMED+FHIR+Terminology+Server+Integration+with+Bahmni)