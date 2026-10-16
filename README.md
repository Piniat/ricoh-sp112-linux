# ricoh-sp112-linux
CUPS driver (PPD + filter) for the Ricoh SP 112 laser printer on Linux.

## Installation

1. Install the dependencies:
   ```sh
   sudo pacman -S cups ghostscript jbigkit            # Arch
   sudo apt install cups ghostscript jbigkit-bin      # Debian/Ubuntu
   ```
2. From the folder where you extracted the files, install the filter:
   ```sh
   sudo install -m 755 -o root -g root sp112-filter "$(cups-config --serverbin)/filter/"
   ```
3. Add the printer in the CUPS web interface at http://localhost:631
   (Administration → Add Printer). When asked for a driver, choose
   **Provide a PPD File** and select `ricoh-sp112.ppd`.

# NOTE
*This driver was developed with the help of AI (Claude Opus 5.5) which reverse engineered
the protocol from Ricoh's Windows driver. It has been tested on a real SP 112.*
