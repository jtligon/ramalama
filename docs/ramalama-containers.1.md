% ramalama-containers 1

## NAME
ramalama\-containers - List all ramalama containers

## SYNOPSIS
**ramalama containers** [*options*]

**ramalama ps** [*options*]

## DESCRIPTION
List all containers running AI Models

## OPTIONS

#### **--format**=*format*

Pretty-print containers to JSON or using a Go template

Valid placeholders for the Go template are listed below:

| **Placeholder**    | **Description**                              |
|--------------------|----------------------------------------------|
| .Command           | Quoted command used                          |
| .Created ...       | Creation time for container, Y-M-D H:M:S     |
| .CreatedAt         | Creation time for container (same as above)  |
| .CreatedHuman      | Creation time, relative                      |
| .ExitCode          | Container exit code                          |
| .Exited            | "true" if container has exited               |
| .ExitedAt          | Time (epoch seconds) that container exited   |
| .ExposedPorts ...  | Map of exposed ports on this container       |
| .ID                | Container ID                                 |
| .Image             | Image Name/ID                                |
| .ImageID           | Image ID                                     |
| .Label *string*    | Specified label of the container             |
| .Labels ...        | All the labels assigned to the container     |
| .Names             | Name of container                            |
| .Networks          | Show all networks connected to the container |
| .Pid               | Process ID on host system                    |
| .Ports             | Forwarded and exposed ports                  |
| .RunningFor        | Time elapsed since container was started     |
| .Size              | Size of container                            |
| .StartedAt         | Time (epoch seconds) the container started   |
| .State             | Human-friendly description of ctr state      |
| .Status            | Status of container                          |

#### **--help**, **-h**
Print usage message

#### **--noheading**, **-n**
Do not print heading

## EXAMPLE

```
$ ramalama containers
CONTAINER ID  IMAGE                             COMMAND               CREATED        STATUS                    PORTS                   NAMES
85ad75ecf866  quay.io/ramalama/ramalama:latest  /usr/bin/ramalama...  5 hours ago    Up 5 hours                0.0.0.0:8080->8080/tcp  ramalama_s3Oh6oDfOP
85ad75ecf866  quay.io/ramalama/ramalama:latest  /usr/bin/ramalama...  4 minutes ago  Exited (0) 4 minutes ago                          granite-server
```

```
$ ramalama ps --noheading --format "{{ .Names }}"
ramalama_s3Oh6oDfOP
granite-server
```

## SEE ALSO
**[ramalama(1)](ramalama.1.md)**

## HISTORY
Aug 2024, Originally compiled by Dan Walsh <dwalsh@redhat.com>