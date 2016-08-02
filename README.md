# Ansible Role: cpuminer

 * Deploy [cpuminer](https://github.com/pooler/cpuminer) (`minerd`) to target machines.

 * Ease the process of deploying miners for DEFCOIN and/or other cryptocurrencies.

 * Designed to be deployed to 64-bit Debian hosts. Pull requests to support other hosts are welcome.

## Usage

Minimally, you will need to set the `cpuminer_pool_url`, `cpuminer_pool_username`, and `cpu_pool_password` variables.
Then, add this to your [playbook](https://docs.ansible.com/ansible/playbooks.html) just as you would any other role
and assign hosts to it.

## Variables

### Package Configuration

The `minerd` binary will be downloaded from [cpuminer releases](https://github.com/pooler/cpuminer/releases)
if needed. To use an alternate version, you will need to set both of these variables.

 * `cpuminer_version`: The release version of the upstream `cpuminer` to download.

 * `cpuminer_sha256_checksum`: The SHA256 hash of the release archive (not the `minerd` binary itself).

### System Configuration

The deployed service will have its own system user/group to own its processes and files.

 * `cpuminer_system_user`: The system user the `cpuminer` service will run as.

 * `cpuminer_system_group`: The group to which the service's system user should belong.

### Pool Configuration

 * `cpuminer_pool_url`: The URL of the mining server to which this miner should connect.

 * `cpuminer_pool_username`: The username to provide to the mining server.

 * `cpuminer_pool_password`: The password to provide to the mining server.

### Mining Configuration

Options provided to the service's [minerd](https://github.com/pooler/cpuminer/blob/master/minerd.1) executable.
See `minerd --help`.

 * `cpuminer_algorithm`: The `--algo` option to provide to `minerd`.

 * `cpuminer_threads`: The `--threads` option to provide to `minerd`.

 * `cpuminer_scan_time`: The `--scantime` option to provide to `minerd`.

## Contributing

 1. **Fork this repo.**

 2. **Create a feature branch.** Work within your feature branch until you're finished.

 3. **Create a pull request.** If your pull request fixes a particular Github issue, then make sure to link to it. You'll get some feedback, and you may need to tweak something.

## License

The MIT License (MIT)

Copyright (c) 2016 Romero Fantastico

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
