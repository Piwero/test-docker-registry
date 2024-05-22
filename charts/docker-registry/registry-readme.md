To create a Kubernetes Secret declaratively for the given Docker registry credentials, you can use the following YAML manifest:
`apps/registry-secret.yaml`

You will need to encode the  `.dockerconfigjson`  field with the Docker registry credentials in base64 format. Here's how you can encode the Docker registry credentials:

1. Create a JSON file with the Docker registry credentials: `apps/docker-registry/config.json`

2. Replace  `BASE64_ENCODED_USERNAME_PASSWORD`  with the base64 encoding of  `username:password` . For example, if  `testuser:testpassword`  is base64 encoded, it would be  `ewogICJhdXRocyI6IHsKICAgICJyZWdpc3RyeS5waXdlcm8uY29tIjogewogICAgICAidXNlcm5hbWUiOiAidGVzdHVzZXIiLAogICAgICAicGFzc3dvcmQiOiAidGVzdHBhc3N3b3JkIiwKICAgICAgImVtYWlsIjogInBpd2Vyb0BnbWFpbC5jb20iLAogICAgICAiYXV0aCI6ICJCQVNFNjRfRU5DT0RFRF9VU0VSTkFNRV9QQVNTV09SRCIKICAgIH0KICB9Cn0K` .

3. Encode the JSON file to base64:
`cat config.json | base64`

5. Replace  `BASE64_ENCODED_STRING`  in the Kubernetes Secret manifest with the output from step 3.

After updating the manifest with the correct base64 encoded string, you can apply the YAML manifest using  `kubectl apply -f secret.yaml`  to create the Kubernetes Secret for the Docker registry credentials.
