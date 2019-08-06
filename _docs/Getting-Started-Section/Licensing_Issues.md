---
slug: licensing-troubleshooting
title: Licensing-Troubleshooting
---

## Licensing-Troubleshooting

When activating a valid Zynk license in versions prior to 2.20.3 you may come across the following message:

![Licensing Error](/assets/images/general/license.png "Licensing Error")

This can relate to an issue in older versions of Zynk where Zynk cannot create a secure connection to the Zynk licensing server using TLS 1.2.

To resolve this issue please download the following updated licensing library [here.](http://downloads.zynk.com/files/Internetware.Licensing.dll)

Once downloaded you can place the file in the installation folder for Zynk at C:\Program Files (x86)\Zynk Software\Zynk\2.0

If you are prompted to replace the file please do so. Once done restart Zynk and attempt to activate your license again.
