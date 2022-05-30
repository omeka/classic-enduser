# Configuring File Storage

Omeka Classic allows administrators to configure how files are stored (both original files uploaded to Omeka Classic and the derivative images Omeka creates itself). For typical users, the default settings are sufficient: files are simply stored the `files` subdirectory of the Omeka installation and served from there by the web server, just like any other file in Omeka.

However, if you want or need to store files in a different location, on a different drive, or even a different server or service, you'll need to do some configuration. The storage system is configured through the Omeka configuration file, `application/config/config.ini`.

Note: storage changes in the configuration get applied immediately, and will affect all operations involving files. If you change storage methods or locations after already working on an Omeka installation for some time, you'll have to take care of moving or copying any pre-existing files to the new location yourself. If you're thinking about using non-standard storage settings, it's often easiest to make that decision up front, before you upload anything.

## Storage Adapters

Omeka's storage system is based on "adapters." An adapter is simply a method for storing and accessing files, and Omeka ships with two adapters out of the box.

The default adapter is the Filesystem adapter, and it just stores files on the local server. If you haven't explicitly chosen an adapter to use, you're using this one, and it's the right choice for most users, especially if you're not sure which you want to use.

The second adapter included with Omeka is the ZendS3 adapter, which uses Zend Framework code for storing files on Amazon's S3 storage service. This is a more complex adapter, and it requires you to sign up for S3, but it can be the right choice if you have constrained local storage and a large set of files to deal with, or just want to store files remotely for whatever reason.

You set the adapter with a line `storage.adapter` in the configuration file. This configuration option accepts the name of an adapter class. For the built-in adapters, the class name will start with `Omeka_Storage_Adapter`, so the Filesystem adapter would be `Omeka_Storage_Adapter_Filesystem`, and the ZendS3 adapter would be `Omeka_Storage_Adapter_ZendS3`. Plugins can add their own adapters too, and the plugin should document for you how it needs to be configured.

Remember, if you don't explicitly choose an adapter (in other words, if you don't have a `storage.adapter` line in your configuration file) then Omeka will use the Filesystem adapter.

## Adapter Options

Each adapter has some options that can be set to change its behavior. These options differ from adapter to adapter. Adapter options are set with `storage.adapterOptions.` lines in the configuration file (for example, to set the `localDir` option for the Filesystem adapter, you'd use a line like this (with a real path instead):

```
storage.adapterOptions.localDir = "/local/path/to/store/files"
```

### Filesystem Adapter Options

#### `localDir`

The directory where files will be stored. If this is not set, the directory
is set to the `files` subdirectory of the Omeka installation by default.
Just like is true for `files` in a normal installation, whatever directory
you choose here must be readable and writable by the local user Omeka
executes as (often, this is the web server user).

For visitors to be able to see the files, they'll need to be served by a
web server. For the default location, this is taken care of automatically,
as Omeka is already served by your web server along with the files in the
Omeka directory (including the `files` subdirectory). When you change
`localDir` to a custom setting, you almost always also need to set `webDir`
(see the next heading).

#### `webDir`

The URL path to the directory given in `localDir`. By default, this is the
root URL for the Omeka installation plus `/files`, to go along with the
default for `localDir`.

Omeka doesn't do anything by itself to serve files, it just stores them
in the specified directory and calculates the URL for them. A web server like
Apache is required to actually serve the files to users, so you'll need to set
up a server to serve the files from your `localDir`. If you choose a `localDir`
that is within the "document root" of a web server you already have set up, you
may be able to do this without any additional reconfiguration.

This option needs to be an absolute URL, like `https://example.com/files` .
Only the URL up to the directory needs to be provided; Omeka will handle the
part of the URL for referring to a specific file and type of file (in other
words, this option is the *prefix* for the file URLs).

### ZendS3 Adapter Options

Unlike the Filesystem adapter, the ZendS3 adapter has several options that are
mandatory and have no default. So, to use this adapter, you must also always
set at least some settings.

The ZendS3 adapter requires you to have an [Amazon S3][3] bucket set up.

#### `accessKeyId`

Your AWS access key ID. If you are unsure about what this is or how to get it,
refer to [Amazon's documentation on credentials][1].

This option is required.

#### `secretAccessKey`

Your AWS secret access key. If you are unsure about what this is or how to get it,
refer to [Amazon's documentation on credentials][1].

This option is required.

#### `bucket`

The name of the S3 bucket to store files in.

This option is required.

#### `expiration`

The number of minutes a URL is valid for.

By default, this is infinite. Omeka will generate plain direct URLs to your files
stored in S3, which means links that work as long as the file is still there. This
requires the bucket to be configured so anonymous users can view the files.

If you instead want to have a locked-down access policy, you can set this setting,
which will cause Omeka to generate pre-signed URLs for files stored in S3. The
effect is that links to files will only be valid for the configured number of
minutes after the URL was created.

#### `endpoint`

The S3 endpoint for the region your bucket is located in.

By default, this is `s3.amazonaws.com`, the endpoint for the US-East (N. Virginia)
region. If you're using a different region, you can set the correct endpoint for it
here. Amazon's documentation lists the [S3 endpoints for different regions][2].

**Note:** The ZendS3 adapter only supports "Version 2" authentication. Regions listed
as "Version 4 only" in the linked table cannot be used with the ZendS3 adapter.

### `forceSSL`

This setting will use HTTPS urls for files stored in S3. It is useful to prevent mixed content errors/warnings when the Omeka site is accessed via HTTPS.

## Setting the Temporary Directory

There is one storage option that is used regardless of the configured adapter:
`storage.tempDir`.

This option takes a local path to the directory Omeka should temporarily store
files in while initially working on them. Omeka copies files here, and also
performs operations like creating thumbnails here. Plugins that work with files
as they're uploaded can also access files in this temporary directory.

By default, this is the system default temporary directory, but on some systems
that directory isn't accessible to Omeka and a different directory needs to be
used. In those cases, set the appropriate path with `storage.tempDir` in the
configuration file.

Omeka needs to be able to read and write in this directory, just like in the
storage `localDir`.

[1]: https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys
[2]: https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region
[3]: https://aws.amazon.com/s3/getting-started/
