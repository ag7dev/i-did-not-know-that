# DMA FAQ and Setup Guide

Welcome to the DMA FAQ and Setup Guide! This document answers common questions about DMA, related devices, and how to set them up. Images are embedded for easier understanding.

---

## What is DMA?

**DMA (Direct Memory Access)** is a method that allows data to be transferred directly between hardware devices and memory without involving the CPU. In simpler terms, it lets you access and manipulate data on your main PC from a secondary PC. This is often used in gaming to run cheats without being detected by anti-cheat systems.

### How does DMA work?

A DMA device connects to your main PC, and a cable (usually from the JTAG port on the DMA device) links it to a second PC. Cheats run on the second PC while you play on the main PC, helping avoid detection since the cheats aren’t running directly on the main system.

For example, ESP cheats on the second PC might display a black screen with boxes or outlines around players, giving you an advantage in the game.

---

## What is Fuser?

**Fuser** is a tool that overlays the display of your second PC onto your main PC’s screen. This is useful when cheats run on a secondary PC.

When you launch the cheat on the second PC, pressing a button will display the cheat’s visuals (e.g., ESP overlays) on your main PC’s screen. To make this work, you usually need a black background or a command prompt (CMD) window open on the second PC to ensure the overlay is visible.

Note: The cheat runs on the second PC; the main PC only displays the visuals, helping avoid anti-cheat detection.

---

## What are KmBox and Arduino?

Both are devices used for aimbot functionality in games but differ in customization and safety.

- **KmBox**: A plug-and-play device with two versions:
  - KmBox Pro: Original version.
  - KmBox Net: Newer, safer version creating a local network between your main and secondary PC. However, firmware cannot be modified, limiting customization and undetectability.

- **Arduino**: A highly customizable alternative allowing you to create and modify your own firmware, making it safer and harder to detect by anti-cheat systems.

---

## What is Firmware?

Firmware helps you stay undetected by anti-cheat systems by hiding the DMA device in your PC using custom firmware. Without firmware, plugging in a DMA will likely get you banned in games.

Think of firmware as a bypass that enables cheating safely. If your firmware doesn’t support a game, unplug the DMA, play the game, then plug it back in afterward.

---

## How to Set Up DMA

This guide uses the CaptainDMA-75t as an example. Other DMA models may require different steps.

### Step 1: Install the DMA card

1. Turn off your main PC and disconnect the power cable.
2. Locate the farthest PCIe slot from the primary GPU slot on your motherboard (or use the primary GPU slot).
3. Install the DMA card into the PCIe slot as shown:

![Install DMA card](https://imgur.com/a/Unn2Cxy)

### Step 2: Connect cables

1. Plug the power cable back into your main PC and power it on.
2. Connect the provided USB-C to USB-A cable from the JTAG port on the DMA card to a USB 3.0 or higher port on your second PC.

![Connect USB cable](https://imgur.com/a/4EicBq1)

### Step 3: Activate DMA card

If no lights appear on the DMA card when powered on, press the kill switch button (red button) once while the computer is running to activate it.

![Kill switch button](https://imgur.com/a/a5FYhVD)

### Step 4: BIOS Configuration (Main PC)

- **AMD**: Disable IOMMU, Virtualization & SVM
- **Intel**: Disable Virtualization, VT-d
- Optional: Disable Secure Boot (Intel and AMD)

If you cannot find virtualization settings, search for your motherboard BIOS manual online.

### Step 5: Windows Pre-Requisites (Main PC)

- Disable Core Isolation on Windows 10 or 11:

Windows 11: [Disable Core Isolation](https://www.youtube.com/watch?v=XwBRM6Z303Y)  
Windows 10: [Disable Core Isolation](https://www.youtube.com/watch?v=zyp78E9_7YU)

### Step 6: Second PC Setup

Follow this video for second PC changes:  
[Second PC Setup Video](https://www.youtube.com/watch?v=C16Ky_1Glz4)

### Step 7: Driver Installation (Second PC)

1. Power on both PCs.
2. Ensure USB-C to USB-A cable is connected from DMA JTAG port to second PC.
3. Download the Phoenix DMA driver kit:  
[Phoenix DMA Driver Kit](https://www.unknowncheats.me/forum/d...=file&id=48539)  
4. Follow this installation video:  
[Driver Install Video](https://www.youtube.com/watch?v=qi-AX3qXLf0)

### Step 8: DMA Firmware Flash

1. Download firmware flash tool:  
[DMA Firmware Flash](https://www.unknowncheats.me/forum/d...=file&id=48540)  
2. Extract and open "1. Firmware_Flash_Tool" folder.
3. Drag "CH347FPGATool" folder to your C drive for best experience.
4. Run "CH347FpgaDownloadTool.exe".
5. Set FPGA to "xc7a75t" and BIN mode as shown:  
![Firmware Flash Tool](https://imgur.com/a/f8tiZWi)  
6. Load your firmware (example firmware available here:  
[CaptainDMA Firmware](https://github.com/ufrisk/pcileech-fpga/tree/master/CaptainDMA))  
7. Press the middle button to start flashing.
8. If errors occur, try moving the folder to desktop and retry.
9. After flashing, turn off the second PC for 10 seconds, then restart both PCs.

### Step 9: Verify Device

1. After reboot, plug USB-C to USB-A cable into the data port on DMA card.
2. Wait 5-10 seconds, open Device Manager on second PC.
3. You should see “FTDI FT601 USB 3.0 Bridge Device” under Universal Serial Bus Controllers.
4. If not, or if there is a warning icon, seek help.

### Step 10: Test DMA Speed

1. Open "2. FPGA DMA Test" folder.
2. Launch "lone-dma-test.exe".
3. Press 1 and Enter to do a full scan.
4. If speed test shows around 5000+ MB/s and status "Good" or "Excellent", your DMA is working.

---

## How to Set Up KmBox (Net)

1. Connect one blue cable from your main PC to the far left port on KmBox to power it on.
2. Check the version displayed; update firmware if outdated:  
[Firmware Update Video](https://www.youtube.com/watch?v=mgucFgakkvo)  
[Firmware Files](https://www.unknowncheats.me/forum/d...=file&id=48541)  
3. Connect another blue cable from your second PC to the upper left port on KmBox.
4. Plug your mouse into the upper right port on KmBox Net.
5. You should be able to move the mouse on the main PC. If not, try the lower right port.
6. Launch your game and cheat on the second PC. Enter the IP, port, and UUID as prompted.

### Optional: Spoof KmBox Net

1. Download "USB Log View" to get Vendor ID and Product ID of your mouse.
2. On second PC, download spoof tool:  
[Spoof Tool](https://www.unknowncheats.me/forum/d...=file&id=48542)  
3. Run the tool, enter IP, port, UUID from KmBox Net.
4. Enable "ping??" checkbox and press the big button.
5. Add Vendor ID and Product ID in VIP/PID field (e.g., "x34cy35x").
6. Press "VIP/PID" button to complete spoofing.

---

## How to Set Up Fuser

I used a white Dichen Fuser V5; setup may vary slightly.

1. Ensure both systems have the same resolution and refresh rate.
2. Connect HDMI cables:
   - Main PC to Fuser output.
   - Main monitor to Fuser Input 1.
   - Second monitor/PC to Fuser Input 2.
   - Plug in power.

![Fuser Setup](https://imgur.com/a/E801FVB)

3. Turn on the Fuser by pressing the big red button until it glows.
4. In display settings, set both displays to "Extend These Displays".

![Fuser Display Settings](https://imgur.com/a/XUnBOGk)

5. If you get refresh rate errors, unplug all HDMI cables and connect the white Type-C cable to your main PC’s USB 3.0 port.
6. Download and follow instructions here:  
[Fuser Fix Folder](https://www.unknowncheats.me/forum/d...=file&id=48543)  
7. After completing steps, unplug Type-C and reconnect HDMI cables. The Fuser lights should indicate it’s working (K1 and K4 LEDs).

---

## Is it worth buying DMA, Fuser, KmBox Net, and Firmware?

- **Yes:** You can cheat without worrying about bans due to mistakes.
- **No:** It costs a lot of money and setup is complex with many cables and steps.
- If you don’t cheat often or love cheating, it might feel like a waste of time and money.
- Ultimately, it allows you to cheat safely but requires patience and effort.

---

*This guide aims to help you understand and set up DMA and related devices safely and effectively.*

__________________
