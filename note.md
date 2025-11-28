```shell
delete flash:/boot/uImage.ctc7132.e530.d.*

copy mgmt-if tftp://172.16.9.1/uImage.ctc7132.e530.d.251127162602 flash:/boot
boot system flash:/boot/uImage.ctc7132.e530.d.251127162602
```

