### Flashing nabu via recovery mode.

> This guide assumes you know what you are doing and you have latest platform tools installed along with drivers.

* Download `boot.img`, `vendor_boot.img` and `dtbo.img`
> You will find them in the release page

* Boot into bootloader (not fastbootd)
> Poweroff the tablet, Press vol down and power key until you see fastboot written.

* Once in fastboot flash the artifacts that you downloaded, execute the following commands
* boot
  
`fastboot flash boot_a boot.img`

`fastboot flash boot_b boot.img`

* dtbo
  
`fastboot flash dtbo_a dtbo.img`

`fastboot flash dtbo_b dtbo.img`

* vendor_boot
  
`fastboot flash vendor_boot_a vendor_boot.img`

`fastboot flash vendor_boot_b vendor_boot.img`

##### That's it you are done with the hard one time part.

> Reboot to recovery by entering the following command.

`fastboot reboot recovery`

#### In recovery do the following. (You should see LineageOS logo if not then something isn't right)
> Touchscreen takes a little bit of time to probe sometimes so give it 20 seconds if you see that touchscreen is not working.

1: Tap Factory Reset, then Format data / factory reset and continue with the formatting process. This will remove encryption and delete all files stored in the internal storage.

2: Return to the main menu.

3: Sideload the LineageOS .zip package but do not reboot before you read/followed the rest of the instructions!
* On the device, select “Apply Update”, then “Apply from ADB” to begin sideload.
* On the host machine, sideload the package using: adb sideload filename.zip.
> Normally, adb will report Total xfer: 1.00x, but in some cases, even if the process succeeds the output will stop at 47% and report adb: failed to read command: Success. In some cases it will report adb: failed to read command: No error or adb: failed to read command: Undefined error: 0 which is fine.

If there are no errors in the recovery screen ad everything looks good selecting reboot from the main menu should allow you to boot into LineageOS.
