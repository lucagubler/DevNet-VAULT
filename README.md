# HashiCorp Vault Setup for the Cisco Certified DevNet Expert Exam
This repository provides a quick setup for HashiCorp Vault. This is essential if you're preparing for the Cisco Certified DevNet Expert exam. With Docker Compose, you can easily launch a Vault instance to secure your applications and manage secrets.

## Quick Start

Ensure you have Docker and Docker Compose installed on your machine. Then, follow these steps:

1. Execute `docker-compose up -d` to start the Vault.
2. Verify it using `docker ps -a`.
3. Visit `https://localhost:8200`.

## Environment Variables

Before using the Vault CLI, set the following environment variables:

```bash
export VAULT_ADDR=https://127.0.0.1:8200
export VAULT_CACERT=<absolute_path_to_repo>/certs/vault.crt
export VAULT_TOKEN="s.wkFzpK95G7g5B6kh9myEBMM6"
```

**Note:** Adjust the `VAULT_CACERT` path to match your local repository location. The `VAULT_TOKEN` should be set to your root token obtained after initializing Vault.

## Basic Commands

### Check Vault Status

```bash
vault status
```

Example output:
```
Key             Value
---             -----
Seal Type       shamir
Initialized     true
Sealed          false
Total Shares    1
Threshold       1
Version         1.8.0
Build Date      n/a
Storage Type    file
Cluster Name    vault-cluster-ebf0f42f
Cluster ID      732ffdf5-3f6b-a55e-72fd-e81d202a4415
HA Enabled      false
```

### Initialize Vault

If Vault is not initialized, run:

```bash
vault operator init
```

This will output unseal keys and an initial root token. **Save these securely!**

### Unseal Vault

If Vault is sealed, unseal it using:

```bash
vault operator unseal <unseal-key>
```

For a single unseal key setup, you'll need to run this once.

## Support
For any issues or questions, feel free to open an issue in this repository.

## Become an Expert
In my [DevNet Expert e-learning](https://devnet-academy.com) HashiCorp Vault is covered extensively. Learn everything from creating secrets to writing custom Python applications using the hvac library.
