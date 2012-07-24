# Encryption bundle

The encryption bundle will cause every document and index to be encrypted before written to disk, meaning the raw document data is never written to disk unencrypted.

## Important note

You must backup your encryption key. It cannot be restored in any way whatsoever if it is lost.

## Installation

The encryption bundle must be installed on a clean database; the encryption key cannot be changed on a database, and the encryption bundle cannot be removed - to change anything, all data must be copied to a different instance of RavenDB.

To install, put Raven.Bundles.Encryption.dll in the server's Plugins directory. Then set the encryption key, and you may start using your new database. The settings should never be changed after the database has been started.

## Settings

* `Raven/Encryption/Key` - the encryption key, in base 64. If this setting does't exist, the database will not start, but the exception message will suggest a cryptographically random key to use here.
* `Raven/Encryption/Algorithm` (optional) - this is the full typename for an encryption algorithm to use. It must be a class derived from System.Security.Cryptography.SymmetricAlgorithm, with a parameterless constructor. The default value is System.Security.Cryptography.AesManaged.
* `Raven/Encryption/EncryptIndexes` (optional) - if false, indexes will not be encrypted. By default this is set to true.
