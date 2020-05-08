Microsoft Lync / Skype for Business Wireshark Plugin
====================================================

            

The standard protocol decoders within Wireshark do not correctly decode a lot of the ICE/TURN/RTP/RTCP traffic created by Lync / Skype for Business clients and servers. So I created a LUA plugin for Wireshark that does this job. This plugin can be used on
 Lync / Skype for Business servers or also on Lync / Skype for Business client machines to allow you to see exactly how ICE/TURN/STUN negotiation and RTP/RTCP traffic is being sent. The plugin has been written based on the specifications in the following
 documentations:  


**Protocol Documentation:           
**


  *  [MS-TURNBWM] http://msdn.microsoft.com/en-us/library/ff595670.aspx 
  *  [MS-TURN] http://msdn.microsoft.com/en-us/library/cc431507.aspx 
  *  [MS-RTP] http://msdn.microsoft.com/en-us/library/cc431492.aspx 
  *  [MS-SRTP] http://msdn.microsoft.com/en-us/library/cc431516.aspx 
  *  [MS-RTASPF] http://msdn.microsoft.com/en-us/library/cc308725.aspx 
  *  [MS-RTPDT] http://msdn.microsoft.com/en-us/library/cc485841.aspx 
  *  [MS-ICE] http://msdn.microsoft.com/en-us/library/dd922095.aspx 
  *  [MS-ICE2] http://msdn.microsoft.com/en-us/library/cc431504.aspx 
  *  ICE RFC5245 - https://tools.ietf.org/html/rfc5245 
  *  STUN RFC5389 - http://tools.ietf.org/html/rfc5389 
  *  ICE-19 - http://tools.ietf.org/html/draft-ietf-mmusic-ice-19 
  *  RTP / RTCP - http://tools.ietf.org/html/rfc3550 

 


**Release Notes:**


**1.00 Initial Release:**


  *  This Wireshark plugin is designed to dissect Lync AV Edge and Internal Edge AV traffic. Captures can be taken on the Edge server (Capturing AV Edge External traffic, and Internal Interface traffic), or it can also be used on the client side for decoding
 STUN and RTP/RTCP traffic. 
  *  This Wireshark plugin dissects STUN/TURN traffic on Microsoft Lync Edge port 3478 (STUN, RTCP, RTP)

  *  This Wireshark plugin dissects traffic on Microsoft Lync Edge port 443 (STUN, RTCP, RTP)

  *  This Wireshark plugin dissects dynamically assigned RTP and RTCP traffic by using ports allocated in STUN requests.

  *  Dissector can be turned on/off within Wireshark Preferences. (Edit->Preferences->Protocols->LYNC_SKYPE_PLUGIN)

  *  Port numbers can be changed within Wireshark Preferences. (Edit->Preferences->Protocols->LYNC_SKYPE_PLUGIN)

  *  If you enter “lync_skype_plugin” in the Filter bar, only the traffic that is being decoded by the Lync Plugin will be displayed.

  *  To be used with the latest release of Wireshark (however, the plugin should work with higher than Wireshark 1.0)


 


**2.00 Wireshark 2.0 update:**


  *  Some updates to work with Wireshark 2.0+ 
  *  Changed the naming of the plugin to LYNC_SKYPE_PLUGIN. 
  *  Big updates to RTP and STUN classification to fix detection issues. 
  *  Corrected some issues with decoding 0x0013 Data Attribute encapsulated data. 
  *  Added TLS pass-through to the Wireshark default SSL dissector for Hello, Handshaking, and Application data. So now you can have the plugin running all the time and still troubleshoot TLS handshaking issues on port 443. This also makes the plugin better
 for client side testing. 
  *  The decoding of port 443 can have false positive matches for different packet types. The amount of false positive in this version of the plugin has been greatly decreased.

  *  Widened the scope of RTP port classification from 1024-59999 (which was limited for Edge use) to 1024-65535. This makes the plugin work better when testing client side connections.

  *  And more! 

 


**Usage:**


Place the plugin in the following directory and enjoy: 'C:\Program Files\Wireshark\plugins\<wireshark version number>\'


 


**More information on the plugin settings and controls can be found here:**


[http://www.myteamslab.com/2014/05/microsoft-lync-wireshark-plugin.html](http://www.myskypelab.com/2014/05/microsoft-lync-wireshark-plugin.html)


 






        
    
