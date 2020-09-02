# Basic WebRTC

## Signaling and video calling

### <a name="sdp">SDP</a>
*Session Description Protocol* standard describing a peer-to-peer connection. Contains the codec, source address, and timing information of audio and video.
Never used alone, but by protocols like [RTP](#rtp-srtp) and [RTSP](#rtsp). Also as component of WebRTC.

### <a name="ice">ICE</a>
*Interactive Connectivity Establishment* is a framework used by WebRTC for connecting two peers, regardless of network topology (usually for audio and video chat).
This protocol lets two peers find and establish a connection with one another event though they may both be using NAT.

The framework algorithm looks for the lowest-latency path for connecting the two peers, trying these options in order:

1. Direct UDP connection (A [STUN](#stun)  server is used to find the network-facing address of a peer)
2. Direct TCP connection, via HTTP port
3. Direct TCP connection, via HTTPS port
4. Indirect connection via a relay/TURN server (if a direct connection fails)

### <a name="stun">STUN</a>
*Session Traversal Utilities for NAT* is an auxiliary protocol for transmitting data around a NAT (Network Address Translator). **STUN** return the IP address, port, and connectivity status of a networked computer behind a NAT.

### <a name="rtp-srtp">RTP/SRTP</a>
*Real-time Transport Protocol* is a network protocol which described how to transmit various media(audio, video) from one endpoiknt to another in a real-time fashion.
The secure version of RTP, **SRTP**, is used by *WebRTC*, and uses encryption and authentication to minimize the risk of denial-of-service attacks and security breaches.
RTP is rarely used aline; instead, it is used in conjunction with other protocols like [RTSP](#rtsp) and [SDP](#sdp)

### <a name="rtsp">RTSP</a>
*Real-Time Streaming Protocol* is a network protocol that controls how the streaming of a media should occur between a server and a client. Basically, *RTSP* describes what happens when you click "Pause"/"Play" when streaming a vide. If you computer where a remote control and the streaming server a television, RTSP  would describe how the instruction of the remote control affects the TV.
