# Key Management Service (KMS)
[On Your console > Key Management](https://console.cloud.google.com/security/kms/keyrings)
Create and manage cryptographic keys

# Features
- Create & Manage cryptographic keys
- Control their use
- API
# Create keys
[On Your console > Key Management > Create Key Ring](https://console.cloud.google.com/security/kms/keyring/create)
- specify Name
- Generate Key
- Specify Key Name
- Protection level: Software (Cryptographic operations are performed in software) or Hardware Security Module (Cryptographic operations are performed in an HSM.)

# Price
You paid for each key you have.
[Full Documentation](https://cloud.google.com/kms/pricing)
# CLI
Create Key: `gcloud kms keys create`
List All Keys: `gcloud kms keys list`
Grant Permission: `gcloud kms 5Kkeys set-iam-policy`
Decrypt: `gcloud kms decrypt`
Encrypt: `gcloud kms encrypt`
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/kms)

