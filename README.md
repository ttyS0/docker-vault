# docker-vault

This closely tracks https://github.com/hashicorp/docker-vault/tree/c9a1e0087e0e91c1c276290ef34950f81cb7174e.

The primary modifications are version numbers, since I'm impatient and don't want to wait for Docker Hub to update.

---
# Vault Official Image Build

The version of this hosted on [HashiCorp's Docker Hub for Vault](https://hub.docker.com/r/hashicorp/vault/)
is built from the same source as the [Vault Official Image](https://hub.docker.com/_/vault/).

There are several pieces that are used to build this image:

* We start with an Alpine base image and add CA certificates in order to reach
  the HashiCorp releases server. These are useful to leave in the image so that
  the container can access Atlas features as well.
* Finally a specific Vault build is fetched and the rest of the Vault-specific
  configuration happens according to the Dockerfile.
