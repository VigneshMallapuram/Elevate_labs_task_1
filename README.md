# Elevate_labs_task_1

# Nmap Network Scan Lab

## Objective

To perform a TCP SYN scan on the local network using Nmap and identify active hosts, open ports, and potential security risks.

## Tools Used

* Nmap
* Windows Command Prompt

## Finding the Local IP Range

Using:

```cmd
ipconfig
```

Active Wi-Fi Adapter:

* IPv4 Address: 10.249.127.7
* Subnet Mask: 255.255.255.0

Network Range:

```text
10.249.127.0/24
```

## Nmap Scan

Command used:

```cmd
nmap -sS 10.249.127.0/24
```

## Hosts Discovered

| IP Address    | Description    |
| ------------- | -------------- |
| 10.249.127.44 | Gateway/Router |
| 10.249.127.7  | Local Machine  |

## Open Ports Found

### 10.249.127.44

| Port | Service |
| ---- | ------- |
| 53   | DNS     |

### 10.249.127.7

| Port | Service        |
| ---- | -------------- |
| 80   | HTTP           |
| 135  | MSRPC          |
| 139  | NetBIOS        |
| 445  | SMB            |
| 902  | VMware         |
| 912  | VMware Related |
| 3306 | MySQL          |
| 5432 | PostgreSQL     |

## Security Risks

* Port 80 transmits unencrypted web traffic.
* Ports 139 and 445 are commonly targeted in Windows network attacks.
* MySQL (3306) and PostgreSQL (5432) should not be exposed publicly.
* VMware services should only be accessible within trusted networks.

## Conclusion

The scan successfully identified active hosts and open ports on the local network. Several services were found running on the local machine, including database and virtualization services. Proper firewall configuration and service management are recommended to reduce unnecessary exposure.
