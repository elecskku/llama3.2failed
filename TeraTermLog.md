U-Boot 2023.01 (May 10 2024 - 06:24:11 +0000)

CPU:   ZynqMP
Silicon: v3
Chip:  xck26
Detected name: zynqmp-smk-k26-xcl2g-rev2-sck-kv-g-rev2
Model: ZynqMP KV260 revB
Board: Xilinx ZynqMP
DRAM:  2 GiB (effective 4 GiB)
PMUFW:  v1.1
Xilinx I2C FRU format at nvmem0:
 Manufacturer Name: XILINX
 Product Name: SMK-K26-XCL2G
 Serial No: XFL1PYN5YO0C
 Part Number: 05057-01
 File ID: 0x0
 Revision Number: 2
Xilinx I2C FRU format at nvmem1:
 Manufacturer Name: XILINX
 Product Name: SCK-KV-G
 Serial No: XFL15LILWYL1
 Part Number: 5066-01
 File ID: 0x0
 Revision Number: 2
EL Level:       EL2
Secure Boot:    not authenticated, not encrypted
Core:  127 devices, 35 uclasses, devicetree: fit
NAND:  0 MiB
MMC:   mmc@ff170000: 1
Loading Environment from nowhere... OK
In:    serial
Out:   serial
Err:   serial
Bootmode: QSPI_MODE
Reset reason:   SOFT
Net:   PHY reset timed out

ZYNQ GEM: ff0e0000, mdio bus ff0e0000, phyaddr 1, interface rgmii-id
eth0: ethernet@ff0e0000

gpio: pin gpio@ff0a000038 (gpio 38) value is 0
gpio: pin gpio@ff0a000038 (gpio 38) value is 1
starting USB...
Bus usb@fe200000: Register 2000440 NbrPorts 2
Starting the controller
USB XHCI 1.00
scanning bus usb@fe200000 for devices... 3 USB Device(s) found
       scanning usb for storage devices... 0 Storage Device(s) found
Hit any key to stop autoboot:  0
ZynqMP> setenv bootargs 'console=ttyPS0,115200 earlycon=cdns,mmio,0xFF010000 root=/dev/mmcblk0p2 rw rootwait cma=1024M clk_ignore_unused'
ZynqMP> load mmc 1:1 ${kernel_addr_r} image.ub
12851851 bytes read in 848 ms (14.5 MiB/s)
ZynqMP> load mmc 1:1 ${fdt_addr_r} system.dtb
41739 bytes read in 21 ms (1.9 MiB/s)
ZynqMP> bootm ${kernel_addr_r}:kernel-1 - ${fdt_addr_r}
## Loading kernel from FIT Image at 18000000 ...
   Trying 'kernel-1' kernel subimage
     Description:  Linux kernel
     Created:      2025-11-07  15:28:23 UTC
     Type:         Kernel Image
     Compression:  gzip compressed
     Data Start:   0x180000f8
     Data Size:    12807688 Bytes = 12.2 MiB
     Architecture: AArch64
     OS:           Linux
     Load Address: 0x00200000
     Entry Point:  0x00200000
     Hash algo:    sha256
     Hash value:   5ceb3e10b6ebd4afb0c4c78906efce35d698333ffbff2d8d7859dc2591441e13
   Verifying Hash Integrity ... sha256+ OK
## Flattened Device Tree blob at 40000000
   Booting using the fdt blob at 0x40000000
Working FDT set to 40000000
   Uncompressing Kernel Image
   Loading Device Tree to 000000000fff2000, end 000000000ffff30a ... OK
Working FDT set to fff2000

Starting kernel ...

[    0.000000] Booting Linux on physical CPU 0x0000000000 [0x410fd034]
[    0.000000] Linux version 6.12.40-xilinx-g31626ef92ff1 (oe-user@oe-host) (aarch64-amd-linux-gcc (GCC) 13.4.0, GNU ld (GNU Binutils) 2.42.0.20240723) #1 SMP Fri Nov  7 15:28:23 UTC 2025
[    0.000000] KASLR disabled due to lack of seed
[    0.000000] Machine model: ZynqMP KV260 revB
[    0.000000] earlycon: cdns0 at MMIO 0x00000000ff010000 (options '')
[    0.000000] printk: legacy bootconsole [cdns0] enabled
[    0.000000] efi: UEFI not found.
[    0.000000] OF: reserved mem: Reserved memory: No reserved-memory node in the DT
[    0.000000] Zone ranges:
[    0.000000]   DMA      [mem 0x0000000000000000-0x00000000ffffffff]
[    0.000000]   DMA32    empty
[    0.000000]   Normal   [mem 0x0000000100000000-0x000000087fffffff]
[    0.000000] Movable zone start for each node
[    0.000000] Early memory node ranges
[    0.000000]   node   0: [mem 0x0000000000000000-0x000000007fefffff]
[    0.000000]   node   0: [mem 0x0000000800000000-0x000000087fffffff]
[    0.000000] Initmem setup node 0 [mem 0x0000000000000000-0x000000087fffffff]
[    0.000000] On node 0, zone Normal: 256 pages in unavailable ranges
[    0.000000] cma: Reserved 1024 MiB at 0x000000003fe00000 on node -1
[    0.000000] psci: probing for conduit method from DT.
[    0.000000] psci: PSCIv1.1 detected in firmware.
[    0.000000] psci: Using standard PSCI v0.2 function IDs
[    0.000000] psci: MIGRATE_INFO_TYPE not supported.
[    0.000000] psci: SMC Calling Convention v1.2
[    0.000000] percpu: Embedded 31 pages/cpu s89816 r8192 d28968 u126976
[    0.000000] Detected VIPT I-cache on CPU0
[    0.000000] CPU features: detected: ARM erratum 845719
[    0.000000] alternatives: applying boot alternatives
[    0.000000] Kernel command line: console=ttyPS0,115200 earlycon=cdns,mmio,0xFF010000 root=/dev/mmcblk0p2 rw rootwait cma=1024M clk_ignore_unused
[    0.000000] Dentry cache hash table entries: 524288 (order: 10, 4194304 bytes, linear)
[    0.000000] Inode-cache hash table entries: 262144 (order: 9, 2097152 bytes, linear)
[    0.000000] Built 1 zonelists, mobility grouping on.  Total pages: 1048320
[    0.000000] mem auto-init: stack:all(zero), heap alloc:off, heap free:off
[    0.000000] software IO TLB: area num 4.
[    0.000000] software IO TLB: mapped [mem 0x000000003be00000-0x000000003fe00000] (64MB)
[    0.000000] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=4, Nodes=1
[    0.000000] rcu: Hierarchical RCU implementation.
[    0.000000] rcu:     RCU event tracing is enabled.
[    0.000000] rcu:     RCU restricting CPUs from NR_CPUS=16 to nr_cpu_ids=4.
[    0.000000]  Tracing variant of Tasks RCU enabled.
[    0.000000] rcu: RCU calculated value of scheduler-enlistment delay is 25 jiffies.
[    0.000000] rcu: Adjusting geometry for rcu_fanout_leaf=16, nr_cpu_ids=4
[    0.000000] RCU Tasks Trace: Setting shift to 2 and lim to 1 rcu_task_cb_adjust=1 rcu_task_cpu_ids=4.
[    0.000000] NR_IRQS: 64, nr_irqs: 64, preallocated irqs: 0
[    0.000000] GIC: Adjusting CPU interface base to 0x00000000f902f000
[    0.000000] Root IRQ handler: gic_handle_irq
[    0.000000] GIC: Using split EOI/Deactivate mode
[    0.000000] rcu: srcu_init: Setting srcu_struct sizes based on contention.
[    0.000000] arch_timer: cp15 timer(s) running at 99.99MHz (phys).
[    0.000000] clocksource: arch_sys_counter: mask: 0x1ffffffffffffff max_cycles: 0x171015c90f, max_idle_ns: 440795203080 ns
[    0.000000] sched_clock: 57 bits at 100MHz, resolution 10ns, wraps every 4398046511101ns
[    0.008339] Console: colour dummy device 80x25
[    0.012560] Calibrating delay loop (skipped), value calculated using timer frequency.. 199.99 BogoMIPS (lpj=399996)
[    0.022972] pid_max: default: 32768 minimum: 301
[    0.027706] Mount-cache hash table entries: 8192 (order: 4, 65536 bytes, linear)
[    0.034988] Mountpoint-cache hash table entries: 8192 (order: 4, 65536 bytes, linear)
[    0.044429] rcu: Hierarchical SRCU implementation.
[    0.047597] rcu:     Max phase no-delay instances is 1000.
[    0.052979] Timer migration: 1 hierarchy levels; 8 children per group; 1 crossnode level
[    0.061214] EFI services will not be available.
[    0.065602] smp: Bringing up secondary CPUs ...
[    0.070356] Detected VIPT I-cache on CPU1
[    0.070419] CPU1: Booted secondary processor 0x0000000001 [0x410fd034]
[    0.070862] Detected VIPT I-cache on CPU2
[    0.070905] CPU2: Booted secondary processor 0x0000000002 [0x410fd034]
[    0.071317] Detected VIPT I-cache on CPU3
[    0.071360] CPU3: Booted secondary processor 0x0000000003 [0x410fd034]
[    0.071419] smp: Brought up 1 node, 4 CPUs
[    0.105622] SMP: Total of 4 processors activated.
[    0.110319] CPU: All CPU(s) started at EL2
[    0.114409] CPU features: detected: 32-bit EL0 Support
[    0.119543] CPU features: detected: CRC32 instructions
[    0.124703] alternatives: applying system-wide alternatives
[    0.131145] Memory: 2961268K/4193280K available (18624K kernel code, 2364K rwdata, 5792K rodata, 4672K init, 500K bss, 179128K reserved, 1048576K cma-reserved)
[    0.145229] devtmpfs: initialized
[    0.153450] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645041785100000 ns
[    0.157581] futex hash table entries: 1024 (order: 4, 65536 bytes, linear)
[    0.187307] 24720 pages in range for non-PLT usage
[    0.187325] 516240 pages in range for PLT usage
[    0.187515] pinctrl core: initialized pinctrl subsystem
[    0.196691] DMI not present or invalid.
[    0.201864] NET: Registered PF_NETLINK/PF_ROUTE protocol family
[    0.206672] DMA: preallocated 512 KiB GFP_KERNEL pool for atomic allocations
[    0.213142] DMA: preallocated 512 KiB GFP_KERNEL|GFP_DMA pool for atomic allocations
[    0.220929] DMA: preallocated 512 KiB GFP_KERNEL|GFP_DMA32 pool for atomic allocations
[    0.228691] audit: initializing netlink subsys (disabled)
[    0.234204] audit: type=2000 audit(0.152:1): state=initialized audit_enabled=0 res=1
[    0.234500] thermal_sys: Registered thermal governor 'step_wise'
[    0.241952] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
[    0.254659] ASID allocator initialised with 65536 entries
[    0.260131] Serial: AMBA PL011 UART driver
[    0.268982] /axi/interrupt-controller@f9010000: Fixed dependency cycle(s) with /axi/interrupt-controller@f9010000
[    0.274529] /axi/display@fd4a0000: Fixed dependency cycle(s) with /dpcon
[    0.286218] /dpcon: Fixed dependency cycle(s) with /axi/display@fd4a0000
[    0.287773] /axi/display@fd4a0000: Fixed dependency cycle(s) with /dpcon
[    0.300449] HugeTLB: registered 1.00 GiB page size, pre-allocated 0 pages
[    0.301595] HugeTLB: 0 KiB vmemmap can be freed for a 1.00 GiB page
[    0.307873] HugeTLB: registered 32.0 MiB page size, pre-allocated 0 pages
[    0.314653] HugeTLB: 0 KiB vmemmap can be freed for a 32.0 MiB page
[    0.320916] HugeTLB: registered 2.00 MiB page size, pre-allocated 0 pages
[    0.327700] HugeTLB: 0 KiB vmemmap can be freed for a 2.00 MiB page
[    0.333966] HugeTLB: registered 64.0 KiB page size, pre-allocated 0 pages
[    0.340750] HugeTLB: 0 KiB vmemmap can be freed for a 64.0 KiB page
[    0.415092] raid6: neonx8   gen()  2516 MB/s
[    0.483158] raid6: neonx4   gen()  2468 MB/s
[    0.551232] raid6: neonx2   gen()  2358 MB/s
[    0.619308] raid6: neonx1   gen()  2007 MB/s
[    0.687357] raid6: int64x8  gen()  1583 MB/s
[    0.755437] raid6: int64x4  gen()  1740 MB/s
[    0.823503] raid6: int64x2  gen()  1555 MB/s
[    0.891578] raid6: int64x1  gen()  1146 MB/s
[    0.891619] raid6: using algorithm neonx8 gen() 2516 MB/s
[    0.963657] raid6: .... xor() 1839 MB/s, rmw enabled
[    0.963703] raid6: using neon recovery algorithm
[    0.968182] iommu: Default domain type: Translated
[    0.972381] iommu: DMA domain TLB invalidation policy: strict mode
[    0.986467] SCSI subsystem initialized
[    0.986673] usbcore: registered new interface driver usbfs
[    0.990072] usbcore: registered new interface driver hub
[    0.995388] usbcore: registered new device driver usb
[    1.000495] mc: Linux media interface: v0.10
[    1.004700] videodev: Linux video capture interface: v2.00
[    1.010177] pps_core: LinuxPPS API ver. 1 registered
[    1.015111] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
[    1.024256] PTP clock support registered
[    1.028183] EDAC MC: Ver: 3.0.0
[    1.031504] scmi_core: SCMI protocol bus registered
[    1.036312] zynqmp-ipi-mbox mailbox@ff9905c0: Registered ZynqMP IPI mbox with TX/RX channels.
[    1.045114] FPGA manager framework
[    1.048231] Advanced Linux Sound Architecture Driver Initialized.
[    1.054764] Bluetooth: Core ver 2.22
[    1.057754] NET: Registered PF_BLUETOOTH protocol family
[    1.063052] Bluetooth: HCI device and connection manager initialized
[    1.069404] Bluetooth: HCI socket layer initialized
[    1.074275] Bluetooth: L2CAP socket layer initialized
[    1.079325] Bluetooth: SCO socket layer initialized
[    1.084709] clocksource: Switched to clocksource arch_sys_counter
[    1.090540] VFS: Disk quotas dquot_6.6.0
[    1.094210] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
[    1.106195] NET: Registered PF_INET protocol family
[    1.106394] IP idents hash table entries: 65536 (order: 7, 524288 bytes, linear)
[    1.115826] tcp_listen_portaddr_hash hash table entries: 2048 (order: 3, 32768 bytes, linear)
[    1.121889] Table-perturb hash table entries: 65536 (order: 6, 262144 bytes, linear)
[    1.129613] TCP established hash table entries: 32768 (order: 6, 262144 bytes, linear)
[    1.137706] TCP bind hash table entries: 32768 (order: 8, 1048576 bytes, linear)
[    1.145654] TCP: Hash tables configured (established 32768 bind 32768)
[    1.151518] UDP hash table entries: 2048 (order: 4, 65536 bytes, linear)
[    1.158207] UDP-Lite hash table entries: 2048 (order: 4, 65536 bytes, linear)
[    1.165425] NET: Registered PF_UNIX/PF_LOCAL protocol family
[    1.171340] RPC: Registered named UNIX socket transport module.
[    1.176851] RPC: Registered udp transport module.
[    1.181545] RPC: Registered tcp transport module.
[    1.186243] RPC: Registered tcp-with-tls transport module.
[    1.191723] RPC: Registered tcp NFSv4.1 backchannel transport module.
[    1.198170] PCI: CLS 0 bytes, default 64
[    1.205125] Initialise system trusted keyrings
[    1.206614] workingset: timestamp_bits=46 max_order=20 bucket_order=0
[    1.213462] NFS: Registering the id_resolver key type
[    1.218015] Key type id_resolver registered
[    1.222176] Key type id_legacy registered
[    1.226198] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
[    1.232882] nfs4flexfilelayout_init: NFSv4 Flexfile Layout Driver Registering...
[    1.240439] jffs2: version 2.2. (NAND) (SUMMARY)  © 2001-2006 Red Hat, Inc.
[    1.297586] NET: Registered PF_ALG protocol family
[    1.297640] xor: measuring software checksum speed
[    1.302703]    8regs           :  2798 MB/sec
[    1.307048]    32regs          :  2803 MB/sec
[    1.311476]    arm64_neon      :  2631 MB/sec
[    1.314578] xor: using function: 32regs (2803 MB/sec)
[    1.319630] Key type asymmetric registered
[    1.323715] Asymmetric key parser 'x509' registered
[    1.328623] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 243)
[    1.335985] io scheduler mq-deadline registered
[    1.340512] io scheduler kyber registered
[    1.344532] io scheduler bfq registered
[    1.352411] ledtrig-cpu: registered to indicate activity on CPUs
[    1.388484] Serial: 8250/16550 driver, 4 ports, IRQ sharing disabled
[    1.390618] Serial: AMBA driver
[    1.399723] brd: module loaded
[    1.403059] loop: module loaded
[    1.407367] CAN device driver interface
[    1.408011] usbcore: registered new interface driver asix
[    1.410986] usbcore: registered new interface driver ax88179_178a
[    1.417077] usbcore: registered new interface driver cdc_ether
[    1.422903] usbcore: registered new interface driver net1080
[    1.428561] usbcore: registered new interface driver cdc_subset
[    1.434474] usbcore: registered new interface driver zaurus
[    1.440046] usbcore: registered new interface driver cdc_ncm
[    1.445700] usbcore: registered new interface driver r8153_ecm
[    1.451709] VFIO - User Level meta-driver version: 0.3
[    1.457297] usbcore: registered new interface driver uas
[    1.461976] usbcore: registered new interface driver usb-storage
[    1.467959] usbcore: registered new device driver onboard-usb-dev
[    1.474997] rtc_zynqmp ffa60000.rtc: registered as rtc0
[    1.479271] rtc_zynqmp ffa60000.rtc: setting system clock to 1970-01-01T00:15:34 UTC (934)
[    1.487570] i2c_dev: i2c /dev entries driver
[    1.493115] usbcore: registered new interface driver uvcvideo
[    1.497528] Driver for 1-wire Dallas network protocol.
[    1.503253] Bluetooth: HCI UART driver ver 2.3
[    1.507102] Bluetooth: HCI UART protocol H4 registered
[    1.512231] Bluetooth: HCI UART protocol BCSP registered
[    1.517554] Bluetooth: HCI UART protocol LL registered
[    1.522671] Bluetooth: HCI UART protocol ATH3K registered
[    1.528079] Bluetooth: HCI UART protocol Three-wire (H5) registered
[    1.534361] Bluetooth: HCI UART protocol Intel registered
[    1.539736] Bluetooth: HCI UART protocol QCA registered
[    1.544975] usbcore: registered new interface driver bcm203x
[    1.550623] usbcore: registered new interface driver bpa10x
[    1.556198] usbcore: registered new interface driver bfusb
[    1.561676] usbcore: registered new interface driver btusb
[    1.567171] usbcore: registered new interface driver ath3k
[    1.572723] EDAC MC: ECC not enabled
[    1.576415] EDAC DEVICE0: Giving out device to module zynqmp-ocm-edac controller zynqmp_ocm: DEV ff960000.memory-controller (INTERRUPT)
[    1.588690] sdhci: Secure Digital Host Controller Interface driver
[    1.594535] sdhci: Copyright(c) Pierre Ossman
[    1.598882] sdhci-pltfm: SDHCI platform and OF driver helper
[    1.605023] SMCCC: SOC_ID: ID = jep106:0049:0000 Revision = 0x04724093
[    1.611135] zynqmp_firmware_probe Platform Management API v1.1
[    1.616908] zynqmp_firmware_probe Trustzone version v1.0
[    1.651630] securefw securefw: securefw probed
[    1.651819] xilinx_ecdsa xilinx_ecdsa.0: ECDSA is not supported on the platform
[    1.658115] zynqmp-aes zynqmp-aes.0: will run requests pump with realtime priority
[    1.665725] zynqmp-sha3-384 zynqmp-sha3-384.0: will run requests pump with realtime priority
[    1.674015] usbcore: registered new interface driver usbhid
[    1.679419] usbhid: USB HID core driver
[    1.685843] ARM CCI_400_r1 PMU driver probed
[    1.686399] hw perfevents: enabled with armv8_cortex_a53 PMU driver, 7 (0,8000003f) counters available
[    1.697808] fpga_manager fpga0: Xilinx ZynqMP FPGA Manager registered
[    1.703730] usbcore: registered new interface driver snd-usb-audio
[    1.709959] pktgen: Packet Generator for packet performance testing. Version: 2.75
[    1.717847] Initializing XFRM netlink socket
[    1.721316] NET: Registered PF_INET6 protocol family
[    1.726783] Segment Routing with IPv6
[    1.729922] In-situ OAM (IOAM) with IPv6
[    1.733870] sit: IPv6, IPv4 and MPLS over IPv4 tunneling driver
[    1.740058] NET: Registered PF_PACKET protocol family
[    1.744763] NET: Registered PF_KEY protocol family
[    1.749554] can: controller area network core
[    1.753918] NET: Registered PF_CAN protocol family
[    1.758676] can: raw protocol
[    1.761637] can: broadcast manager protocol
[    1.765814] can: netlink gateway - max_hops=1
[    1.770246] Bluetooth: RFCOMM TTY layer initialized
[    1.775035] Bluetooth: RFCOMM socket layer initialized
[    1.780178] Bluetooth: RFCOMM ver 1.11
[    1.783910] Bluetooth: BNEP (Ethernet Emulation) ver 1.3
[    1.789212] Bluetooth: BNEP filters: protocol multicast
[    1.794434] Bluetooth: BNEP socket layer initialized
[    1.799392] Bluetooth: HIDP (Human Interface Emulation) ver 1.2
[    1.805310] Bluetooth: HIDP socket layer initialized
[    1.810299] 8021q: 802.1Q VLAN Support v1.8
[    1.814603] 9pnet: Installing 9P2000 support
[    1.818733] Key type dns_resolver registered
[    1.823112] NET: Registered PF_VSOCK protocol family
[    1.836354] registered taskstats version 1
[    1.836507] Loading compiled-in X.509 certificates
[    1.848221] Btrfs loaded, zoned=no, fsverity=no
[    1.948923] ff010000.serial: ttyPS0 at MMIO 0xff010000 (irq = 24, base_baud = 6249999) is a xuartps
[    1.958006] printk: legacy console [ttyPS0] enabled
[    1.958006] printk: legacy console [ttyPS0] enabled
[    1.962923] printk: legacy bootconsole [cdns0] disabled
[    1.962923] printk: legacy bootconsole [cdns0] disabled
[    1.973681] of-fpga-region fpga-region: FPGA Region probed
[    1.989590] xilinx-zynqmp-dpdma fd4c0000.dma-controller: Xilinx DPDMA engine is probed
[    2.414455] [drm] Initialized zynqmp-dpsub 1.0.0 for fd4a0000.display on minor 0
[    2.572516] Console: switching to colour frame buffer device 80x30
[    2.595380] zynqmp-dpsub fd4a0000.display: [drm] fb0: zynqmp-dpsubdrm frame buffer device
[    2.604661] zynqmp-dpsub fd4a0000.display: ZynqMP DisplayPort Subsystem driver probed
[    2.618198] macb ff0e0000.ethernet eth0: Cadence GEM rev 0x50070106 at 0xff0e0000 irq 46 (00:0a:35:24:9c:9a)
[    2.628596] xilinx-axipmon ffa00000.perf-monitor: Probed Xilinx APM
[    2.635257] xilinx-axipmon fd0b0000.perf-monitor: Probed Xilinx APM
[    2.641858] xilinx-axipmon fd490000.perf-monitor: Probed Xilinx APM
[    2.648494] xilinx-axipmon ffa10000.perf-monitor: Probed Xilinx APM
[    2.673671] xhci-hcd xhci-hcd.1.auto: xHCI Host Controller
[    2.679186] xhci-hcd xhci-hcd.1.auto: new USB bus registered, assigned bus number 1
[    2.686941] xhci-hcd xhci-hcd.1.auto: hcc params 0x0238f625 hci version 0x100 quirks 0x0000808002000810
[    2.696370] xhci-hcd xhci-hcd.1.auto: irq 48, io mem 0xfe200000
[    2.702391] xhci-hcd xhci-hcd.1.auto: xHCI Host Controller
[    2.707875] xhci-hcd xhci-hcd.1.auto: new USB bus registered, assigned bus number 2
[    2.715531] xhci-hcd xhci-hcd.1.auto: Host supports USB 3.0 SuperSpeed
[    2.722202] usb usb1: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 6.12
[    2.730469] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
[    2.737686] usb usb1: Product: xHCI Host Controller
[    2.742560] usb usb1: Manufacturer: Linux 6.12.40-xilinx-g31626ef92ff1 xhci-hcd
[    2.749869] usb usb1: SerialNumber: xhci-hcd.1.auto
[    2.755111] hub 1-0:1.0: USB hub found
[    2.758910] hub 1-0:1.0: 1 port detected
[    2.763366] onboard-usb-dev fe200000.usb:hub@1: supply vdd not found, using dummy regulator
[    2.771784] onboard-usb-dev fe200000.usb:hub@1: supply vdd2 not found, using dummy regulator
[    2.800871] usb usb2: New USB device found, idVendor=1d6b, idProduct=0003, bcdDevice= 6.12
[    2.809143] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
[    2.816367] usb usb2: Product: xHCI Host Controller
[    2.821245] usb usb2: Manufacturer: Linux 6.12.40-xilinx-g31626ef92ff1 xhci-hcd
[    2.828550] usb usb2: SerialNumber: xhci-hcd.1.auto
[    2.833757] hub 2-0:1.0: USB hub found
[    2.837523] hub 2-0:1.0: 1 port detected
[    2.842932] i2c i2c-1: using pinctrl states for GPIO recovery
[    2.848898] i2c i2c-1: using generic GPIOs for recovery
[    2.855124] cdns-i2c ff030000.i2c: 400 kHz mmio ff030000 irq 49
[    2.861753] cdns-wdt fd4d0000.watchdog: Xilinx Watchdog Timer with timeout 60s
[    2.869287] cdns-wdt ff150000.watchdog: Xilinx Watchdog Timer with timeout 10s
[    2.876980] cpufreq: cpufreq_online: CPU0: Running at unlisted initial frequency: 1333333 KHz, changing to: 1334000 KHz
[    2.888330] onboard-usb-dev fe200000.usb:hub@1: supply vdd not found, using dummy regulator
[    2.896780] onboard-usb-dev fe200000.usb:hub@1: supply vdd2 not found, using dummy regulator
[    2.926112] of_cfs_init
[    2.928574] of_cfs_init: OK
[    2.931476] clk: Not disabling unused clocks
[    2.935743] PM: genpd: Disabling unused power domains
[    2.941109] ALSA device list:
[    2.944065]   #0: DisplayPort Monitor
[    3.164716] usb 1-1: new high-speed USB device number 2 using xhci-hcd
[    3.305296] usb 1-1: New USB device found, idVendor=0424, idProduct=2744, bcdDevice= 2.21
[    3.313482] usb 1-1: New USB device strings: Mfr=1, Product=2, SerialNumber=0
[    3.320614] usb 1-1: Product: USB2744
[    3.324272] usb 1-1: Manufacturer: Microchip Tech
[    3.362221] hub 1-1:1.0: USB hub found
[    3.366010] hub 1-1:1.0: 5 ports detected
[    3.426140] usb 2-1: new SuperSpeed USB device number 2 using xhci-hcd
[    3.445170] usb 2-1: New USB device found, idVendor=0424, idProduct=5744, bcdDevice= 2.21
[    3.453353] usb 2-1: New USB device strings: Mfr=2, Product=3, SerialNumber=0
[    3.460490] usb 2-1: Product: USB5744
[    3.464147] usb 2-1: Manufacturer: Microchip Tech
[    3.522195] hub 2-1:1.0: USB hub found
[    3.526089] hub 2-1:1.0: 4 ports detected
[    3.712713] usb 1-1.5: new high-speed USB device number 3 using xhci-hcd
[    3.821407] usb 1-1.5: New USB device found, idVendor=0424, idProduct=2740, bcdDevice= 2.00
[    3.829760] usb 1-1.5: New USB device strings: Mfr=1, Product=2, SerialNumber=0
[    3.837061] usb 1-1.5: Product: Hub Controller
[    3.841501] usb 1-1.5: Manufacturer: Microchip Tech
[    4.149731] mmc0: SDHCI controller on ff170000.mmc [ff170000.mmc] using ADMA 64-bit
[    4.157528] Waiting for root device /dev/mmcblk0p2...
[    4.205202] mmc0: new high speed SDHC card at address aaaa
[    4.211137] mmcblk0: mmc0:aaaa SS32G 29.7 GiB
[    4.220055]  mmcblk0: p1 p2
[    5.208153] EXT4-fs (mmcblk0p2): recovery complete
[    5.214760] EXT4-fs (mmcblk0p2): mounted filesystem 2cefaa85-3613-46ea-85c9-0b0ef1a479f8 r/w with ordered data mode. Quota mode: none.
[    5.226914] VFS: Mounted root (ext4 filesystem) on device 179:2.
[    5.235547] devtmpfs: mounted
[    5.239645] Freeing unused kernel memory: 4672K
[    5.244228] Run /sbin/init as init process
[    5.923699] systemd[1]: System time before build time, advancing clock.
[    6.000442] systemd[1]: systemd 255.21^ running in system mode (+PAM -AUDIT -SELINUX -APPARMOR +IMA -SMACK +SECCOMP -GCRYPT -GNUTLS +OPENSSL +ACL +BLKID -CURL -ELFUTILS -FIDO2 -IDN2 -IDN -IPTC +KMOD -LIBCRYPTSETUP +LIBFDISK -PCRE2 -PWQUALITY -P11KIT -QRENCODE -TPM2 -BZIP2 -LZ4 -XZ -ZLIB +ZSTD -BPF_FRAMEWORK +XKBCOMMON +UTMP +SYSVINIT default-hierarchy=unified)
[    6.032380] systemd[1]: Detected architecture arm64.

Welcome to PetaLinux 2025.2+release-S11151021 (scarthgap)!

[    6.060705] systemd[1]: Hostname set to <xilinx-kv260-starterkit-20251>.
[    6.639295] systemd[1]: Queued start job for default target Multi-User System.
[    6.675571] systemd[1]: Created slice Slice /system/getty.
[  OK  ] Created slice Slice /system/getty.
[    6.693893] systemd[1]: Created slice Slice /system/modprobe.
[  OK  ] Created slice Slice /system/modprobe.
[    6.713841] systemd[1]: Created slice Slice /system/serial-getty.
[  OK  ] Created slice Slice /system/serial-getty.
[    6.733522] systemd[1]: Created slice User and Session Slice.
[  OK  ] Created slice User and Session Slice.
[    6.752962] systemd[1]: Started Dispatch Password Requests to Console Directory Watch.
[  OK  ] Started Dispatch Password Requests to Console Directory Watch.
[    6.772915] systemd[1]: Started Forward Password Requests to Wall Directory Watch.
[  OK  ] Started Forward Password Requests to Wall Directory Watch.
[    6.792821] systemd[1]: Expecting device /dev/disk/by-label/boot...
         Expecting device /dev/disk/by-label/boot...
[    6.812907] systemd[1]: Reached target Path Units.
[  OK  ] Reached target Path Units.
[    6.824811] systemd[1]: Reached target Remote File Systems.
[  OK  ] Reached target Remote File Systems.
[    6.840812] systemd[1]: Reached target Slice Units.
[  OK  ] Reached target Slice Units.
[    6.852812] systemd[1]: Reached target Swaps.
[  OK  ] Reached target Swaps.
[    6.896878] systemd[1]: Listening on RPCbind Server Activation Socket.
[  OK  ] Listening on RPCbind Server Activation Socket.
[    6.916930] systemd[1]: Reached target RPC Port Mapper.
[  OK  ] Reached target RPC Port Mapper.
[    6.933317] systemd[1]: Listening on Syslog Socket.
[  OK  ] Listening on Syslog Socket.
[    6.945009] systemd[1]: Listening on initctl Compatibility Named Pipe.
[  OK  ] Listening on initctl Compatibility Named Pipe.
[    6.965531] systemd[1]: Listening on Journal Audit Socket.
[  OK  ] Listening on Journal Audit Socket.
[    6.985106] systemd[1]: Listening on Journal Socket (/dev/log).
[  OK  ] Listening on Journal Socket (/dev/log).
[    7.009203] systemd[1]: Listening on Journal Socket.
[  OK  ] Listening on Journal Socket.
[    7.021306] systemd[1]: Listening on Network Service Netlink Socket.
[  OK  ] Listening on Network Service Netlink Socket.
[    7.044073] systemd[1]: Listening on udev Control Socket.
[  OK  ] Listening on udev Control Socket.
[    7.061088] systemd[1]: Listening on udev Kernel Socket.
[  OK  ] Listening on udev Kernel Socket.
[    7.077127] systemd[1]: Listening on User Database Manager Socket.
[  OK  ] Listening on User Database Manager Socket.
[    7.136958] systemd[1]: Mounting Huge Pages File System...
         Mounting Huge Pages File System...
[    7.151520] systemd[1]: Mounting POSIX Message Queue File System...
         Mounting POSIX Message Queue File System...
[    7.171564] systemd[1]: Mounting Kernel Debug File System...
         Mounting Kernel Debug File System...
[    7.187497] systemd[1]: Mounting Kernel Trace File System...
         Mounting Kernel Trace File System...
[    7.206635] systemd[1]: Mounting Temporary Directory /tmp...
         Mounting Temporary Directory /tmp...
[    7.224285] systemd[1]: Starting Create List of Static Device Nodes...
         Starting Create List of Static Device Nodes...
[    7.248022] systemd[1]: Starting Load Kernel Module configfs...
         Starting Load Kernel Module configfs...
[    7.265304] systemd[1]: Starting Load Kernel Module dm_mod...
         Starting Load Kernel Module dm_mod...
[    7.289319] systemd[1]: Starting Load Kernel Module drm...
         Starting Load Kernel Module drm...
[    7.307958] systemd[1]: Starting Load Kernel Module fuse...
         Starting Load Kernel Module fuse...
[    7.327938] systemd[1]: Starting Load Kernel Module loop...
         Starting Load Kernel Module loop...
[    7.351168] systemd[1]: Starting RPC Bind...
         Starting RPC Bind...
[    7.361087] systemd[1]: File System Check on Root Device was skipped because of an unmet condition check (ConditionPathIsReadWrite=!/).
[    7.379125] systemd[1]: Starting Journal Service...
         Starting Journal Service...
[    7.423001] systemd[1]: Starting Load Kernel Modules...
         Starting Load Kernel Modules...
[    7.443830] systemd[1]: Starting Generate network units from Kernel command line...
         Starting Generate network units from Kernel command line...
[    7.469035] systemd[1]: Starting Remount Root and Kernel File Systems...
         Starting Remount Root and Kernel File Systems...
[    7.493501] systemd[1]: Starting Coldplug All udev Devices...
         Starting Coldplug All udev Devices...
[    7.502473] dmaproxy: loading out-of-tree module taints kernel.
[    7.514029] systemd-journald[234]: Collecting audit messages is enabled.
[    7.518911] systemd[1]: Started RPC Bind.
[  OK  ] Started RPC Bind.
[    7.534725] systemd[1]: Mounted Huge Pages File System.
[  OK  ] Mounted Huge Pages File System.
[    7.553433] systemd[1]: Mounted POSIX Message Queue File System.
[  OK  ] Mounted POSIX Message Queue File Sys[    7.561204] EXT4-fs (mmcblk0p2): re-mounted 2cefaa85-3613-46ea-85c9-0b0ef1a479f8.
tem.
[    7.582663] systemd[1]: Mounted Kernel Debug File System.
[  OK  ] Mounted Kernel Debug File System.
[    7.601181] systemd[1]: Started Journal Service.
[  OK  ] Started Journal Service.
[    7.610633] openvswitch: Open vSwitch switching datapath
[  OK  ] Mounted Kernel Trace File System.
[  OK  ] Mounted Temporary Directory /tmp.
[  OK  ] Finished Create List of Static Device Nodes.
[  OK  ] Finished Load Kernel Module configfs.
[  OK  ] Finished Load Kernel Module dm_mod.
[  OK  ] Finished Load Kernel Module drm.
[  OK  ] Finished Load Kernel Module fuse.
[  OK  ] Finished Load Kernel Module loop.
[  OK  ] Finished Load Kernel Modules.
[  OK  ] Finished Generate network units from Kernel command line.
[  OK  ] Finished Remount Root and Kernel File Systems.
         Mounting NFSD configuration filesystem...
         Mounting Kernel Configuration File System...
         Starting Flush Journal to Persistent Storage...
         Starting Apply Kernel Variables...
         Starting Create Static Device Nodes in /dev gracefully...
[    7.923645] systemd-journald[234]: Received client request to flush runtime journal.
[  OK  ] Mounted NFSD configuration filesystem.
[  OK  ] Mounted Kernel Configuration File System.
[  OK  ] Finished Flush Journal to Persistent Storage.
[  OK  ] Finished Apply Kernel Variables.
[  OK  ] Finished Create Static Device Nodes in /dev gracefully.
         Starting Create Static Device Nodes in /dev...
[  OK  ] Finished Create Static Device Nodes in /dev.
[  OK  ] Reached target Preparation for Local File Systems.
         Mounting /var/volatile...
         Starting Rule-based Manager for Device Events and Files...
[  OK  ] Mounted /var/volatile.
         Starting Load/Save OS Random Seed...
[  OK  ] Started Rule-based Manager for Device Events and Files.
[  OK  ] Finished Coldplug All udev Devices.
[  OK  ] Finished Load/Save OS Random Seed.
[  OK  ] Found device /dev/disk/by-label/boot.
[  OK  ] Reached target Sound Card.
[  OK  ] Listening on Load/Save RF Kill Switch Status /dev/rfkill Watch.
         Mounting /boot...
         Starting Virtual Console Setup...
[  OK  ] Mounted /boot.
[  OK  ] Reached target Local File Systems.
         Starting Create System Files and Directories...
[  OK  ] Finished Create System Files and Directories.
         Starting Network Name Resolution...
         Starting Network Time Synchronization...
         Starting Record System Boot/Shutdown in UTMP...
[  OK  ] Finished Virtual Console Setup.
         Starting User Database Manager...
[  OK  ] Finished Record System Boot/Shutdown in UTMP.
[  OK  ] Started User Database Manager.
[  OK  ] Started Network Time Synchronization.
[  OK  ] Reached target System Time Set.
[  OK  ] Started Network Name Resolution.
[  OK  ] Reached target Host and Network Name Lookups.
[  OK  ] Reached target System Initialization.
[  OK  ] Started Daily rotation of log files.
[  OK  ] Started Daily Cleanup of Temporary Directories.
[  OK  ] Reached target Timer Units.
[  OK  ] Listening on D-Bus System Message Bus Socket.
         Starting sshd.socket...
[  OK  ] Listening on sshd.socket.
[  OK  ] Reached target Socket Units.
[  OK  ] Reached target Basic System.
[  OK  ] Started Job spooling tools.
[  OK  ] Started Periodic Command Scheduler.
         Starting D-Bus System Message Bus...
         Starting dfx-mgrd Dynamic Function eXchange...
[  OK  ] Started Start fan control, if configured.
         Starting IPv6 Packet Filtering Framework...
         Starting IPv4 Packet Filtering Framework...
[  OK  ] Started System Logging Service.
         Starting User Login Management...
         Starting OpenSSH Key Generation...
May 29 18:28:45 xilinx-kv260-starterkit-20251 kernel: KASLR disabled due to lack of seed
May 29 18:28:45 xilinx-kv260-starterkit-20251 kernel: GIC: Adjusting CPU interface base to 0x00000000f902f000
[  OK  ] Started dfx-mgrd Dynamic Function eXchange.
[  OK  ] Finished IPv6 Packet Filtering Framework.
[  OK  ] Finished IPv4 Packet Filtering Framework.
[  OK  ] Reached target Preparation for Network.
         Starting dfx-mgrd Default Firmware Load Service...
May 29 18:28:46 xilinx-kv260-starterkit-20251 kernel: xilinx_ecdsa xilinx_ecdsa.0: ECDSA is not supported on the platform
May 29 18:28:47 xilinx-kv260-starterkit-20251 kernel: onboard-usb-dev fe200000.usb:hub@1: supply vdd not found, using dummy regulator
May 29 18:28:47 xilinx-kv260-starterkit-20251 kernel: onboard-usb-dev fe200000.usb:hub@1: supply vdd2 not found, using dummy regulator
May 29 18:28:47 xilinx-kv260-starterkit-20251 kernel: onboard-usb-dev fe200000.usb:hub@1: supply vdd not found, using dummy regulator
May 29 18:28:47 xilinx-kv260-starterkit-20251 kernel: onboard-usb-dev fe200000.usb:hub@1: supply vdd2 not found, using dummy regulator
May 29 18:28:47 xilinx-kv260-starterkit-20251 kernel: clk: Not disabling unused clocks
         Starting Network Configuration...
May 29 18:28:52 xilinx-kv260-starterkit-20251 kernel: dmaproxy: loading out-of-tree module taints kernel.
May 29 18:28:54 xilinx-kv260-starterkit-20251 kernel: Must use shrinker_alloc() to dynamically allocate the shrinker
May 29 18:28:55 xilinx-kv260-starterkit-20251 kernel: FAT-fs (mmcblk0p1): Volume was not properly unmounted. Some data may be corrupt. Please run fsck.
[  OK  ] Started D-Bus System Message Bus.
[  OK  ] Finished dfx-mgrd Default Firmware Load Service.
[  OK  ] Finished OpenSSH Key Generation.
[  OK  ] Started User Login Management.
May 29 18:28:57 xilinx-kv260-starterkit-20251 kernel: platform regulatory.0: Direct firmware load for regulatory.db failed with error -2
[  OK  ] Started Network Configuration.
[  OK  ] Reached target Network.
         Starting DNS forwarder and DHCP server...
[  OK  ] Started Network Time Service.
         Starting Wait for Network to be Configured...
         Starting Permit User Sessions...
         Starting Target Communication Framework agent...
[  OK  ] Finished Permit User Sessions.
[  OK  ] Started Getty on tty1.
[  OK  ] Started Serial Getty on ttyPS0.
[  OK  ] Reached target Login Prompts.
[  OK  ] Started DNS forwarder and DHCP server.
[  OK  ] Started Target Communication Framework agent.
[  OK  ] Started Start fan control, if configured.

********************************************************************************************
The PetaLinux source code and images provided/generated are for demonstration purposes only.
Please refer to https://xilinx-wiki.atlassian.net/wiki/spaces/A/pages/2741928025/Moving+from+PetaLinux+to+Production+Deployment
for more details.
********************************************************************************************
PetaLinux 2025.2+release-S11151021 xilinx-kv260-starterkit-20251 ttyPS0

xilinx-kv260-starterkit-20251 login: petalinux
Password:
May 29 18:29:11 xilinx-kv260-starterkit-20251 kernel: kauditd_printk_skb: 1 callbacks suppressed
xilinx-kv260-starterkit-20251:~$ sudo -i
Password:
Sorry, try again.
Password:
root@xilinx-kv260-starterkit-20251:~# ls /dev/mmcblk*
/dev/mmcblk0  /dev/mmcblk0p1  /dev/mmcblk0p2
root@xilinx-kv260-starterkit-20251:~# sudo mkdir -p /mnt/sdcard
root@xilinx-kv260-starterkit-20251:~# sudo mount /dev/mmcblk0p1 /mnt/sdcard
root@xilinx-kv260-starterkit-20251:~# cd /mnt/sdcard
root@xilinx-kv260-starterkit-20251:/mnt/sdcard# sudo cp forward.xclbin llama_host_app model.bin tokenizer.bin /root/
root@xilinx-kv260-starterkit-20251:/mnt/sdcard# mkdir -p /lib/firmware/xilinx/llama-opt
root@xilinx-kv260-starterkit-20251:/mnt/sdcard# cd /lib/firmware/xilinx/llama-opt
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# cp /root/forward.xclbin ./llama-opt.xclbin
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# xclbinutil --input llama-opt.xclbin --dump-section BITSTREAM:RAW:llama-opt.bin --force
XRT Build Version: 2.20.0 (2025.2)
       Build Date: 2025-11-11 22:38:22
          Hash ID: 74dec3c9c4f6dd9bfb62ae11e71ec96bcc4859eb
------------------------------------------------------------------------------
Warning: The option '--output' has not been specified. All operations will
         be done in memory with the exception of the '--dump-section' command.
------------------------------------------------------------------------------
Reading xclbin file into memory.  File: llama-opt.xclbin

Section: 'BITSTREAM'(0) was successfully written.
Format: RAW
File  : 'llama-opt.bin'
Leaving xclbinutil.
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# cat > shell.json << 'EOF'
> {
>     "shell_type" : "XRT_FLAT",
>     "num_slots": "1"
> }
> EOF
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# cat > llama-opt.dtso << 'EOF'
> /dts-v1/;
> /plugin/;
> / {
>   fragment@0 {
>     target-path = "/fpga-region";
>     __overlay__ {
>       firmware-name = "xilinx/llama-opt/llama-opt.bin";
>     };
>   };
> };
> EOF
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# dtc -@ -I dts -O dtb \
>   -o /lib/firmware/xilinx/llama-opt/llama-opt.dtbo \
>   /lib/firmware/xilinx/llama-opt/llama-opt.dtso
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# [  132.755857] kria-dashboard.sh[2808]: Cant find IP addr, please call /usr/bin/kria-dashboard.sh after assigning IP addr

root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# xmutil loadapp llama-opt
May 29 18:31:06 xilinx-kv260-starterkit-20251 kernel: OF: overlay: WARNING: memory leak will occur if overlay removed, property: /fpga-region/firmware-name
llama-opt: Loaded with slot_handle 0
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# cat > /root/llama-opt-dev.dtso << 'EOF'
> /dts-v1/;
> /plugin/;
> / {
>   fragment@0 {
>     target-path = "/axi/interrupt-controller@b0000000";
>     __overlay__ {
>       status = "okay";
>       interrupt-parent = <&gic>;
>       interrupts = <0 89 4>;
>     };
>   };
>
>   fragment@1 {
>     target-path = "/axi/zyxclmm_drm";
>     __overlay__ {
>       status = "okay";
>       firmware-name = "xilinx/llama-opt/llama-opt.xclbin";
>     };
>   };
> };
>
> EOF
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# dtc -@ -I dts -O dtb \
>   -o /root/llama-opt-dev.dtbo \
>   /root/llama-opt-dev.dtso
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# mount -t configfs none /sys/kernel/config
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# mkdir -p /sys/kernel/config/device-tree/overlays/llamaopt
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# cat /root/llama-opt-dev.dtbo > \
>     /sys/kernel/config/device-tree/overlays/llamaopt/dtbo
May 29 18:31:42 xilinx-kv260-starterkit-20251 kernel: OF: overlay: WARNING: memory leak will occur if overlay removed, property: /axi/interrupt-controller@b0000000/status
May 29 18:31:42 xilinx-kv260-starterkit-20251 kernel: OF: overlay: WARNING: memory leak will occur if overlay removed, property: /axi/interrupt-controller@b0000000/interrupt-parent
May 29 18:31:42 xilinx-kv260-starterkit-20251 kernel: OF: overlay: WARNING: memory leak will occur if overlay removed, property: /axi/interrupt-controller@b0000000/interrupts
May 29 18:31:42 xilinx-kv260-starterkit-20251 kernel: OF: overlay: WARNING: memory leak will occur if overlay removed, property: /axi/zyxclmm_drm/status
May 29 18:31:42 xilinx-kv260-starterkit-20251 kernel: OF: overlay: WARNING: memory leak will occur if overlay removed, property: /axi/zyxclmm_drm/firmware-name
May 29 18:31:42 xilinx-kv260-starterkit-20251 kernel: zocl-drm axi:zyxclmm_drm: error -ENXIO: IRQ index 0 not found
May 29 18:31:42 xilinx-kv260-starterkit-20251 kernel: [drm] Failed to initialize the cma mem reserved nodes
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# ls /dev/dri
by-path  card0  card1  renderD128
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# export XILINX_XRT=/usr
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# export LD_LIBRARY_PATH=/usr/lib:$LD_LIBRARY_PATH
root@xilinx-kv260-starterkit-20251:/lib/firmware/xilinx/llama-opt# cd /root
root@xilinx-kv260-starterkit-20251:~# chmod +x llama_host_app
root@xilinx-kv260-starterkit-20251:~# ./llama_host_app \
>     forward.xclbin \
>     model.bin \
>     tokenizer.bin
=============================================================
  KV260 Llama Accelerator - XRT Native API
=============================================================

[1] Initializing FPGA device...
May 29 18:32:13 xilinx-kv260-starterkit-20251 kernel: [drm] Failed to initial CU interrupt. Fall back to polling
    ✓ Device initialized and XCLBIN loaded

[2] Loading model weights and tokenizer...
    ✓ Model loaded (dim=768, layers=12)
    ✓ Tokenizer initialized (vocab=32000)

[3] Creating kernel and allocating buffers...
    ✓ Buffers allocated:
      - transformer: 235203 KB
      - key_cache:   36864 KB
      - value_cache: 36864 KB
      - out:         125 KB

[4] Transferring model weights to FPGA (one-time)...
    ✓ Weights transferred

=============================================================
  Ready for interactive generation
  (Type your prompt and press Enter. Type 'exit' to quit)
=============================================================

You: What is a University?
Assistant:
