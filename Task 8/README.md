# Capture Network Traffic with Wireshark

## Objective

To capture and analyze real-time network traffic using the **Wireshark GUI** interface on a Linux system. This helps understand how devices communicate on a local network and reveals common protocols in use.

---

## 🛠Tools Used

- **Wireshark** (GUI Application)
- **Operating System**: Kali Linux
- **Network Interface**: eth0

---

## Steps Performed

1. **Opened the Wireshark application** from the system menu (no commands used).
2. Selected the active network interface: `eth0`.
3. Clicked the **"Start Capture"** (shark fin) icon.
4. Wireshark started capturing real-time network traffic.
5. Used the **display filter**:  
   ```
   ip.addr == 192.168.29.147
   ```
   to focus on traffic related to a specific host.
6. Stopped the capture after a few minutes using the red square (Stop).
7. Saved the capture as `wireshark_capture.pcapng`.

---

## Packet Analysis Summary

Captured traffic includes:

| Protocol | Description                                                                 |
|----------|-----------------------------------------------------------------------------|
| IGMPv3   | Multicast group management protocol (used for joining multicast groups)     |
| NBNS     | NetBIOS Name Service — used in Windows environments for name resolution     |
| LLMNR    | Link-Local Multicast Name Resolution — fallback to DNS                      |
| BROWSER  | NT Workgroup/domain announcements                                           |

- The host `192.168.29.147` was communicating with multicast IPs like `224.0.0.22` and `224.0.0.252`.
- The system was announcing its presence and querying names like `MICROWAVE`.
- The packets reveal normal local area network (LAN) discovery activity.

---

## Files Included

```
├── wireshark_capture.pcapng           # Captured network traffic
├── Screenshot_2025-07-14_17_04_48.png # Wireshark live capture view
└── README.md                          # This explanation file
```

---

## Conclusion

Wireshark successfully captured local traffic without using any terminal commands. This GUI-based approach helps beginners visualize what’s happening on a network in real time. The traffic shows common discovery and name resolution protocols, useful for learning network fundamentals and identifying potential vulnerabilities (like LLMNR/NBNS spoofing).

---

## Notes

- **No commands were used**; only Wireshark GUI was used for this task.
- It's essential to use Wireshark only on **authorized networks** to avoid legal/ethical issues.
- Even simple captures like this can uncover useful insights into network behavior.

---

