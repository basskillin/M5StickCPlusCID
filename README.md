# M5StickCPlusCID
M5StickCPlus CallerID using FreePBX CallerID Superfecta Send to URL.

1. Modify the Script to Send Data to the M5StickC:
edit  /var/www/html/admin/modules/superfecta/sources/source-Send_to_URL.module in you'r FreePBX Box
and add whats in "modified_script" and add it to source-Send_to_URL.module on FreePBX.
Edit your WiFi INFO and the IP of the M5StickC. Save

2.  Use Arduino and send "M5StickC_sketch-101" to the M5StickC.

3. It worked for me. I hope the same.   
