# buildroot_rpi4_rt
# Steps to Build a Custom Linux Kernel with RT Patch

## Step 1: Download Buildroot
Download Buildroot from the official [GitHub repository](https://github.com/buildroot/buildroot).

## Step 2: Download the Linux Kernel
Download the Linux kernel source code from the [Linux GitHub repository](https://github.com/torvalds/linux) in `.tar.gz` format.  
Find the version you need in the `Makefile` of the kernel source.

## Step 3: Download the RT Patch
For the chosen kernel version, download the corresponding RT patch from [kernel.org](https://cdn.kernel.org/pub/linux/kernel/projects/rt/) in `.patch.xz` format.

## Step 4: Generate and Write Hashes
1. Write the hash of the RT patch inside the `linux.hash` file using the values from `sha256sums.asc`.
2. Generate the SHA-256 hash for the Linux kernel `.tar.gz` file using the command:
   ```bash
   sha256sum filename

## Step 5: Create linux.config
Create linux.config file in board/raspberrypi-rt/linux.config and write the following
`# enable full preemption
CONFIG_PREEMPT_RT=y`
