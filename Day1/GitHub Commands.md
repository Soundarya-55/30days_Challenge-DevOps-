Here are some essential commands for managing an AWS EC2 instance running Ubuntu:

Update & Upgrade Packages
sudo apt update # Update package lists
sudo apt upgrade -y # Upgrade installed packages

Install Software
sudo apt install -y # Install a package (e.g., Apache, Nginx)

Check Installed Package
dpkg -l | grep # List installed packages

Remove or Uninstall a Package
sudo apt remove -y # Remove a package (without config files)
sudo apt purge -y # Remove a package (with config files)
sudo apt autoremove -y # Remove unused dependencies

Start, Stop & Restart Services
sudo systemctl start # Start a service
sudo systemctl stop # Stop a service
sudo systemctl restart # Restart a service
sudo systemctl status # Check service status

Enable/Disable Services on Boot
sudo systemctl enable # Enable service at startup
sudo systemctl disable # Disable service at startup

Manage Files and Directories
ls -l # List files in directory
mkdir # Create a directory
rm -r # Delete a directory
rm # Delete a file

Monitor System & Resources
top # View system processes
htop # Interactive process viewer (install with sudo apt install htop)
df -h # Check disk space
free -m # Check memory usage

Manage EC2 Instance (Start, Stop, Restart)
sudo shutdown -h now # Shutdown instance
sudo reboot # Reboot instance
