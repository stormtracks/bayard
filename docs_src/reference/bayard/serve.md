# bayard serve

The `bayard serve` CLI starts the server.

## USAGE

    bayard serve [OPTIONS]

## FLAGS

    -h, --help       Prints help information.
    -v, --version    Prints version information.

## OPTIONS

    -i, --id <ID>
            Server ID. Must specify a numeric ID that is unique within the cluster. If not specified, use the default
            ID. [default: 1]
    -H, --host <HOST>
            Host address. Must specify the host name or IP address. If not specified, use the default address. [default:
            0.0.0.0]
    -P, --port <PORT>
            Port number. This port is used for communication via gRPC. If not specified, use the default port. [default:
            5000]
    -p, --peers <ID=IP:PORT>...
            Server ID and addresses in an existing cluster separated by ",". If specified, the server will join the
            cluster.
    -d, --data-directory <DATA_DIRECTORY>
            Data directory. Stores index, snapshots, and raft logs. If not specified, use the default directory.
            [default: ./data]
    -s, --schema-file <SCHEMA_FILE>
            Schema file. Must specify An existing file name. If not specified, use the default schema file. [default:
            ./etc/schema.json]
    -t, --indexer-threads <INDEXER_THREADS>
            Number of indexer threads. If not specified, number of CPU cores - 1 will be used. [default: 7]

    -m, --indexer-memory-size <INDEXER_MEMORY_SIZE>
            Total memory size (in bytes) used by the indexer. It will be split for the different thread. If not
            specified, use the default. [default: 1000000000]

## EXAMPLES

To start a server with default options:

```text
$ ./bin/bayard serve
```

To start a server with options:

```text
$ ./bin/bayard serve \
      --id=1 \
      --host=0.0.0.0 \
      --port=5001 \
      --data-directory=./data/1 \
      --schema-file=./etc/schema.json
```
