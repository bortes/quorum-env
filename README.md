# quorum-env

A set of services used to deliver a [Quorum](https://github.com/jpmorganchase/quorum) sample environment.

Using _raft consensus_ and [Constellation](https://github.com/jpmorganchase/constellation) as _transaction manager_.

>
> **DO NOT USE THIS IN PRODUCTION, especially the [private key](./node/prv.key) and the definition of the [genesis block](./node/genesis.json).**
>

# hands-on

Just run the componser to execute both **Quorum** and **Constellation**:

```bash
docker-compose up
```

To reproduce a network, we can scale up the _transaction manager_ and _node_. Before, ensure that current node is ready to receiving connections.

In the case, first scale _transaction manager_:

```bash
docker-compose scale tx-manager=2
```

And then the node:

```bash
docker-compose scale node=2
```

# next steps

Expose services behind a reverse proxy.

# more info

[Using a Layer 7 Proxy for Ethereum Blockchain Client’s JSON-RPC Endpoint](https://devblogs.microsoft.com/cse/2017/04/18/using-a-layer-7-proxy-for-ethereum-blockchain/).
