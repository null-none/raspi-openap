# raspi-openap

Ansible playbook to configure a Raspberry Pi as a Wi-Fi access point **without a password**, and log all connected clients in real time.

## Features

- Open Wi-Fi hotspot (no password)
- DHCP configuration
- Static IP setup on `wlan0`
- Systemd-based logging of connected devices (`iw dev wlan0 station dump`)
- Fully automated via Ansible

## Usage

1. Clone this repo:
    ```bash
    git clone https://github.com/your-username/raspi-openap.git
    cd raspi-openap
    ```

2. Update `inventory.ini` with your Raspberry Pi IP or hostname:
    ```ini
    [raspberry]
    raspberrypi.local ansible_user=pi ansible_ssh_pass=raspberry ansible_become=true
    ```

3. Run the playbook:
    ```bash
    ansible-playbook -i inventory.ini playbook.yml
    ```

4. Check log:
    ```bash
    sudo tail -f /var/log/wifi_clients.log
    ```

## Requirements

- Raspberry Pi with built-in Wi-Fi (or USB dongle)
- OS: Raspberry Pi OS Lite or Full
- Ansible installed on your local machine

## License

MIT
