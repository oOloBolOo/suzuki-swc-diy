---
share: true
---
Retain factory steering wheel controls without buying an expensive OEM remote adapter. Most Japanese cars use a simple passive resistive ladder network that modern head units can read and program directly.

- **Vehicle:** 2007 Suzuki Grand Vitara
- **Factory Radio:** Clarion CLCC01 / PS-2654
- **Aftermarket Head Unit:** Kenwood DMX8021DABS

## Step 1: Verify Hardware Support

Your aftermarket unit must support native resistive SWC programming. Most modern Kenwood, Sony, JVC, and Pioneer units have an internal ADC (Analog-to-Digital Converter) for this. Check your unit's box or manual for a "Configurable Steering Wheel Remote Input" logo.

![Car Audio and Video Guide - Steering Wheel Audio Controls](https://www.fasmoto.com/image/data/blog/steering-wheel-control-interface-buyer-guide/lookout-for-these-swc-icons.jpg)


## Step 2: Source the Matching Harness

To keep the vehicle-side wiring intact, you need a Suzuki-to-ISO adapter harness.

Do not just look up your car's year online—cross-reference the plug layout by looking at the physical connections on your original factory radio.

![[15ef310434bc0f17eb9274a6a31a5535.jpg|15ef310434bc0f17eb9274a6a31a5535.jpg]]

![[212aa53f43c580b56154b5734d7a.jpg|212aa53f43c580b56154b5734d7a.jpg]]

According to the Kenwood wiring documentation, a standard ISO connection is required:

![[Pasted image 20251029105602.png|Pasted image 20251029105602.png]]

Buy the matching Suzuki radio harness to ISO connector. Double-check the connector "gender" before buying:

![[Pasted image 20251029110155.png|Pasted image 20251029110155.png]]

> [!WARNING] Watch out for incorrect variants Generic online fitment tools often recommend variants like the one below, which will not physically fit the factory vehicle harness. Always source by matching your specific factory radio model. ![[Pasted image 20251029105934.png|Pasted image 20251029105934.png]]

## Step 3: Fabricate the SWC Patch Cable

Instead of buying an overpriced or hard-to-find proprietary patch cable (like the Sony RC-SR1), you can build your own using a standard 3.5mm jack cable.

![[159839_Cable.PNG..png|159839_Cable.PNG..png]]

### Wiring Logic

1. Cut one end off a 3.5mm mini-jack cable and strip the wires.
    
2. Use a multimeter to trace which wire goes to which section of the physical plug:
    
    - **Sleeve (Base):** Ground
        
    - **Tip:** Input 1 (Channel 1)
        
    - **Ring (Middle):** Input 2 / Isolate if unused
        
3. Match these up to your vehicle's factory steering wheel control lines using the factory pinout layout. For the Clarion PS-2654, map the wires directly onto your new ISO adapter harness:
    

![[połączenie jack harness.png|połączenie jack harness.png]]

![[Pasted image 20251004214459.png|Pasted image 20251004214459.png]]

## Step 4: Connect the Head Unit & Ground the Parking Brake

1. Plug the custom 3.5mm jack into the **REMOTE INPUT** port (Pin 11) on the back of the Kenwood chassis.
    

![[Pasted image 20251029111918.png|Pasted image 20251029111918.png]]

![[20251013_131953-2.jpg|20251013_131953-2.jpg]]

2. **The Bypass Trick:** Locate the light green **Parking Brake Sensor Wire (`PRK SW`)** and connect it directly to the metal chassis or splice it straight into the main black ground wire.
    

![[Pasted image 20251029111813.png|Pasted image 20251029111813.png]]

![[Pasted image 20251026185654.png|Pasted image 20251026185654.png]]

> [!IMPORTANT] If you do not ground this wire, the head unit's firmware will assume the car is driving and completely lock out the steering wheel learning menu. Grounding it tricks the system into thinking the parking brake is permanently engaged.

## Step 5: Program the Buttons

Turn on the ignition and pull up the Kenwood interface settings to map your physical buttons:

1. Press **MENU** -> **SETUP**.
    
2. Select **User Interface**.
    
3. Scroll down and tap **Steering Remote Controller**.
    
4. Map the functions by holding down a physical button on your steering wheel and assigning its action (Volume, Skip, Mode) on the touchscreen.
    

![[Pasted image 20251029112502.png|Pasted image 20251029112502.png]]

## Technical Appendix: The Extra SWC Wire

You might notice both a loose Light Blue/Yellow wire labeled `REMOTE CONT` (Steering remote control wire) and a physical 3.5mm socket labeled `REMOTE INPUT` on the back of the unit.

![[Pasted image 20251029112551.png|Pasted image 20251029112551.png]]

Both lines map back to the same internal microcontroller system. The discrete Light Blue/Yellow wire is intended for installations using digital data modules (like CAN-bus boxes or iDatalink Maestro interfaces) that pass signals via raw loose wires. Since this installation uses a direct analog resistive connection through the DIY 3.5mm jack, the loose `REMOTE CONT` wire is redundant. It can be safely capped, taped off, and left disconnected.

