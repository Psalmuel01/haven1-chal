# Academic Credential Verifier

The Academic Credential Verifier is a smart contract written in Solidity that allows users to submit and verify academic credentials on the blockchain. The contract integrates with `Haven1 Proof of Identity contract` to ensure the authenticity and competency rating of users.

## Features

- **Credential Submission:** Users can submit their academic credentials, including institution, degree, and graduation year.
- **Identity Verification:** Credentials are verified using `Haven1 Proof of Identity contract` to ensure users are not suspended and have a sufficient competency rating.
- **Credential Verification:** The contract owner (presumably an educational institution or trusted entity) can verify submitted credentials.
- **Credential Rejection:** The contract owner can reject credentials that do not meet the verification criteria.
- **Owner Management:** The contract is Ownable, allowing the owner to manage and control the verification process.

## Usage

1. **Constructor:**

   - Initialize the contract by providing the address of the Proof of Identity contract and the initial owner's address.

2. **Submit Credential:**

   - Users can submit their academic credentials using the `submitCredential` function. The submitted credentials will be verified against the Proof of Identity.

3. **Verify Credential:**

   - The contract owner can use the `verifyCredential` function to verify submitted credentials.

4. **Reject Credential:**

   - The contract owner can use the `rejectCredential` function to reject submitted credentials that do not meet the verification criteria.

5. **Query Credential Information:**
   - Users can query information about their submitted credentials, including status and details.

## Custom Errors

- `InvalidGraduationYear`: The submitted graduation year is in the future.
- `IdentitySuspended`: The user's identity is suspended in the Proof of Identity contract.
- `InsufficientCompetencyRating`: The user's competency rating is below the required threshold.
- `InvalidCredentialIndex`: The provided credential index is invalid.
- `CredentialNotPendingVerification`: The credential is not in a pending verification state.

## Events

- `CredentialSubmitted`: Fired when a user successfully submits a new credential.
- `CredentialVerified`: Fired when the contract owner verifies a credential.

## Requirements

- Solidity ^0.8.20
- OpenZeppelin Contracts (Ownable)

## License

This smart contract is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
