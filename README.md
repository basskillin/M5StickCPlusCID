<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/basskillin/M5StickCPlusCID/blob/main/Img/74cd329ee907a31168ad4a917e4a7330-2851971051.jpg">
</picture>

# M5StickCPlusCID
M5StickCPlus CallerID using FreePBX CallerID Superfecta Send to URL.

1. Modify the Script to Send Data to the M5StickC:
edit  /var/www/html/admin/modules/superfecta/sources/source-Send_to_URL.module in you'r FreePBX Box
and add whats in "modified_script" and add it to source-Send_to_URL.module on FreePBX.
replace 10.0.0.10 with the IP of M5StickC . Save

3.  Use Arduino and send the code in "M5StickC_sketch-101" to the M5StickC replace your_ssid and your_password
with your own.

5. It worked for me. I hope the same.   
