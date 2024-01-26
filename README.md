# viem-kms-signer

This is a wallet or signer that can be used together with [Viem](https://viem.sh/) applications.

## Getting Started

```ts
import { KmsSigner } from 'viem-kms-signer';

const kmsCredentials = {
  accessKeyId: 'AKIAxxxxxxxxxxxxxxxx', // credentials for your IAM user with KMS access
  secretAccessKey: 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx', // credentials for your IAM user with KMS access
  region: 'us-east-1',
  keyId:
    'arn:aws:kms:us-east-1:123456789012:key/123a1234-1234-4111-a1ab-a1abc1a12b12',
};
const signer = new KmsSigner(kmsCredentials);

// Returns a custom viem account instance
const account = await signer.getAccount();
```

## License

MIT © [Jack Chuma](https://github.com/jackchuma)

## Credits

- A significant portion of code was inspired by RJ Chow's work published at https://github.com/rjchow/ethers-aws-kms-signer.
- Utmost credit goes to Lucas Henning for doing the legwork on parsing the AWS KMS signature and public key asn formats: https://luhenning.medium.com/the-dark-side-of-the-elliptic-curve-signing-ethereum-transactions-with-aws-kms-in-javascript-83610d9a6f81
