

# er-hardware Device Tree Overlay

### How to Use


2. **Configure the overlay in `config.txt`:**
	- After installing, you can enable and configure the overlay by adding a line to your `/boot/firmware/config.txt` (or `/boot/config.txt`):
	  ```
	  dtoverlay=er-hardware:hw_type=mrcm,hw_rev_major=0,hw_rev_minor=5
	  ```
	- Replace the parameters as needed for your hardware:
	  - `hw_type`: Hardware type (e.g., `mrcm`)
	  - `hw_rev_major`: Major hardware revision (e.g., `0`)
	  - `hw_rev_minor`: Minor hardware revision (e.g., `5`)

3. **Reboot** the device for changes to take effect.

### Example

To enable the overlay for a board of type `mrcm` with hardware revision 0.5, add this to your config:

```
dtoverlay=er-hardware,hw_type=mrcm,hw_rev_major=0,hw_rev_minor=5
```

### Result

On boot, the kernel loads the overlay and applies the configuration. You can verify this by checking the kernel log (`dmesg`) or inspecting `/proc/device-tree/overlays/`.

## When *Not* to Use

- If your hardware is already supported by the default device tree
- If you do not have the "er-hardware" board or compatible hardware

## More Information

See comments in `er-hardware.dts` for all supported parameters and hardware details.

---
See [LICENSE](LICENSE) for license information.
