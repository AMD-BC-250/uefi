# AMD BC-250 UEFI

## How to flash

### 1. Install kernel souces

* OpenSUSE

```bash
sudo zypper install kernel-source
```


### 2. Execute AMI AFU Linux

```bash
sudo ./tools/afulnx/afulnx_64_5.12.03 ./data_patched/4.00G/dump.bin
```
