# Creality K1 MCU flasher
## Pure python implementation

Command flags and parameters compatible with official mcu_util flasher.
Notes:
bootloader awaits handshake 15 seconds after powerup MCU,
handshake need for any operation and only ONCE

Examples:
 - Run handshake only (after handshake other commands may be used without handshake):

    `mcu_util.py -c -i /dev/ttyS1`

- Get HW and FW version:

    `mcu_util.py -c -i /dev/ttyS1 -g`

- Flash firmware (remember - power cycle mcu before run update, or insert update command into init script):

    `mcu_util.py -c -i /dev/ttyS1 -u -f /usr/data/klipper/fw/K1/bed_klipper.bin`

- Startup firmware (if not started yet):

    `mcu_util.py -c -i /dev/ttyS1 -s`

- Reboot to bootloader (previously flashed supported firmware and stopped klipper service required)
    `mcu_util.py -b -i /dev/ttyS1 -br 230400 -g`