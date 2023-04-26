---
published: true
subtitle: 
date: 2023-04-26
tags: 
---

# 2023-04 linguistic steganography notes

### [[Frustratingly Easy Edit-based Linguistic Steganography with a Masked Language Model.pdf]]
*Formally, the goal of linguistic steganography is to create a steganographic system (stegosystem) with which the sender Alice encodes a secret message, usually in the form of a bit sequence, into a text and the receiver Bob decodes the message, with the requirement that the text is so natural that even if transmitted in a public channel, it does not arouse the suspicion of the eavesdropper Eve.

#### traditional edit based approach
synonym substitution
*a bit chunk was assigned to each member of a synonym group, for example, ‘0’ to marry and ‘1’ to wed. The cover text She will marry him was then modified to the stego text She will wed him such that the latter carried the secret bit sequence ‘1’.

#### generative approach 
bit chunks are directly assigned to the conditional probability distribution over the next word estimated by the LM

#### Masked LM

this is usually an intermediary step in training a model

eliminates painstaking rule construction because it readily offers a list of words applicable in the context.

higher payload (many bits can be encoded) than traditional edit based approaches. less than generative approach but better control over security

*Given a text in which some tokens were replaced with the special token MASK, the masked LM is trained to recover the original tokens based only on their context. As a result of the training, it provides a [[probability distribution]] over the vocabulary for each masked token according to the applicability in the given context. Note that high probability items are not necessarily synonymous with the original tokens but nevertheless fit into the context.

*we can use these probability distributions to encode a secret message in the form of a bit sequence