#This program is free software: you can redistribute it and/or modify   
#it under the terms of the GNU General Public License as published by   
#the Free Software Foundation, either version 3 of the License, or      
#(at your option) any later version.                                    
#                                                                            
#This program is distributed in the hope that it will be useful,        
#but WITHOUT ANY WARRANTY; without even the implied warranty of         
#MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the          
#GNU General Public License for more details.                           
#                                                                            
#You should have received a copy of the GNU General Public License       
#along with this program.  If not, see <http://www.gnu.org/licenses/>.   
#	                                                                          
#Nova32 Development Software and Nova32 NAS (Animation Studios)                                            
#(c) Rolando Fernandez Benavidez 2017.                                   
#GNU General Public License. 

CC=cl
CFLAGS= -gexplus128
OBJECTS= /gexplus/lib/libgex.a   \
	 /gexplus/lib/libfight.a
SYSTEM= PS2OS.SYS
GAME_ID=SCUS_793.11

binary: main.prg
	 clear
	 @echo compile PS2 game -BennuGD- makefile version 1.0 for SDK homebrew.
	 $(CC) main $(CFLAGS) $(SYSTEM)
	 @echo -----------------------------
	 @echo End compilation.

mass0: main.prg
	 clear
	 @echo PHASE 01:
	 @echo =========
	 @echo Compile PS2 game -BennuGD- makefile version 1.0 for SDK homebrew.
	 $(CC) main $(CFLAGS) $(SYSTEM)
	 @echo PHASE 02:
	 @echo =========
	 @echo Clean USB package.
	 usb-clean
	 @echo PHASE 03:
	 @echo =========
	 @echo Build USB struct...
	 mkdir USB
	 mkdir ./USB/SYSIO
	 @echo PHASE 04:
	 @echo =========
	 @echo Update USB package directory.
	 cp *.* ./USB
	 @echo PHASE 05:
	 @echo =========
	 @echo Remove source files in USB package
	 rm ./USB/*.prg
	 @echo PHASE 06:
	 @echo =========
	 @echo Install IO.SYS 
	 cp /ps2/usb/*.* ./USB
	 cp /ps2/usb/SYSIO/*.* ./USB/SYSIO
	 mv ./USB/IO.SYS ./USB/GAME.ELF
	 @echo * * * USB package is created now, play on your PS2 * * *

cdrom0:
	 clear
	 @echo Build DVD:$(GAME_ID)
	 @echo PHASE 01:
	 @echo =========
	 @echo Compile PS2 game -BennuGD- makefile version 1.0 for SDK homebrew.
	 $(CC) main $(CFLAGS) $(SYSTEM)
	 @echo PHASE 02:
	 @echo =========
	 @echo Clean DVD:$(GAME_ID)
	 iso-clean
	 cdrom-clean
	 @echo PHASE 03:
	 @echo =========
	 @echo Build DVD:$(GAME_ID) struct...
	 mkdir /swap/DVD
	 mkdir /swap/DVD/SYSIO
	 mkdir ISO
	 @echo PHASE 04:
	 @echo =========
	 @echo Update DVD:$(GAME_ID) directory.
	 cp *.* /swap/DVD
	 @echo PHASE 05:
	 @echo =========
	 @echo Remove source files in DVD:$(GAME_ID)
	 rm /swap/DVD/*.prg
	 @echo PHASE 06:
	 @echo =========
	 @echo Install SCUS_793.11
	 cp /ps2/iso/*.* /swap/DVD
	 cp /ps2/iso/SYSIO/*.* /swap/DVD/SYSIO
	 @echo PHASE 07:
	 @echo =========
	 @echo Build SCUS_793.11 ISO
	 mkisofs -V PS2 -o ./ISO/DISK.ISO /swap/DVD
	 @echo * * * PS2 ISO is created now, burn to 4x and play on your PS2 * * *

.PHONY: clean
clean:
	 @echo remove old objects
	 rm PS2OS.SYS







