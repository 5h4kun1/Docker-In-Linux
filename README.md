# Docker-In-Linux


![](https://developers.redhat.com/sites/default/files/styles/article_feature/public/blog/2014/05/homepage-docker-logo.png?itok=zx0e-vcP)

The easiest way to install Docker on Linux depends on your specific Linux distribution. Here are the general steps for some popular Linux distributions:

1. Ubuntu:
   - Update the package lists: `sudo apt update`
   - Install Docker: `sudo apt install docker.io`
   - Start and enable the Docker service: `sudo systemctl start docker` and `sudo systemctl enable docker`
   - Add your user to the `docker` group to run Docker commands without using `sudo`: `sudo usermod -aG docker your_username`

2. Debian:
   - Update the package lists: `sudo apt update`
   - Install Docker: `sudo apt install docker.io`
   - Start and enable the Docker service: `sudo systemctl start docker` and `sudo systemctl enable docker`
   - Add your user to the `docker` group to run Docker commands without using `sudo`: `sudo usermod -aG docker your_username`

3. CentOS:
   - Enable the Docker CE repository: `sudo dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo`
   - Install Docker: `sudo dnf install docker-ce`
   - Start and enable the Docker service: `sudo systemctl start docker` and `sudo systemctl enable docker`
   - Add your user to the `docker` group to run Docker commands without using `sudo`: `sudo usermod -aG docker your_username`

4. Fedora:
   - Install Docker: `sudo dnf install docker`
   - Start and enable the Docker service: `sudo systemctl start docker` and `sudo systemctl enable docker`
   - Add your user to the `docker` group to run Docker commands without using `sudo`: `sudo usermod -aG docker your_username`

5. Arch Linux:
   - Install Docker: `sudo pacman -S docker`
   - Start and enable the Docker service: `sudo systemctl start docker` and `sudo systemctl enable docker`
   - Add your user to the `docker` group to run Docker commands without using `sudo`: `sudo usermod -aG docker your_username`

These steps provide a general guideline, but it's always recommended to consult your distribution's documentation for specific instructions tailored to your version and setup.



To install Docker on Linux, you can follow the steps outlined below. Please note that the instructions provided are general, and the exact commands may vary depending on your Linux distribution.

1. Update the package manager:
   ```
   sudo apt update
   ```

2. Install necessary dependencies to add repositories over HTTPS:
   ```
   sudo apt install apt-transport-https ca-certificates curl software-properties-common
   ```

3. Download and add Docker's official GPG key:
   ```
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
   ```

4. Add the Docker repository to your system's package sources:
   ```
   echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   ```

   Note: If you're not using Ubuntu, replace `$(lsb_release -cs)` with your specific distribution codename, such as `focal` for Ubuntu 20.04.

5. Update the package manager again:
   ```
   sudo apt update
   ```

6. Install Docker:
   ```
   sudo apt install docker-ce docker-ce-cli containerd.io
   ```

7. Add your user to the "docker" group to run Docker commands without sudo:
   ```
   sudo usermod -aG docker $USER
   ```

8. Log out of your session and log back in for the group changes to take effect.

After following these steps, Docker should be successfully installed on your Linux system. You can verify the installation by running the command:

```
docker --version
```

This should display the Docker version information if the installation was successful.
