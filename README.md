
1) Digital Signature:
•	Generate DSA Key Pair
•	dsa.generate_private_key(key_size=2048) creates a 2048-bit private key.
•	The corresponding public key is derived using private_key.public_key().
•	Sign a Message
•	private_key.sign(message, hashes.SHA256()) produces a digital signature for the given message using the SHA-256 hash.
•	Verify the Signature
•	public_key.verify(signature, message, hashes.SHA256()) checks whether the signature is valid for the message.
•	If verification passes → prints "Signature is valid ✅"
•	If verification fails → prints an error message.


 IPsec (Internet Protocol Security):
This code simulates the core functionality of IPsec at a conceptual level:
•	Message Preparation: Takes a Greek text message and encodes it in UTF-8.
•	Key & IV Generation: Randomly generates a 128-bit AES key and 16-byte IV.
•	Encryption (ESP-like): Uses AES in CBC mode to encrypt the message, ensuring confidentiality.
•	Integrity & Authentication (AH-like): Computes an HMAC-SHA256 over the ciphertext to verify integrity and authenticity.
•	Decryption & Verification:
•	First, verifies the HMAC to ensure the data hasn’t been tampered with.
•	Then decrypts the ciphertext to recover the original message.


 X.509:
•	Generate a Private Key
•	Creates a 2048-bit RSA private key for signing the certificate.
•	Define Subject and Issuer
•	Sets certificate details like country, state, locality, organization, and common name.
•	Since it’s self-signed, the issuer is the same as the subject.
•	Build the Certificate
•	Uses x509.CertificateBuilder() to define the certificate’s:
	Public key
	Serial number
	Validity period (1 year)
	Optional extensions (e.g., Subject Alternative Name).
•	Sign the Certificate
•	Signs the certificate with the generated private key using SHA-256.
•	Save to Files
•	Writes the certificate to certificate.pem.
•	Writes the private key to private_key.pem.


X.509 Version 3 (v3):
 An enhanced version of X.509 that supports extensions such as key usage, alternative names, policies, and constraints.
 Widely used in SSL/TLS certificates for secure web communication.


