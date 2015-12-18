# PERC Requirements

This document outlines the requirements guiding the work in the
[Privacy Enhanced RTP Conferencing](https://datatracker.ietf.org/wg/perc/charter/)
(PERC) working group in the IETF.

The PERC working group was chartered to improve communications security
when using cloud-based conferencing systems.  Appreciating the fact that
an adversary might be able to monitor traffic to and from a conferencing
server, or that an adversary might be able to gain access to the
conferencing server itself, the goal of the work is to render access to
the media flows or the conferencing server effectively useless.  The
way this was to be accomplished was by encrypting all media flows
transmitted to the server from each endpoint, with all endpoints knowing
a shared secret.  Further, the conference server itself would not have
access to the key material, meaning that even if the server was
compromised the attacker could not gain access to the unencrypted
media.

Since the conference server cannot decrypt media, the conference server
operates differently than the traditional multipoint conferencing unit
(MCU) found in legacy enterprise deployments.  The conference server
cannot mix, transcode, transrate, or otherwise manipulate media flows.
What it can do is switch the media from one active speaker to another.
Since the behavior of this conference server is, in effect, a switching
media server that distributes media to conference participants, the IETF
elected to introduce the term “media distribution device” (MDD) to
describe this conferencing function.  While the MDD is unable to
manipulate media, conference participants provide clues in plaintext
about who the active speaker is.  This allows the MDD to switch media
for the active speaker(s) by relying on intelligent endpoints and
implementing simple switching logic.  Further, since the MDD is not
performing heavy processing on the media, these devices are much more
suitable for deployment in cloud networks where processing power is
limited.  Basically, the MDD just forwards media it receives onward to
the recipient(s) in the conference, perhaps only serving to limit the
number of flows sent to any one endpoint, selecting which video flows
from a speaker to send if there are various resolutions available, etc.
In contrast, legacy MCUs were often outfitted with expensive and
specialized hardware to decrypt audio and video flows, mix media, etc.
that make them very impractical for deploying in cloud networks.

This document is not targeted to be an RFC, but was written as an aid in
the development of the solution.

The markdown used is consumable by
[mmark](https://github.com/miekg/mmark) markdown processor.

