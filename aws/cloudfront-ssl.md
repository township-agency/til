# Uploading custom SSL Cert to AWS / Cloudfront

If you have your own SSL Cert, and you're trying to use Cloudfront (with S3 or otherwise), you have to manually upload your cert via the command line. 

Here's the command:

```
aws iam upload-server-certificate --server-certificate-name [name for cert] \
    --certificate-body file://[cert file].crt \
    --private-key file://[cert file].key \
    --certificate-chain file://[chain file, or "bundle"].pem
    --path /cloudfront/
```

A couple gotchas that took me _hours_ to figure out. 

- I've always needed the `file://` prefix, not entirely sure why, but this same file will fail otherwise
- `--path` is needed to tell IAM you need this for `/cloudfront/`
- Your name for the cert does not need to be sensitive to the file contents/names
- The chain file was downloaded from my DNS provider, it was not included in the bundle from the SSL provider

## Fixing any mistakes

I've done this twice, and both times I've done it, I forgot the `--path` option. Cloudfront/AWS (from what I can tell) will not be able to find the cert if you don't provide this option. 

To correct this mistake, you can update the cert. You _have_ to provide the name of the cert, *and* the option names are not the same, they're prefixed with `new`. In my case, I followed up my mistake with this command:

```
aws iam update-server-certificate --server-certificate-name [name of cert] \ 
    --new-path /cloudfront/
```

... and all was gravy.
