01/26/2023: This fork contain's Eccentric's personal Dvorak+Steno keymap layout and change in config for NKRO functionality.

Below details the steps I made to get the firmware file using the GitHub Actions workflow:

0) Forked from xudongz's ergodox-zmk-config, then on my fork:
1) In build.yaml, changed Board to `raytac_mdbt50q_rx_green` to correspond with my dongle 
2) In config/slicemk_ergodox_dongle.conf I added the line CONFIG_ZMK_HID_REPORT_TYPE_NKRO=y
3) In config/slicemk_ergodox.keymap I copy/pasted the keymap I generated from xudongz's SliceMK Keymap Configurator
Once both were committed, then:
4) Go to Actions tab
5) Click on the latest .github/workflows/build.yml (should have a green checkmark next to it to indicate the run is completed, and should correspond to the latest commit, I think)
6) Scroll down to Artifacts
7) Download firmware file

-------------------------------------------------------------------------------
Below is the original Readme
===============================================================================

This repository contains the default ZMK user configuration for the [ErgoDox
Wireless](https://www.slicemk.com/pages/ergodox-wireless) keyboard. While the
[SliceMK Keymap Configurator](https://config.slicemk.com/) is recommended for
the majority of users, the GitHub Actions workflow provides some additional
options for customization.

If you have questions, feel free to join the [SliceMK
Discord](https://discord.gg/FQvyd7BAaA).

# Instructions

- Fork this repository on GitHub.
- Modify the `board` and `shield` values in `build.yaml` to match the ZMK build
  target based on your hardware (see below).
- If you have a dongleless setup, delete `config/slicemk_ergodox_dongle.conf`
  and create an empty `config/slicemk_ergodox_leftcentral.conf` in its place.

# Board/Shield

If you are not sure which dongle or PCB version you have, please put your
dongle/PCB into bootloader mode and check the "Model" value within the
`INFO_UF2.TXT` file.

Here are some of the common dongle options:

- **Raytac MDBT50Q-RX Green**
	- Board `raytac_mdbt50q_rx_green`
	- Shield `slicemk_ergodox_dongle`
- **Raytac MDBT50Q-RX** (if it does not say "green")
	- Board `raytac_mdbt50q_rx`
	- Shield `slicemk_ergodox_dongle`
- **Nordic nRF52840 Dongle**
	- Board `nordic_nrf52840_dongle_slicemk`
	- Shield `slicemk_ergodox_dongle`
- **SliceMK USB C Dongle MDBT50Q Blue**
	- Board `slicemk_usbc_mdbt50q_blue`
	- Shield `slicemk_ergodox_dongle`

Here are some of the common dongleless options:

- **SliceMK ErgoDox Wireless 202104**
	- Board `slicemk_ergodox_202104`
	- Shield `slicemk_ergodox_leftcentral`
- **SliceMK ErgoDox Wireless 202108 Blue**
	- Board `slicemk_ergodox_202108_blue_left`
	- Shield `slicemk_ergodox_leftcentral`
- **SliceMK ErgoDox Wireless 202108 Green**
	- Board `slicemk_ergodox_202108_green_left`
	- Shield `slicemk_ergodox_leftcentral`
- **SliceMK ErgoDox Wireless 202109**
	- Board `slicemk_ergodox_202109`
	- Shield `slicemk_ergodox_leftcentral`
- **SliceMK ErgoDox Wireless 202205 Green**
	- Board `slicemk_ergodox_202205_green_left`
	- Shield `slicemk_ergodox_leftcentral`
- **SliceMK ErgoDox Wireless 202207 Green**
	- Board `slicemk_ergodox_202207_green_left`
	- Shield `slicemk_ergodox_leftcentral`
