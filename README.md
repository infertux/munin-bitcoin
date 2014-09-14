# Munin plugins for Bitcoin Core

## Installation & Configuration

1. Copy the `bitcoind_*` scripts to `/etc/munin/plugins`.

1. If you're using SELinux, don't forget to `chcon` them properly.

1. Configure the plugins by creating a file named `/etc/munin/plugin-conf.d/bitcoind` with this content:

    ```
    [bitcoind*]
    user bitcoin
    ```

    This will tell Munin to run `bitcoin-cli` as the `bitcoin` user. Adapt it to your setup and avoid using `root`.

1. Restart the *munin-node* daemon with `systemctl restart munin-node` or `/etc/init.d/munin-node restart`.

1. Done. You should now start to see a new section *bitcoind* in your Munin pages with the corresponding graphs.

## License

AGPLv3+

