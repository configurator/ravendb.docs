# Compression bundle

The compression bundle will cause every document to be compressed before written to disk.

## Installation

The compression bundle may be installed on a pre-existing database, but may not be removed from one.

To install, simply put Raven.Bundles.Compression.dll in the server's Plugins directory. New documents will be compressed before written to disk, as well as old documents as soon as they are changed. Old documents which are not rewritten will not be compressed.