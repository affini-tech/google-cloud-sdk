# google-cloud-sdk

Get the cloud sdk image:
```sh
$ docker pull affinitech/google-cloud-sdk
```

Auth & save the credentials in gcloud-config volumes:
```sh
$ docker run -t -i --name gcloud-config affinitech/google-cloud-sdk gcloud init
```

If you would like to use service account instead please look here:
```sh
$ docker run -t -i --name gcloud-config affinitech/google-cloud-sdk gcloud auth activate-service-account <your-service-account-email> --key-file /tmp/your-key.p12 --project <your-project-id>
```

Re-use the credentials from gcloud-config volumes & run sdk commands:
```sh
$ docker run --rm -ti --volumes-from gcloud-config affinitech/google-cloud-sdk gcloud info
```
