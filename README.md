# What is XMR-AEON-CPU?

XMR-AEON-CPU is a universal Stratum pool miner. This is the CPU-mining version.

## Links

- [Discussion](https://www.reddit.com/r/Monero/comments/5lsfgt/xmrstakcpu_high_performance_open_source_miner/)
- [Source Code](https://github.com/IndeedMiners/xmr-aeon-stak)
- [Dockerfile](https://github.com/EmbeddedAndroid/docker-xmr-aeon-cpu)

# How to use this image

## Configuration file

Create `config.txt` `cpu.txt` and `pools.txt` configuration files and adapt to your need before running.
You can copy file from a container:

```console
$ docker run -d --name some-xmr-stak-cpu-config mineblocks/xmr-aeon-cpu
$ docker cp some-xmr-stak-cpu-config:/cpu.txt .
$ docker cp some-xmr-stak-config:/config.txt
$ docker cp some-xmr-stack-pool-conifg:/pool.txt
$ docker stop some-xmr-stak-cpu-config
$ docker rm some-xmr-stak-cpu-config
```

or copy example from [GitHub](https://github.com/fireice-uk/xmr-stak-cpu/blob/v1.1.0-1.1.0/config.txt).

## Running

Run in background:

```console
$ docker run -dit --privileged --name some-xmr-stak-cpu -p 9090:9090 -v /home/user/pools.txt:/pools.txt -v /home/user/cpu.txt:/cpu.txt -v /home/user/config.txt:/config.txt mineblocks/xmr-aeon-cpu
```

Use `--privileged` option for large pages support. Large pages need a properly set up OS.

Fetch logs of a container:

```console
$ docker logs some-xmr-stak-cpu
```

Attach:

```console
$ docker attach some-xmr-stak-cpu
```

This variant has no donation fee.

# Donations

Donations for work on dockerizing are accepted at:

- BTC: `32L1B2a2nMhSqCJX7eSBnDu1E3cDyCPdbM`
- XMR: `493q7wHvUfhTRk9JMopZVxFFWDNowZkqkRWpMZdbTyRSepzfMjRau6g2JpS9QaRDZ55gJ11wtJTmF1nhEYxUqePu7VhXpLB`
- XHV: `hvxxxQSefQZ8vj279PnKRparKjVFvxxjNSMpftzKLT8QUKEzKxzsgYmSy3kFSgmEEMJStLTs1aiXtQVK5V5wo7zz79RNHT9AWk`
