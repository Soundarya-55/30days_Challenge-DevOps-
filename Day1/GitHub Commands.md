Here are some essential commands for managing an AWS EC2 instance running Ubuntu:

1. Update & Upgrade Packages
sudo apt update          # Update package lists
sudo apt upgrade -y      # Upgrade installed packages

2. Install Software
sudo apt install <package-name> -y   # Install a package (e.g., Apache, Nginx)

3. Check Installed Package
dpkg -l | grep <package-name>   # List installed packages

4. Remove or Uninstall a Package
sudo apt remove <package-name> -y     # Remove a package (without config files)
sudo apt purge <package-name> -y      # Remove a package (with config files)
sudo apt autoremove -y                # Remove unused dependencies

5. Start, Stop & Restart Services
sudo systemctl start <service-name>   # Start a service
sudo systemctl stop <service-name>    # Stop a service
sudo systemctl restart <service-name> # Restart a service
sudo systemctl status <service-name>  # Check service status

6. Enable/Disable Services on Boot
sudo systemctl enable <service-name>  # Enable service at startup
sudo systemctl disable <service-name> # Disable service at startup

7. Manage Files and Directories
ls -l                   # List files in directory
mkdir <dir-name>        # Create a directory
rm -r <dir-name>        # Delete a directory
rm <file-name>          # Delete a file

8. Monitor System & Resources
top            # View system processes
htop           # Interactive process viewer (install with `sudo apt install htop`)
df -h          # Check disk space
free -m        # Check memory usage

9. Manage EC2 Instance (Start, Stop, Restart)
sudo shutdown -h now      # Shutdown instance
sudo reboot               # Reboot instance
