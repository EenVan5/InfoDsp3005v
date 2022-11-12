# InfoDsp3005v
[Conrad](https://www.conrad.com/p/voltcraft-dsp-3005v-se-bench-psu-adjustable-voltage-0-30-v-0-5-a-150-w-usb-remote-controlled-no-of-outputs-1-x-2446085) 

![Voltcraft DSP3005v](https://asset.conrad.com/media10/isa/160267/c1/-/en/002446085PI00/image.jpg  "Voltcraft DSP3005v")
The Voltcraft DSP3005v is a power supply with SCPI control over USB.
Since documentation on this interface is hard to find. Here some info accumulated so far.

# Serial interface
A ch341-uart converter (QinHeng Electronics HL-340 USB-Serial adapter) takes care of the serial connection on the power supply side. On an Ubuntu 20.04 Linux system, driver ch341 is loaded automatically for this.

The uart connection speed is 115200 Baud.

# Commands
The supported commands are a subset of the SCPI commands.

## General
	*IDN?
	Voltcraft,DSP3005V,2143728,FV:V3.2.0
	
	*OPC?
	V2.12.2B.1C.D
	
	:SYST:VERS?
	V1.0.0
	
	:SYST:ERR?
	0x0000
	
## Setup
	VOLT?
	6.000
	CURR?
	2.000
	VOLT 5.0
	CURR 1.0
	OUTP ON
	VOLT:LIM?
	30.000
	VOLT:LIM 10.0
	CURR:LIM?
	2.000
	CURR:LIM 1.0
	
## Readback
	:MEAS:VOLT?
	4.970
	:MEAS:CURR?
	0.000
	:MEAS:POW?
	0.000
	:MEAS:ALL:INFO?
	4.980,0.000,0.000,OFF,OFF,OFF,1
	OUTP?
	ON
	
## Power off
	OUTP OFF
