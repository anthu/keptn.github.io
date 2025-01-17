---
date: "2021-04-22T09:31:37+02:00"
title: "keptn trigger delivery"
slug: keptn_trigger_delivery
---
## keptn trigger delivery

Triggers the delivery of a new artifact for a service in a project

### Synopsis

Triggers the delivery of a new artifact for a service in a project.
An "artifact" is the name of a Docker image which can be located at any Docker registry (e.g., DockerHub or Quay).
The new artifact is pushed in the first stage specified in the Shipyard of the project. Afterwards, Keptn takes care
of deploying the artifact to the other stages as well.

Note: The value provided in the --image flag has to contain the full qualified image name (incl. docker registry).
The only exception is "docker.io", as this is the default in Kubernetes.
For pulling an image from a private registry, we would like to refer to the Kubernetes documentation (https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/).


```
keptn trigger delivery [flags]
```

### Examples

```
keptn trigger delivery --project=<project> --service=<service> --image=<image> --tag=<tag> [--sequence=<sequence>]
```

### Options

```
      --image string            The image name, e.g.
                                "docker.io/<YOUR_ORG>/<YOUR_IMAGE> or quay.io/<YOUR_ORG>/<YOUR_IMAGE>
                                "Optionally, you can append a tag using ":<YOUR_TAG>
  -l, --labels stringToString   Additional labels to be included in the event (default [])
  -o, --output string           Output format for the --watch flag. One of: json|yaml
      --project string          The project containing the service for which the new artifact will be delivered
      --sequence string         The name of the sequence to be triggered (default "delivery")
      --service string          The service which for which the new artifact will be delivered
      --stage string            The stage containing the service for which a new artifact will be delivered
      --tag string              The tag of the image. If no tag is specified, the "latest" tag is used
      --values strings          Values to use for the new artifact to be delivered
  -w, --watch                   Print event stream
      --watch-time int          Timeout (in seconds) used for the --watch flag (default 2147483647)
```

### Options inherited from parent commands

```
  -h, --help               help
      --mock               Disables communication to a Keptn endpoint
  -n, --namespace string   Specify the namespace where Keptn should be installed, used and uninstalled in (default "keptn")
  -q, --quiet              Suppresses debug and info messages
  -v, --verbose            Enables verbose logging to print debug messages
  -y, --yes                Assume yes for all user prompts
```

### SEE ALSO

* [keptn trigger](../keptn_trigger/)	 - Triggers the execution of an action in keptn

###### Auto generated by spf13/cobra on 22-Apr-2021
