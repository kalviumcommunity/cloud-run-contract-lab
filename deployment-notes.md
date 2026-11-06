# Deployment interpretation

Correct each claim and give a one-sentence reason. Do not create cloud resources.

1. Local Docker success proves this app has been deployed to Cloud Run.
2. Cloud Run always uses port 8080 and cannot be configured differently; EXPOSE makes the app listen there.
3. A service, revision and container instance are three names for the same object.
4. `gcloud run deploy --image IMAGE_URL` uploads and builds my local source directory, just like `--source .`.
5. An HTTPS service URL guarantees anonymous access; ingress, caller authorization and runtime service identity are the same setting.
6. A ready revision guarantees every business endpoint works, every new revision always receives all traffic, and rollback undoes database writes.
7. Setting minimum instances to zero guarantees the whole deployment costs nothing and needs no billing account.
