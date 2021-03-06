# PKCS11 bindings for PHP

Work in progress. DO NOT USE!

Tested with the following HSMs:
* SafeNET Luna SA 4
* SoftHSM 2.6

Currently supports:

* C_Initialize (via new PKCS11\Module())
* C_GetInfo
* C_GetSlotList
* C_GetSlotInfo
* C_GetTokenInfo
* C_InitToken
* C_GetMechanismList
* C_GetMechanismInfo
* C_OpenSession
* C_Login
* C_Logout
* C_InitPIN
* C_SetPIN
* Generating keys (C_GenerateKey, C_GenerateKeyPair)
* Retrieving keys and properties (C_FindObjectsInit, C_FindObjects, C_FindObjectsFinal, C_GetAttributeValue)
* Encrypt/Decrypt (C_EncryptInit, C_Encrypt, C_DecryptInit, C_Decrypt) Tested with:
  * CKM_AES_CBC_PAD
  * CKM_AES_GCM
  * CKM_RSA_PKCS
  * CKM_RSA_PKCS_OAEP
* EncryptUpdate/EncryptFinal (via EncryptionContext object)
* DecryptUpdate/DecryptFinal (via DecryptionContext object)
* Digest (C_DigestInit, C_Digest)
* DigestUpdate/DigestKey/DigestFinal (via DigestionContext object)
* Signing (C_SignInit, C_Sign, C_VerifyInit, C_Verify) Tested with:
  * CKM_*RSA_PKCS
  * CKM_*RSA_PKCS_PSS
  * CKM_ECDSA
  * CKM_EDDSA
  * CKM_*HMAC
* SignUpdate/SignFinal (via SignatureContext object)
* VerifyUpdate/VerifyFinal (via VerificationContext object)
* Key Wrapping (C_WrapKey, C_UnwrapKey) Tested with 
  * CKM_RSA_PKCS
  * CKM_RSA_PKCS_OAEP
* Deriving (C_DeriveKey) Tested with:
  * CKM_ECDH1_DERIVE (P-256, P-384, P-521, X25519, X448)
* Object Management (C_CreateObject, C_CopyObject, C_DestroyObject)

Upcoming features:
* Pkcs11\Mechanism object to avoid having to pass IV or Mechanism Param object as second argument to action methods
* Include original PKCS11 functions as Method Aliases on the Pkcs11\Module object
