# Verifiable Credentials and Authenticated Media

by [Eric Scouten](mailto:scouten@adobe.com) and [Leonard Rosenthol](lrosenth@adobe.com), Adobe

## The Problem Space

In recent years, technology advances have made it increasingly easy to produce highly-realistic, but synthetic, digital media (photography, videography, audio recordings, etc.). In this same time frame, social media and other Internet technologies have gained prominence as a means for disseminating news, opinion, and digital media related to current events.

While this makes it possible for valid information about a rapidly-evolving event to be propagated quickly, it also makes it possible for **misinformation** to be introduced and widely viewed. There are numerous examples of deepfakes or intentionally-misattributed media being used to inflame tensions around the world.

Consumers of digital media have insufficient information available to them to distinguish legitimate reportage from misattributed or outright false media.

## Proposed Solution

We are interested in providing standards to allow legitimate media producers to state claims about their work and to allow motivated media consumers to verify those claims. For the purposes of this paper, we'll refer to such media as **authenticated media.**

Broadly speaking, we expect this to allow some or all of the following information to be verifiably claimed:

* Cryptographic verification of media contents
* Information about time and location of capture
* Audit trail of manipulations performed between capture and presentation
* Identity of those involved in capture, manipulation, and presentation

## Specific Questions of Interest

Each of these pose interesting technical and societal challenges, but it is the last one, _identity,_ that we are particularly interested in diving into for this paper. Some of the key questions we are considering include:

* How do we connect a user to an asset for the purposes of authentic media?
* What control would users want/need to have with regard to revealing/concealing said identity?  And would that control be part of the media or managed separately (or both)?
* What measures need to be taken to ensure that an authenticated workflow does not _inadvertently_ reveal identity when that could cause harm to an author?
* If identity is known, could that be used to aid in reputation/trust? Could that be done without disclosure of the actual identity? (Or does even "reputation" impact anonymity?)
