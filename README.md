# AMD BC-250 UEFI

## Known versions

| Version | Date       | Comments |
|---------|------------|----------|
| 4.00G   | 2022.04.08 |          |
| 5.00    | 2022.05.03 |          |
|         |            |          |


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
