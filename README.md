# LITESHIELD

This paper introduces LITESHIELD, a new userspace isolation architecture for secure containers. LITESHIELD decouples guest kernel functionality into userspace microkernel (μkernel) services that communicate with guest applications through low-latency, shared-memory-based userspace IPC.
By avoiding hypervisor dependence and hardware virtualization, LITESHIELD delivers isolation with reduced complexity and high efficiency.

This artifact provides scripts to run our prototype to reproduce our evaluation figures.  We are currently working on getting an authorization to release the source code from AFRL but it takes ~45 days, so only the binaries have been provided, (no source).  Please do not download the binaries.

# Usage
## Access our testbed remotely:
```
ssh -p 12345 root@kaesi.dev
```

Password is provided on HotCRP; Only one reviewer can use the testbed at-a-time.

# Reproducing the figures
## Figure 5: (~30min)

```
cd /src/artifact
sudo ./scripts/ae/figure_5_syscall_bench.sh
```

This runs our syscall benchmark on LITESHIELD as well as the baselines
the resulting figures can be found in: `output/figures/`

It should produce the figures for 5a and 5b: fig5-getpid.pdf, fig5-read.pdf

On our testbed, it takes about ~30min to run

## Figure 6: (~60min)
```
cd /src/artifact
sudo ./scripts/ae/figure_6a_udp.sh #run 6a
sudo ./scripts/ae/figure_6b_tcp.sh #run 6b
```
This runs our udp benchmark on LITESHIELD as well as the baselines
the resulting figures can be found in: `output/figures/`

It should produce the figures for 6a: fig6a-udp.pdf

On our testbed, each of (a and b) take about ~30min to run

## Figure 7: (~1h30min)
```
cd /src/artifact
sudo ./scripts/ae/figure_7_fio.sh
```

This runs the FIO benchmark on LITESHIELD + baselines

resulting figure is: `output/figures/fig7-fio.pdf`

## Figure 8: (~40min)
```
cd /src/artifact
sudo ./scripts/ae/figure_8_ycsb.sh
```

This runs the YCSB benchmark on LITESHIELD + baselines using redis

resulting figure will be in `output/figures/fig8-ycsb.pdf`

# Contact

Contact us on HotCRP if you have any questions
