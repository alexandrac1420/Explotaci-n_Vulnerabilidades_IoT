# Exploiting Vulnerabilities in IoT (Internet of Things)

## Project Overview

This project addresses the growing interconnection of devices in the **Internet of Things (IoT)** and the associated security risks. It analyzes what IoT is, the devices that comprise it, and how their vulnerabilities can be exploited, affecting the privacy and integrity of information. Furthermore, approaches to mitigate these risks are discussed.

---

## Architecture

The study was conducted in a controlled laboratory scenario to perform an ethical attack on an IoT surveillance system.

1. **Private Network Environment in Kali Linux**: Kali Linux was used as the attack platform due to its versatility and integrated cybersecurity tools, such as network analysis and vulnerability scanning.

2. **Equipment and Tools Used**:

   * **DVRs and IP Cameras**: DVRs vulnerable to CVE-2018-9995 connected to several IP cameras were used to simulate the attack target.

   * **Search Tools (Shodan and Google Dorks)**: To simulate the identification of vulnerable DVRs exposed on the network.

   * **IE Tab Extension in Chrome Browser**: Allows viewing the camera interface in Internet Explorer mode, simulating real-time access to the DVR.

---

## Vulnerability Exploited: CVE-2018-9995

The **CVE-2018-9995** vulnerability affects certain DVR models, allowing administrator credentials to be obtained without authentication due to a flaw in the validation of specific HTTP requests. Its exploitation allows attackers to view real-time streams and manipulate configurations of affected DVRs.

### Attack Description

To exploit this vulnerability, the *script* `getDVR_Credentials.py` was used on a Kali Linux system.

1. **Explanation of the `getDVR_Credentials.py` Script**:

   * The *script* sends an HTTP request with manipulated headers to the target DVR.

   * Due to the lack of validation, the DVR responds with administrator credentials in a readable format (username and password).

   * The *script* allows automation by entering multiple IP addresses and ports.

2. **Script Execution in Kali Linux**:

   * **Repository Cloning**: The repository containing the *script* is cloned in Kali Linux.

   * **Identification of Vulnerable DVRs**: Google Dorks (`intitle:"DVR login"`) and Shodan (`Html:"/login.rsp"`) are used to locate DVRs exposed on the network.

   * **Script Execution**: Once the vulnerable IPs and ports are collected, the script is executed to obtain access credentials.

   * **Real-time Stream Access**: With the obtained credentials, the DVR interface is accessed using a browser with the IE Tab extension to view camera streams.

---

## Vulnerability Mitigation

To reduce the risks associated with IoT, robust security practices are proposed:

* **Strong Authentication**: Implementation of strong passwords and multi-factor authentication (MFA), forcing the change of default passwords.

* **Data Encryption in Transit**: Enabling end-to-end encryption, such as HTTPS, to protect data transmission.

* **Firmware Updates and Security Patches**: Ensuring regular firmware updates to mitigate known vulnerabilities.

* **User Awareness**: Educating users about the risks of default configurations and the use of VPNs.

* **Use of Segmented Networks**: Separating IoT devices from the main network to limit damage in case of compromise.

* **Network Monitoring with Intrusion Detection Systems (IDS)**: To identify and notify suspicious activities in real-time.

---

## Conclusions

The study underscores the urgent need to adopt a proactive approach to IoT device security to leverage its benefits without compromising privacy and security. The implementation of robust protection measures, such as multi-factor authentication, data encryption, and regular firmware updates, is crucial to strengthening IoT infrastructure.

---

## Authors

* **Alexandra Cortes Tovar** - [alexandrac1420](https://github.com/alexandrac1420)

* **José Ricardo Vásquez Vega** - [Richi025](https://github.com/Richi025)

* **Juan Sebastián Vásquez Vega** - [Sebasvasquezz](https://github.com/Sebasvasquezz)

## Date

July 2025

## License

This project is licensed under the MIT License.
