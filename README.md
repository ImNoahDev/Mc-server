# Create folder and change directory
mkdir mc
cd mc

# Download java and paper spigiot
sudo apt-get install default-jre
wget https://github.com/dev-bash/Mc-server/raw/main/paper-1.16.5-631.jar

# Run spigiot
java -Xms1G -Xmx2G -XX:+UseG1GC -jar paper-1.16.5-631.jar nogui

# accept EULA
change to true in:
sudo nano eula.txt

# Run spigiot and generate files
java -Xms1G -Xmx2G -XX:+UseG1GC -jar paper-1.16.5-631.jar nogui

# install crossplay
cd plugins
wget https://github.com/dev-bash/Mc-server/raw/main/Floodgate/floodgate-bukkit.jar
wget https://github.com/dev-bash/Mc-server/raw/main/Geyser/Geyser-Spigot.jar

# Run spigiot and generate files
java -Xms1G -Xmx2G -XX:+UseG1GC -jar paper-1.16.5-631.jar nogui

# Install settings
cd Geyser-Spigiot
wget https://raw.githubusercontent.com/dev-bash/Mc-server/main/Geyser/config.yml?token=AOE64SIULGJNC2AAGLQVJJTARMPDA
cd ~
cd Floodgate
wget https://raw.githubusercontent.com/dev-bash/Mc-server/main/Floodgate/config.yml?token=AOE64SLZGFDQWAZOGK2XNV3ARMPHG

# start at boot
crontab -e
and add:
@reboot cd mc & java -Xms1G -Xmx2G -XX:+UseG1GC -jar paper-1.16.5-631.jar nogui

# Reboot!
sudo reboot
