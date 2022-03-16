rough notes for manual building. to be gradualy replaced by minicvlplay.yml

build ubuntu20 VM on nectar
ssh -X ubuntu@118.138.234.168
sudo apt update
sudo apt install -y tightvncserver
sudo apt install -y ubuntu-mate-desktop
sudo apt install -y tigervnc-viewer

vncserver  entering passwords manually # see generated contents  below

ubuntu@cvltest:~$ cat /home/ubuntu/.vnc/passwd                                                                        
<rzXubuntu@cvltest:~$ 

xtigervncviewer -SecurityTypes VncAuth -passwd /home/ubuntu/.vnc/passwd :1

test on the desktop for vglrun is :   ~$ ./vglrun ./glxspheres64

test singularity via
singularity exec library://sylabsed/examples/lolcow cowsay "Fresh from the library!"

