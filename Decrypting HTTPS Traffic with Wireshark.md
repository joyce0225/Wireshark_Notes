# Decrypting HTTPS Traffic with Wireshark: Step-by-Step Guide

**Introduction**  
As an wannabe SOC analyst, I've summarized the steps to decrypt HTTPS traffic using Wireshark from a tutorial I watched. This guide is intended for educational purposes to track my learning progress.

**Steps to Decrypt HTTPS Traffic**  
*Step 1: Set Up Environment for Capturing Session Keys*  
- **Environment:** Windows 10, Chrome Browser.  
- **Action:** Go to Control Panel → System Properties.  
- **Configure Environment Variable:**  
    - Create a new variable named SSLKEYLOGFILE.  
    - Specify the file path where session keys will be stored.

*Step 2: Store Session Keys*  
- **Action:** Open Chrome and navigate to the target site.  
- **Result:** The client starts storing temporary session keys in the log file.

*Step 3: Start Wireshark for Packet Capturing*  
- **Action:** Open Wireshark.  
- **Select Network Interface:** Choose the appropriate interface, typically Wi-Fi for wireless connections.  
- **Start Capturing:** Observe the packets being captured.

*Step 4: Navigate to Target Site*  
- **Action:** In Chrome, navigate to the desired website (e.g., wireshark.org).  
- **Note:** This ensures session keys are exchanged and established.

*Step 5: Verify Capture in Wireshark*  
- **Action:** Use Wireshark's filter (e.g., frame contains wireshark) to check for DNS and TLS traffic.  
- **Goal:** Confirm that the correct packets are captured.

*Step 6: Analyze TLS Handshake in Wireshark*  
- **Focus:** Look for the TCP handshake and TLS details.  
- **Check:** Client Hello and Server Hello packets for TLS information.

*Step 7: Configure Wireshark for Decryption*  
- **Path:** Edit → Preferences → Protocols → TLS.  
- **Action:** Provide the path to the SSLKEYLOGFILE.  
- **Apply Changes:** Wireshark will now use these keys to decrypt traffic.

*Step 8: Observe Decrypted Traffic*  
- **Check for Changes:** Look for additional packets indicating successful decryption.  
- **Examine:** Specific packets, like the Server's Finished message and HTTP/2 traffic.  
- **Note:** Ensure TCP reassembly is enabled for complete data analysis.

*Step 9: Analyze Decrypted Application Data*  
- **Find Packet:** Jump to a specific packet number (e.g., 57) where data is reassembled.  
- **View Details:** Check the uncompressed entity body for decrypted information.

**Conclusion**  
These steps provide a clear guide to decrypt HTTPS traffic in Wireshark. This process is vital for deep packet analysis and understanding secure communications in network troubleshooting and forensic analysis.

[Source](https://www.youtube.com/watch?v=5qecyZHL-GU)
