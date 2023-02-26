# delft3d
Compiled delft3d_7545

# use in archlinux
```bash
# install mpich
yay -S mpich
# add path to bashrc
export PATH=/opt/mpich/bin: $PATH
export LD_LIBRARY_PATH=/opt/mpich/lib


#tackle 'libssl.so.1.0.0 not found'
sudo pacman -Qo libssl.so.1.0.0 # Check if the installed packages include this file
sudo pacman -F libssl.so.1.0.0 # Find which package include this file, The result shows that teamspeak3 contains, Sync

yay -S teamspeak3
sudo ln -s /opt/teamspeak3/libssl.so.1.0.0 /lib/libssl.so.1.0.0  #自己添加一个软连接，貌似不行，找别的办法，这个仅仅记录思路
sudo ln -s /opt/teamspeak3/libcrypto.so.1.0.0 /lib/libssl.so.1.0.0

# other issues
Please refer to the website [[https://oss.deltares.nl/web/delft3d/get-started]]

```
# get examples from source code & run examples
```bash
sudo pacman -S subversion
svn checkout https://svn.oss.deltares.nl/repos/delft3d/tags/delft3d4/7545/ 'your path'

# copy examples to where you store this repository, or you have to edit the scripts, for me:'~/delft3d/'
cp -r 'your path'/delft3d_7545/examples ~/delft3d/

# test
cd ~/delft3d/examples/01_standard
./run_flow2d3d.sh
```
![image](https://user-images.githubusercontent.com/55399089/221386603-5bc97a75-322a-41c8-9474-2a559b4e8d84.png)
