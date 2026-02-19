# SIP Dialog Basics: INVITE Transaction Walkthrough

This repository demonstrates the basic SIP call establishment process using a minimal INVITE transaction (INVITE -> 200 OK -> ACK).
The goal is to illustrate how a SIP dialog is formed and how signaling works before RTP media transmission begins.

## What is SIP?
Session Initiation Protocol (SIP) is a signaling protocol used to establish, modify, and terminate multimedia sessions such as VoIP calls.
SIP does NOT carry voice data.
RTP (Real-time Transport Protocol) carries the actual media.

## Basic SIP Call Flow

```
Alice                         Bob
  | -------- INVITE --------> |
  | <------- 200 OK --------- |
  | --------- ACK ----------> |
```

1. INVITE – Initiates the session.
2. 200 OK – Accepts the session.
3. ACK – Confirms receipt of the final response and completes the handshake.

## Dialog Identification
A SIP dialog is uniquely identified by:
Call-ID + From tag + To tag
- Call-ID identifies the call attempt.
- From tag identifies the caller side.
- To tag identifies the callee side.
When both tags exist along with the Call-ID, the dialog is established.

## After ACK
After the ACK is sent, SIP signaling for session establishment is complete.
Media transmission begins using RTP.
SIP continues to manage signaling (e.g., BYE, re-INVITE), but voice packets flow over RTP.

## Key SIP Headers Explained
- Via: Tracks the transport path and prevents routing loops.
- From: Identifies the caller.
- To: Identifies the callee.
- Call-ID: Unique identifier for the session.
- CSeq: Maintains transaction order.
- Contact: Indicates where future requests should be sent.




