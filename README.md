# awesome voip [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

❤️ Support my app ❤️ 

- [Push Hero - pure Swift native macOS application to test push notifications](https://www.producthunt.com/posts/push-hero-2)
- [PastePal - Pasteboard, note and shortcut manager](https://www.producthunt.com/posts/pastepal)
- [Frame recorder - Recorder gif and video with frame](https://www.producthunt.com/posts/frame-recorder)
- [Other apps](https://onmyway133.github.io/projects/)

❤️❤️😇😍🤘❤️❤️

Before working with Windows Phone and iOS, my life involved researching VoIP. That was to build a C library for voice over IP functionality for a very popular app, and that was how I got started in open source.

The library I was working with were [Linphone](https://www.linphone.org/) and [pjsip](http://pjsip.org/). I learn a lot of UDP and SIP protocol, how to build C library for consumption in iOS, Android and Windows Phone, how challenging it is to support C++ component and thread pool in Windows Phone 8, how to tweak entropy functionality in OpenSSL to make it compile in Windows Phone 8, how hard it was to debug C code with Android NDK. It was time when I needed to open Visual Studio, Xcode and Eclipse IDE at the same time, joined [mailing list](https://www.google.no/search?q=lists.pjsip.org+onmyway133&oq=lists.pjsip.org+onmyway133) and followed [gmane](http://dir.gmane.org/gmane.comp.voip.pjsip). Lots of good memories.

Today I find that those bookmarks I made are still available on Safari, so I think I should share here. I need to remove many articles because they are outdated or not available anymore. These are the resources that I actually read and used, not some random links. Hopefully you can find something useful.

This post focuses more about resources for pjsip on client and how to talk directly and with/without a proxy server.

## First of all

Here are some of the articles and open sources made by me regarding VoIP, hope you find it useful

* [rtpproxy](https://github.com/onmyway133/rtpproxy): I forked from [http://www.rtpproxy.org/](http://www.rtpproxy.org/) and changed code to make it support for IP handover. It means the proxy can handle when IP changes from 3G, 4G to Wifi and to reduce chances of attacks

* [Jitter buffer in VoIP](https://github.com/onmyway133/blog/issues/157)

* [How to calculate packet size in VoIP](https://github.com/onmyway133/blog/issues/155)

## VoIP overview
> **Voice over Internet Protocol** (also **voice over IP**, **VoIP** or **IP telephony**) is a methodology and group of technologies for the delivery of [voice communications](https://en.wikipedia.org/wiki/Voice_communication) and [multimedia](https://en.wikipedia.org/wiki/Multimedia) sessions over [Internet Protocol](https://en.wikipedia.org/wiki/Internet_Protocol) (IP) networks, such as the [Internet](https://en.wikipedia.org/wiki/Internet)

* [Voice over IP Overview](http://toncar.cz/Tutorials/VoIP/index.html): introduction to VoIP concepts, H.323 and SIP protocol

* [Voice over Internet Protocol](https://en.wikipedia.org/wiki/Voice_over_IP) the wikipedia article contains very foundation knowledge

* [Open Source VOIP Software](https://www.voip-info.org/open-source-voip-software): this is a must read. Lots of foundation articles about client and server functionalities, SIP, TURN, RTP, and many open sources framworks

* [VOIP call bandwidth](https://planetcalc.com/3144/): a very key factor in VoIP application is bandwidth consumption, it’s good to not going far beyond the accepted limit

* [Routers SIP ALG](https://www.voip-info.org/routers-sip-alg): this is the most annoying, because there is NAT and many types of NAT, also router with SIP ALG

* [SIP SIMPLE Client SDK](http://sipsimpleclient.org/projects/sipsimpleclient/wiki/SipCoreApiDocumentation): introduction to SIP core library, but it gives an overview of how

## SIP
> The **Session Initiation Protocol** (**SIP**) is a [communications protocol](https://en.wikipedia.org/wiki/Communications_protocol) for [signaling](https://en.wikipedia.org/wiki/Signaling_(telecommunications)) and controlling multimedia [communication sessions](https://en.wikipedia.org/wiki/Communication_session) in applications of [Internet telephony](https://en.wikipedia.org/wiki/Internet_telephony) for voice and video calls, in private IP telephone systems, as well as in [instant messaging](https://en.wikipedia.org/wiki/Instant_messaging) over [Internet Protocol](https://en.wikipedia.org/wiki/Internet_Protocol) (IP) networks.

![](https://cdn-images-1.medium.com/max/2000/0*QBmsgWtKc5q30xgb.jpeg)

* [Session Initiation Protocol](https://en.wikipedia.org/wiki/Session_Initiation_Protocol)

* [RFC 3261](https://www.ietf.org/rfc/rfc3261.txt): to understand SIP, we need to read its standard. I don’t know how many times I read this RFC.

* [OpenSIPS](http://www.opensips.org): OpenSIPS is a multi-functional, multi-purpose signaling SIP server

* [SIP protocol structure through an example](http://www.tech-invite.com/fo-sip/tinv-fo-sip-archi.html): this is a must read, it shows very basic but necessary knowledge

* [Relation among Call, Dialog, Transaction & Message](http://www.siptutorial.net/SIP/relation.html): basic concepts about call, dialog, transaction and message

* [microSIP](https://www.microsip.org): Open source portable SIP softphone for Windows based on PJSIP stack. I used to use this to test my pjsip tweaked library before building it for mobile

* [What is SIP](https://code.google.com/archive/p/csipsimple/wikis/WhatIsSIP.wiki): introduction to SIP written by the author of CSipSimple

* [What is SIP proxy server](https://www.onsip.com/blog/sip-proxy-server)

* [SIP by Wireshack](https://wiki.wireshark.org/SIP): introduction to SIP written by Wireshack. I used Wireshack a lot to intercept and debug SIP sessions

* [Solving the Firewall/NAT Traversal Issue of SIP](http://www.ingate.com/files/Solving_Firewall-NAT_Traversal.pdf): this shows how NAT can be a problem to SIP applications and how NAT traversal works

* [Introduction to SIP for Java, C#, and VB Developers](https://www.codeproject.com/Articles/97657/Introduction-to-SIP-for-Java-C-and-VB-Developers)

* [SipML5](https://www.doubango.org/sipml5/) SIP client written in Javascript

* [SIP Retransmissions](https://wiki.asterisk.org/wiki/display/AST/SIP+Retransmissions): what and how to handle retransmission

* [draft-ietf-sipping-dialogusage-06](https://tools.ietf.org/html/draft-ietf-sipping-dialogusage-06): this is a draft about Multiple Dialog Usages in the Session Initiation Protocol

* [Creating and sending INVITE and CANCEL SIP text messages](https://docs.switzernet.com/people/emin-gabrielyan/070403-sip-invite-cancel/): SIP also supports sending text message, not just audio and video packages. This isa good for chat application

## SIP server

* [Kamailio](https://www.voip-info.org/kamailio): this is the server that I used, and it plays well with lots of standard SIP clients, including pjsip. Debugging on this server was also a fun story

![](https://cdn-images-1.medium.com/max/2000/0*2bnrKUxdiJMuqO1D.png)

* [Configuring NAT traversal using Kamailio 3.1 and the Rtpproxy server](http://nil.uniza.sk/sip/nat-fw/configuring-nat-traversal-using-kamailio-31-and-rtpproxy-server): I don’t know how many times I had read this post

* [How to set up and use SIP Server on Windows](http://www.thewindowsclub.com/set-up-sip-server-windows): I used this to test a working SIP server on Windows

* [Build your own VoIP System](https://www.sipwise.org/news/technical/byov-system-spce-as-sbc/)

* [OpenSIPS/Kamailio serving far end nat traversal](https://puck.nether.net/pipermail/voiceops/2011-May/002512.html): discussion about how Kamailio deals with NAT traversal

* [NAT Traversal Module](http://kamailio.org/docs/modules/3.0.x/modules_k/nat_traversal.html): how NAT traversal works in Kamailio as a module

## RFC

RTP, SIP clients and server need to conform to some predefined protocols to meet standard and to be able to talk with each other. You need to read [RFC](https://en.wikipedia.org/wiki/Request_for_Comments) a lot, besides you need to read some drafts.

* [RFC 3550 - RTP: A Transport Protocol for Real-Time Applications](https://tools.ietf.org/html/rfc3550)

* [RFC 3261 - SIP: Session Initiation Protocol](https://tools.ietf.org/html/rfc3261)

* [Symmetric NAT Traversal using STUN](https://tools.ietf.org/id/draft-takeda-symmetric-nat-traversal-00.txt)

* [RFC 3842 - A Message Summary and Message Waiting Indication Event Package for the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3842)

## NAT

NAT solves the problem with lack of IP, but it causes lots of problem for SIP applications, and for me as well 😂

![](https://cdn-images-1.medium.com/max/2000/0*CyseeMdKG6RWTsoM.gif)

* [Network address translation](https://en.wikipedia.org/wiki/Network_address_translation): Network address translation (NAT) is a method of remapping one IP address space into another by modifying network address information in the IP header of packets while they are in transit across a traffic routing device

* [SIP and NAT: Why is it a problem?](https://kb.smartvox.co.uk/voip-sip/sip-nat-problem/)

* [Configuring Port Address Translation (PAT)](http://www.freeccnaworkbook.com/workbooks/ccna/configuring-port-address-translation-pat-many-to-one): how to configure port forwarding

* [Types Of NAT Explained (Port Restricted NAT, etc)](http://www.think-like-a-computer.com/2011/09/16/types-of-nat/): This is a must read. I didn’t expect there’s many kinds of NAT in real life, and how each type affects SIP application in its own way

* [One Way Audio SIP Fix](http://www.think-like-a-computer.com/2011/03/14/one-way-audio-voip/): sometimes we get the problem that only 1 person can speak, this talks about why

* [NAT traversal for the SIP protocol](http://freshmeat.sourceforge.net/articles/nat-traversal-for-the-sip-protocol): explains RTP, SIP and NAT

* [A New Method for Symmetric NAT Traversal in UDP and TCP](http://www.goto.info.waseda.ac.jp/~wei/file/wei-apan-v10.pdf)

* [SIP NAT Traversal](https://voipstudio.com/sip-nat-traversal/): This is a must read. How to make SIP work under NAT

* [NAT and Firewall Traversal with STUN / TURN / ICE](http://www.viagenie.ca/publications/2008-09-24-astricon-stun-turn-ice.pdf): pjsip and Kamailio actually supports STUN, TURN and ICE protocol. Learn about these concepts and how to make it work

* [Introduction to Network Address Translation (NAT) and NAT Traversal](http://www.pjsip.org/pjnath/docs/html/group__nat__intro.htm)

## TCP

Learn how TCP helps SIP in initiating session and to turn in TCP mode for package sending

![](https://cdn-images-1.medium.com/max/2826/0*OKLXqTzL1z4-OhZO.png)

* [Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol): The Transmission Control Protocol (TCP) is one of the main protocols of the Internet protocol suite. It originated in the initial network implementation in which it complemented the Internet Protocol (IP)

* [Datagram socket](https://en.wikipedia.org/wiki/Network_socket#Datagram_socket): A datagram socket is a type of network socket which provides a connectionless point for sending or receiving data packets.[2] Each packet sent or received on a datagram socket is individually addressed and routed

* [TCP RST packet details](https://stackoverflow.com/questions/7735618/tcp-rst-packet-details): learn the important of RST bit

* [RST packet sent from application when TCP connection not getting closed properly](https://stackoverflow.com/questions/11410754/rst-packet-sent-from-application-when-tcp-connection-not-getting-closed-properly?rq=1)

* [Why will a TCP Server send a FIN immediately after accepting a connection?](https://stackoverflow.com/questions/3870260/why-will-a-tcp-server-send-a-fin-immediately-after-accepting-a-connection)

* [Where do resets come from? (No, the stork does not bring them.)](https://blogs.technet.microsoft.com/networking/2009/08/12/where-do-resets-come-from-no-the-stork-does-not-bring-them/): learn about 3 ways handshake in TCP connection

* [TCP listen() Backlog](http://www.linuxjournal.com/files/linuxjournal.com/linuxjournal/articles/023/2333/2333s2.html)

* [Sockets and Ports](http://www.freesoft.org/CIE/Course/Section4/6.htm): Do not confuse between socket and port

* [TCP Wake-Up: Reducing Keep-Alive Traffic in Mobile IPv4 and IPsec NAT Traversal](http://www.pasieronen.com/publications/NRCTR2008002.pdf)

* [failed to register using tcp only](https://code.google.com/archive/p/csipsimple/issues/1582)

* [TCP vs UDP](https://code.google.com/archive/p/csipsimple/issues/705)

## TLS

Learn about [Transport Layer Security](https://en.wikipedia.org/wiki/Transport_Layer_Security) and SSL, especially openSSL for how to secure SIP connection. The interesting thing is to read code in pjsip about how it uses openSSL to encrypt messages

* [Configuring PJSIP with TLS](https://trac.pjsip.org/repos/wiki/TLS)

* [Why TLS for SIP](https://stackoverflow.com/questions/8178963/why-tls-for-sip)

* [SIP Signaling Over TLS](http://excelsupport.dialogic.com/imgpubs/webhelp/sip_over_tls_ov.htm)

* [SSL/TLS certificates: What you need to know](https://www.techrepublic.com/blog/data-center/ssl-tls-certificates-what-you-need-to-know/)

* [Configuring TLS support in Kamailio 3.1 — Howto](http://nil.uniza.sk/network-security/tls/configuring-tls-support-kamailio-31-howto): learn how to enable TLS mode in Kamailio

* [SIP TLS](https://www.voip-info.org/sip-tls): how to configure TLS in Asterisk

## ICE

Learn about [Interactive Connectivity Establishment](https://en.wikipedia.org/wiki/Interactive_Connectivity_Establishment), another way to workaround NAT

* [SIP 2012:: ICE — NAT traversal for media](https://www.slideshare.net/oej/sip-2012-ice-nat-traversal-for-media)

* [Introducing pjnath — Open Source ICE, STUN, and TURN for NAT Traversal](https://blog.pjsip.org/2007/04/06/introducing-pjnath-open-source-ice-stun-and-turn/)

* [ICE Media Transport](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__TRANSPORT__ICE.htm)

## STUN and TURN

Learn about [Session Traversal Utilities for NAT](https://en.wikipedia.org/wiki/STUN) and [Traversal Using Relays around NAT](https://en.wikipedia.org/wiki/Traversal_Using_Relays_around_NAT), another way to workaround NAT

* [STUN](https://www.voip-info.org/stun): STUN (Simple Traversal of UDP through NATs (Network Address Translation)) is a protocol for assisting devices behind a NAT firewall or router with their packet routing. RFC 5389 redefines the term STUN as ‘Session Traversal Utilities for NAT’.

* [What is STUN and does it need a port-forwarded server?](https://stackoverflow.com/questions/13501288/what-is-stun-and-does-it-need-a-port-forwarded-server)

* [TURN server](http://turnserver.sourceforge.net)

## ALG

Learn about [Application Layer Gateway](http://Application Layer Gateway) and how it affects your SIP application. This component knows how to deal and modify your SIP message, so it might introduce unexpected behaviours.

* [What is SIP ALG and why does Gradwell recommend that I turn it off?](https://support.gradwell.com/hc/en-gb/articles/215553503)

* [Understanding the SIP ALG](https://www.juniper.net/documentation/software/junos-security/junos-security95/junos-security-swconfig-security/sip-alg-understanding.html)

* [What Is Sip ALG (Application Layer Gateway) Voip firewall](http://www.voiptuts.com/2011/02/what-is-sip-alg-application-layer.html)

* [About the SIP ALG](http://www.watchguard.com/help/docs/wsm/11/en-us/content/en-us/proxies/sip/sip_proxy_about_c.html)

* [Understanding SIP with Network Address Translation (NAT)](https://www.juniper.net/documentation/software/junos-security/junos-security96/junos-security-swconfig-security/id-60290.html): This is a must read, a very thorough document

## Voice quality

Learn about voice quality, bandwidth and fixing delay in audio

![](https://cdn-images-1.medium.com/max/2000/1*Gst1j53g8PaqkBuP6RbZZg.png)

* [VoIP — fixing voice quality](https://www.voipmechanic.com/phoneandvoicequality_2.htm)

* [What is Delay in VoIP?](https://www.lifewire.com/delay-in-voip-3426312)

* [Understanding Delay in Packet Voice Networks](https://www.cisco.com/c/en/us/support/docs/voice/voice-quality/5125-delay-details.html)

* [Reducing the SIP Packet Size in VoIP](https://hubpages.com/technology/Reducing-the-SIP-Packet-Size-in-VoIP)

* [What Affects Voice Quality in VoIP Calls](https://www.lifewire.com/what-affects-voice-quality-in-voip-calls-3426724)

* [5 Curable Causes of Poor VoIP Call Quality](https://www.voip-info.org/5-curable-causes-of-poor-voip-call-quality)

* [RTP, Jitter and audio quality in VoIP](https://kb.smartvox.co.uk/voip-sip/rtp-jitter-audio-quality-voip/): learn about the important of jitter and RTP

* [An Adaptive Codec Switching Scheme for SIP-based VoIP](https://www.comsys.rwth-aachen.de/fileadmin/papers/2012/2012-aktas-new2an-codecswitching.pdf): explain codec switching during call in SIP based VoIP

* [How to master VoIP bandwidth fundamentals](https://searchunifiedcommunications.techtarget.com/tutorial/VoIP-bandwidth-fundamentals)

* [Voice Over IP — Per Call Bandwidth Consumption](https://www.cisco.com/c/en/us/support/docs/voice/voice-quality/7934-bwidth-consume.html)

## Echo

This is a very common problem in VoIP, sometimes we hear voice from the other and also from us. Learn how echo is made, and how to effectively do echo cancellation

![](https://cdn-images-1.medium.com/max/2000/0*GyZHcz0TKL_UHdYJ.png)

* [Echo Analysis for Voice over IP](https://www.cisco.com/c/en/us/td/docs/ios/solutions_docs/voip_solutions/EA_ISD.html)

* [Echo Cancellation](https://www.speex.org/docs/manual/speex-manual/node7.html#SECTION00740000000000000000): How to use Speex to cancel echo

* [Echo suppression and cancellation](https://en.wikipedia.org/wiki/Echo_suppression_and_cancellation)

* [Echo and Sidetone](https://www.voip-info.org/echo-and-sidetone): A telephone is a duplex device, meaning it is both transmitting and receiving on the same pair of wires. The phone network must ensure that not too much of the caller’s voice is fed back into his or her receiver

* [VoIP Echo and how to correct it](https://www.voipmechanic.com/echo-technical.htm)

* [Causes of Echo](https://www.voip-info.org/causes-of-echo)

* [How software echo canceller works?](https://stackoverflow.com/questions/18870124/how-software-echo-canceller-works): I asked about how we use software to do echo cancellation

## Dual Tone

Learn how to generate dual tone to make signal in telecommunication

* [DTMF (Dual-Tone Multi-Frequency)](https://www.mediacollege.com/audio/tone/dtmf.html)

* [The dance of DTMF, SIP & RFC 2833 — An introduction](https://www.3cx.com/blog/voip-howto/dtmf-rfc2833/)

* [How can I send inband DTMF tones?](https://trac.pjsip.org/repos/wiki/FAQ#dtmf)

## pjsip
> PJSIP is a free and [open source](http://www.pjsip.org/about.htm#opensource) multimedia communication library written in C language implementing standard based protocols such as SIP, SDP, RTP, STUN, TURN, and ICE. It combines signaling protocol (SIP) with rich multimedia framework and NAT traversal functionality into high level API that is portable and suitable for almost any type of systems ranging from desktops, embedded systems, to mobile handsets.

![](https://cdn-images-1.medium.com/max/2000/0*E82pcZW_6lhy8l1H.jpg)

* [PJSUA API — High Level Softphone API](http://www.pjsip.org/pjsip/docs/html/group__PJSUA__LIB.htm): high level usage of pjsip

* [pjsip library architecture](https://www.scribd.com/document/55939030/Suresh-Report-Voip1)

* [pjsip documentation](https://trac.pjsip.org/repos/)

![](https://cdn-images-1.medium.com/max/2000/0*e4Lr7TxJlSdQhA-b.png)

* [Stateful Operations](http://www.pjsip.org/pjsip/docs/html/group__PJSIP__TRANSACT__UTIL.htm): common functions to send request statefully

* [Message Creation and Stateless Operations](http://www.pjsip.org/pjsip/docs/html/group__PJSIP__ENDPT__STATELESS.htm): functions related to send and receive messages

* [Understanding Media Flow](https://trac.pjsip.org/repos/wiki/media-flow#IncomingRTPRTCPPackets): this is a must read. The media layer is so important, it controls sound, codec and conference bridge.

![](https://cdn-images-1.medium.com/max/2000/1*oEs7lMDuaSG-En-R7ig-og.png)

* [Getting Started: Building and Using PJSIP and PJMEDIA](http://www.pjsip.org/using.htm): This article describes how to download, customize, build, and use the open source PJSIP and PJMEDIA SIP and media stack

* [Codec Framework](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__CODEC.htm): pjsip supports multiple codec

* [Adaptive jitter buffer](http://www.pjsip.org/pjmedia/docs/html/group__PJMED__JBUF.htm): this takes sometime to understand, but it plays an important part in making pjsip work properly regarding buffer handling

* [PJSUA-API Accounts Management](http://www.pjsip.org/pjsip/docs/html/group__PJSUA__LIB__ACC.htm): how to register account in pjsua

* [Building Dynamic Link Libraries (DLL/DSO)](http://www.pjsip.org/pjlib/docs/html/group__pj__dll__target.htm): how to build pjsip as a dynamic library

* [Compile time configuration](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__CONFIG.htm): lots of configuration we can apply to pjsip

* [Fast Memory Pool](http://www.pjsip.org/pjlib/docs/html/group__PJ__POOL__GROUP.htm): pjsip has its own memory pool. It’s very interesting to look at the source code and learn something new

* [SIP and Media Features](http://www.pjsip.org/sip_media_features.htm)

* [Using SIP TCP Transport](https://trac.pjsip.org/repos/wiki/Using_SIP_TCP): How to enable TCP mode in SIP and to initiate SIP session

* [Monochannel and multichannel audio frame converter](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__STEREO.htm): interesting read about mono and multi channel

* [IOQueue: I/O Event Dispatching with Proactor Pattern](http://www.pjsip.org/pjlib/docs/html/group__PJ__IOQUEUE.htm): the code for this is very interesting and plays a fundamental in how pjsip handles events

* [DNS Asynchronous/Caching Resolution Engine](http://www.pjsip.org/pjlib-util/docs/html/group__PJ__DNS__RESOLVER.htm): how pjsip handles DNS resolution by itself

![](https://cdn-images-1.medium.com/max/2000/0*VBotMl-b9232q1JL.png)

* [Secure socket I/O](http://www.pjsip.org/pjlib/docs/html/group__PJ__SSL__SOCK.htm): the code for this is important if you want to learn how to use SSL under the hood

* [Multi-frequency tone generator](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__MF__DTMF__TONE__GENERATOR.htm): I learn a lot how pjsip uses sin wave to generate tone

* [SIP SRV Server Resolution (RFC 3263 — Locating SIP Servers)](http://www.pjsip.org/pjsip/docs/html/group__PJSIP__RESOLVE.htm): learn the mechanism for how pjsip finds a particular SIP server

* [Exception Handling](http://www.pjsip.org/pjlib/docs/html/group__PJ__EXCEPT.htm): how to do Try Catch in C

* [Mutex Locks Order in PJSUA-LIB](https://trac.pjsip.org/repos/wiki/PJSUA_Locks): how multiple locks at each layer helps ensure correction and avoid deadlocks. I had lots of nightmare debugging deadlocks with pjsip 😱

## Threading

pjsip uses [Local Thread Storage](https://en.wikipedia.org/wiki/Thread-local_storage) which introduces very cool behaviors

![](https://cdn-images-1.medium.com/max/2000/0*rD0iy3joZsBXsMYo.png)

* [Thread — Operating System Dependent Functionality](http://www.pjsip.org/pjlib/docs/html/group__PJ__THREAD.htm)

* [Threads question](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2009-April/006997.html): how pjlib handles thread

* [Using Thread Local Storage](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686991(v=vs.85).aspx): how to use TlsAlloc and TlsFree in Windows

* [The Windows Processes and Threads 8](http://www.installsetupconfig.com/win32programming/windowsthreadsprocessapis7_7.html)

* [Example: Thread local storage in a Pthread program](https://www.ibm.com/support/knowledgecenter/ssw_ibm_i_61/rzahw/rzahwex1.htm): how Pthread works

* [Thread Local Storage](http://www.pjsip.org/pjlib/docs/html/group__PJ__TLS.htm): learn about pj_thread

## Resampling

How to work with sample rate of the media stream

![](https://cdn-images-1.medium.com/max/2000/0*DkP_SZQGZaSdvZAF.jpg)

* [Resample Port](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__RESAMPLE__PORT.htm): how to perform resampling in pjmedia

* Resampling Algorithm: code to perform resampling

* [Samples: Using Resample Port](http://www.pjsip.org/pjmedia/docs/html/page_pjmedia_samples_resampleplay_c.htm): very straightforward example to change sample rate of the media stream

## Memory and Performance

* [Memory allocation strategy](http://comments.gmane.org/gmane.comp.voip.pjsip/14219)

* [PJSIP — High Performance Open Source SIP Stack](http://www.pjsip.org/high-performance-sip.htm)

## Audio

* [How to Record Audio with pjsua](https://trac.pjsip.org/repos/wiki/audio-how-to-record): how to use pjsua to record audio.

* [Memory/Buffer-based Capture Port](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__MEM__CAPTURE.htm): believe me, you will jump into pjmedia_mem_capture_create a lot

* [File Writer (Recorder)](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__FILE__REC.htm): record audio to .wav file

* [Using pjsua to create a mp3 stream](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2008-February/001838.html)

* [AMR Audio Encoding](https://www.codeproject.com/Articles/332109/AMR-Audio-Encoding): understands AMR encoding

* [Audio Device API](http://www.pjsip.org/pjmedia/docs/html/group__audio__device__api.htm): how pjsip detects and use Audio device

* [Sound Device Port](http://www.pjsip.org/pjmedia/docs/html/group__PJMED__SND__PORT.htm): Media Port Connection Abstraction to the Sound Device

* [audio bursting](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2009-December/009719.html)

* [Buffer problem](http://comments.gmane.org/gmane.comp.voip.pjsip/11623)

* [Problem with PJMEDIA’s play callback](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2009-March/006783.html)

* [Audio Manipulation Algorithms](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__FRAME__OP.htm): lots of cool algorithm written in C for audio manipulation. The hardest and most imporant one is probably [Adaptive jitter buffer](http://www.pjsip.org/pjmedia/docs/html/group__PJMED__JBUF.htm)

* [bad quality on iphone 2G with os 3.0](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2010-January/010167.html): No one would use iPhone 2G now, but it’s good to be aware of older phones

* [getting Underflow, buf_cnt=0, will generate 1 frame continuessly](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2009-April/007265.html): how to handle underflow in pjmedia

* [Measuring Sound Latency](https://trac.pjsip.org/repos/wiki/MeasuringSoundLatency): This article describes how to measure both sound device latency and overall (end-to-end) latency of ​pjsua

* [Checking for Network Impairments of Incoming RTP Packets](https://trac.pjsip.org/repos/wiki/audio-check-packet-loss)

* [Master/sound](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2013-January/015647.html): How master sound works and deal with no sound on the mic input port

## Video

I learn a lot regarding video capture, ffmpeg and color space, especially YUV

* [siphon — VIdeoSupport.wiki](https://code.google.com/archive/p/siphon/wikis/VIdeoSupport.wiki): How siphon deals with video before pjsip 2.0

* [Video Device API](http://www.pjsip.org/pjmedia/docs/html/group__video__device__api.htm); PJMEDIA Video Device API is a cross-platform video API appropriate for use with VoIP applications and many other types of video streaming applications.

* [PJSUA-API Video](http://www.pjsip.org/pjsip/docs/html/group__PJSUA__LIB__VIDEO.htm): Uses video APIs in pjsua with pjsip 2.1.0

* [PJSIP Video User’s Guide](https://trac.pjsip.org/repos/wiki/Video_Users_Guide): all you need to know about video support in pjsip

* [Video streams](http://www.pjsip.org/pjmedia/docs/html/group__PJMED__VID__STRM.htm): I can’t never forget pjmedia_vid_stream_create

* [Video source duplicator](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__VID__TEE.htm): duplicate video data in the stream.

* [AVI File Player](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__FILE__PLAY.htm): Video and audio playback from AVI file

* [PJSIP Version 2.0 Release Notes](https://trac.pjsip.org/repos/wiki/ReleaseNotes-2.0): starting with 2.0, pjsip supports video. Good to read

* [Video API for PJSUA-LIB](https://trac.pjsip.org/repos/ticket/1263)

* [How to make a loopback video call with AVI file?](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2012-July/014959.html)

* [What is lib Swscale used for by ffmpeg programers?](https://stackoverflow.com/questions/3367187/what-is-lib-swscale-used-for-by-ffmpeg-programers)

* [FFmpeg-iOS-build-script](https://github.com/dmcrodrigues/FFmpeg-iOS-build-script): details how to build ffmpeg for iOS

## CSipSimple

There are many SIP client for mobile and desktop, [microSIP](https://www.microsip.org/), [Jitsi](https://jitsi.org/), [Linphone](https://www.linphone.org/technical-corner/linphone/overview), [Doubango](https://www.doubango.org/), … They all follow strictly SIP standard and may have their own SIP core, for example microSIP uses pjsip, Linphone uses liblinphone, …

Among that, I learn a lot from the Android client, [CSipSimple](https://code.google.com/archive/p/csipsimple/), which offers very nice interface and have good functionalities. Unfortunately [Google Code was closed](https://github.com/r3gis3r/CSipSimple/issues/6), so I don’t know if the author has plan to do development on GitHub.

I also participated a lot on the Google forum for [user](https://groups.google.com/forum/#!searchin/csipsimple-users/onmyway133%7Csort:date) and [dev](https://groups.google.com/forum/#!searchin/csipsimple-dev/onmyway133%7Csort:date). Thanks for Regis, I learn a lot about open source and that made me interested in open source.

You can read [What is a branded version](https://groups.google.com/forum/#!topic/csipsimple-dev/ihZN8s_-g_4)
> I don’t make any money from csipsimple at all. It’s a pure opensource and free as in speech project.
> I develop it on my free time and just so that it benefit users. 
That’s the reason why the project is released under GPL license terms. I advise you to read carefully the license (you’ll learn a lot of things on the spirit of the license and the project) : [http://www.gnu.org/licenses/gpl.html](http://www.gnu.org/licenses/gpl.html)
> To sump up, the spirit of the GPL is that users should be always allowed to see the source code of the software they use, to use it the way they want and to redistribute it.

## RTP Proxy

Because of NAT or in case users want to talk via a proxy, then a [RTP proxy](http://www.rtpproxy.org/) is needed. RTPProxy follows standard and works well with Kamailio

* [Making RTPproxy work](https://saevolgo.blogspot.no/2012/03/making-rtpproxy-work.html)

* [Sippy B2BUA and RFC3261 SIP Stack](https://sourceforge.net/p/sippy/rtpproxy/ci/master/tree/)

* [rtpproxy(8) — Linux man page](https://linux.die.net/man/8/rtpproxy)

* [rtpproxy address filling](https://lists.kamailio.org//pipermail/sr-users/2008-April/062814.html)

## Other related articles

* [Sample Rate and Bitrate: The Guts of Digital Audio](https://thestereobus.com/2008/01/12/sample-rate-and-bitrate-the-guts-of-digital-audio/)

* [VoIP Packet Size](http://webcache.googleusercontent.com/search?q=cache:http://www.techexams.net/forums/ccnp/48768-voip-packet-size.html)

* [How to measure brandwith consumption of an rtp stream?](https://lists.freedesktop.org/archives/gstreamer-devel/2012-August/036865.html)

* [Sending Reliable Provisional Responses](https://docs.microsoft.com/en-us/previous-versions/office/developer/communication-server-2007/bb759215(v=office.12))

* [SILK audio codec wrapper implementation](https://trac.pjsip.org/repos/ticket/1586)

* [conference bridge questions](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2008-July/003843.html)

* [multiple audio devices, multiple calls, conferencing, recording and mix all of the above](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2012-January/014037.html)

* [How to Know Offline Call](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2010-January/010089.html)

* [Symmetric RTP](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2008-May/002857.html)

* [Account specific NAT settings: STUN, ICE, and TURN](https://trac.pjsip.org/repos/ticket/1412)

* [SIP stories, part 3: INVITE retransmission](https://technfun.wordpress.com/2008/11/06/sip-stories-part-3-invite-retransmission/)

* [TCP/TLS reconnect](http://lists.pjsip.org/pipermail/pjsip_lists.pjsip.org/2010-February/010329.html)

* [Configuring TCP keep alive and connection lifetime](https://lists.kamailio.org//pipermail/sr-users/2010-May/063880.html)

* [Max TCP connections](http://lists.opensips.org/pipermail/users/2012-September/023057.html)

* [VAD detection scenario](http://comments.gmane.org/gmane.comp.voip.pjsip/836)

* [Handle native capture preview](https://trac.pjsip.org/repos/ticket/1340)

* [Video orientation support](https://trac.pjsip.org/repos/ticket/1360)

* [Keep-alive mechanism for TCP and TLS transports](https://trac.pjsip.org/repos/ticket/95)

* [Periodically transmit RTP packet on silence](https://trac.pjsip.org/repos/ticket/56)

* [Conference bridge should transmit silence frame when level is zero](https://trac.pjsip.org/repos/ticket/87)

* [Add user defined NAT hole-punching and keep-alive mechanism to media stream](https://trac.pjsip.org/repos/ticket/883)

## IP change

IP change during call can cause problem, such as when user goes from Wifi to 4G mode

* [Proper way to handle Ip address changes in Android](http://comments.gmane.org/gmane.comp.voip.pjsip/16134)

* [support WiFi and 3G simultaneously](https://code.google.com/archive/p/csipsimple/issues/1423)

## RTP and RTCP

Learn about [Realtime transport control protocol](http://Real-time Transport Protocol) and how that works with RTP

* [Voice over IP: RTP/RTCP — The transport layer](http://disi.unitn.it/locigno/didattica/AdNet/10-11/05-5_VoIP-RTP_H.pdf)

* [RTCP, RTP Control Protocol](http://www.networksorcery.com/enp/protocol/rtcp.htm)

* [Protocol overview: RTP and RTCP](http://www.netlab.tkk.fi/opetus/s38130/k99/presentations/4.pdf)

* [The Multimedia Control Protocol RTCP](http://www.cs.odu.edu/~cs778/jeffay/Lecture6.pdf)

* [Using Conference Bridge](http://www.pjsip.org/pjmedia/docs/html/page_pjmedia_samples_confsample_c.htm)

* [SIP and RTP Stack](http://docs.huihoo.com/telecom/sip_rtp_stack.html)

* [Media Transport](http://www.pjsip.org/pjmedia/docs/html/group__PJMEDIA__TRANSPORT.htm)

* [RTP Session and Encapsulation (RFC 3550)](http://www.pjsip.org/pjmedia/docs/html/group__PJMED__RTP.htm)

## Codec

To reduce payload size, we need to encode and decode the audio and video package. We usually use [Speex](https://www.speex.org/) and [Opus](https://opus-codec.org/). Also, it’s good to understand the .wav format

* [Digital Audio — Creating a WAV (RIFF) file](http://www.topherlee.com/software/pcm-tut-wavformat.html)

* [Streaming Data from a WAV File](https://docs.microsoft.com/en-us/previous-versions/windows/xna/ff827591(v=xnagamestudio.41))

* [Programming with Speex (the libspeex API)](https://www.speex.org/docs/manual/speex-manual/node7.html)

* [Speex narrowband mode](https://www.speex.org/docs/manual/speex-manual/node10.html)

* [Developing with libopus (API reference)](http://www.opus-codec.org/docs/)

## Building pjsip for Windows Phone 8

Windows Phone 8 introduces C++ component , changes in threading, VoIP and audio background mode. To do this I need to find another threadpool component and tweak openSSL a bit to make it compile on Windows Phone 8. I lost the source code so can’t upload the code to GitHub 😢. Also many links broke because Nokia was not here any more

* [Building for Other Platforms](https://trac.pjsip.org/repos/wiki/Getting-Started/Other-Platforms)

* [Getting Started: Building for UWP and Windows Phone 8.x](https://trac.pjsip.org/repos/wiki/Getting-Started/Windows-Phone)

* [Porting to New CPU Architecture](http://www.pjsip.org/docs/latest/pjlib/docs/html/porting_pjlib_pg.htm): pjlib is the foundation of pjsip. Learn how to port it to another platform

* [VoIP apps for Windows Phone 8](https://docs.microsoft.com/en-us/previous-versions/windows/desktop/apps/jj206983(v=vs.105))

* [How to implement audio streaming for VoIP calls for Windows Phone 8](https://docs.microsoft.com/en-us/previous-versions/windows/desktop/apps/jj207046(v=vs.105))

* [In-process, Out-of-process, and Remote Servers](http://docs.embarcadero.com/products/rad_studio/delphiAndcpp2009/HelpUpdate2/EN/html/devwin32/oocinprocessoutofprocessandremoteservers_xml.html)

* [Basics of an IDL file](https://www.codeproject.com/Articles/19605/Basics-of-an-IDL-file)

## Porting OpenSSL to Windows Phone 8

Firstly, learn how to compile, use OpenSSL. How to call it from pjsip, and how to make it compile in Visual Studio for Windows Phone 8. I also learn the important of Winsock, how to port a library. I struggled a lot with porting openSSL to Windows RT, then to Windows Phone 8

A lot of links were broken 😢 so I can’t paste them all here.

* [An Introduction to OpenSSL Programming](https://www.linuxjournal.com/article/4822)

* [SSL Socket support in Windows Phone](https://mikaelkoskinen.net/post/ssl-socket-support-in-windows-phone)

* [Building Secure Windows Phone 8 Apps — APIs and Techniques](http://www.markarteaga.com/building-secure-windows-phone-8-apps-apis-and-techniques/)

* [Is Winsock available on Windows Phone 8?](https://social.msdn.microsoft.com/forums/windowsapps/en-US/8f3c82e6-3b42-4138-9342-f9d687ee6466/is-winsock-available-on-windows-phone-8)

* [Why i am not been able to use all the header files (eg->ssl.h) under open source openssl library](https://social.msdn.microsoft.com/Forums/windowsapps/en-US/2662cac1-fbb6-4ac4-8553-06375d798720/why-i-am-not-been-able-to-use-all-the-header-files-egsslh-under-open-source-openssl-library-)

* [Getting Started with Winsock](https://msdn.microsoft.com/en-us/library/windows/desktop/ms738545(v=vs.85).aspx)

* [Building OpenSSL for Visual Studio](http://developer.covenanteyes.com/building-openssl-for-visual-studio/)

* [How to Compile OpenSSL for Visual Studio 2010/2012](http://eran.geek.co.il/wp/archives/3897)

* [OpenSSL for Windows](http://www.blogcompiler.com/2011/12/21/openssl-for-windows/)

* [OpenSSL for Windows RT](https://forum.xda-developers.com/showthread.php?t=2113595)

* [2911: enhancement request: Windows RT support](https://rt.openssl.org/Ticket/Display.html?id=2911&user=guest&pass=guest)

* [Need a fast random generator for c++](https://stackoverflow.com/questions/1640258/need-a-fast-random-generator-for-c)

* [Window C/C++ Crypto API Examples and tips](https://stackoverflow.com/questions/4796590/window-c-c-crypto-api-examples-and-tips)

* [CryptGenRandom function](https://msdn.microsoft.com/en-us/library/windows/desktop/aa379942(v=vs.85).aspx)

* [EGD: The Entropy Gathering Daemon](http://egd.sourceforge.net)

## C and C++

Since pjsip, rtpproxy and kamailio are all C and C++ code. I needed to have a good understanding about them, especially pointer and memory handling. We also needed to learn about compile flags for debug and release builds, how to use Make, how to make static and dynamic libraries.

* [What does a const pointer-to-pointer mean in C and in C++?](https://stackoverflow.com/questions/336585/what-does-a-const-pointer-to-pointer-mean-in-c-and-in-c)

* [comp.lang.c Frequently Asked Questions](http://c-faq.com/index.html): there’s lot of things about C we haven’t known about

* [What is external linkage and internal linkage?](https://stackoverflow.com/questions/1358400/what-is-external-linkage-and-internal-linkage)

* [Bit Twiddling Hacks](http://graphics.stanford.edu/~seander/bithacks.html): how to apply clever hacks with bit operators. Really really good reading here

* [Better types in C++11 — nullptr, enum classes (strongly typed enumerations) and cstdint](https://www.cprogramming.com/c++11/c++11-nullptr-strongly-typed-enum-class.html)

* [Microsoft Visual C++ Static and Dynamic Libraries](https://www.codeproject.com/Articles/85391/Microsoft-Visual-C-Static-and-Dynamic-Libraries)

* [Managed C++ — Learn by Example](https://www.codeproject.com/Articles/11634/Managed-C-Learn-by-Example-Part-1)

* [Preprocessor directives](http://www.cplusplus.com/doc/tutorial/preprocessor/)
