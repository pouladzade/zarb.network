---
id: transaction-bond
title: Bond transaction
---

# Bond transaction

Bond transaction is used to bond stake to a validator. If validator doesn't exist it will be
created.

Bond transaction has a payload like below:

```go
type BondPayload struct {
   Bonder    Address   `cbor:"1,keyasint"`
   Validator PublicKey `cbor:"2,keyasint"`
   Stake     int64     `cbor:"3,keyasint"`
}
```

For example a raw bond transaction will look like this:

```
a90101025820401a78337d2715db2a69916bbedbbb0a44336915fa1e5938b5b9cf350c340bb603186e0400050206a30154ebd6d0afdbe2ac5968224763f1c2dbb99fedda53025860c0ac961b453008e5cf521afab81fe303dc957de4b385bf472108e27b054f14e2da340f288928472b443a716eb795800cd8b885791827debda0a7909c741286cebd324db9546bab8af03830a9f91792389303b3746d76fc57148830184c3e0506031864076c7465737420626f6e642d74781458603b42c95589d73085882cf972c80b8c652de6e89ae4268a37a6c2d3206019bf9b706e048a7555e77f926895f6dccdb10f42efcaf0008006a0a15b8c58d704a9a0f277c66d7c6f6e8be1efb50b509c32b3b4364b2b7feb7eda106164c7ad18408a1558305a53c9e788896943587b594a2c2b930f2f9945abdf12e1c16fae8d235f74663a2f28d1b8fa442af0781f13f7de5a1c99
```

Which can be interpreted in CBOR format:

```
{
    1: 1,
    2: h'401A78337D2715DB2A69916BBEDBBB0A44336915FA1E5938B5B9CF350C340BB6',
    3: 110,
    4: 0,
    5: 2,
    6: {
        1: h'EBD6D0AFDBE2AC5968224763F1C2DBB99FEDDA53',
        2: h'C0AC961B453008E5CF521AFAB81FE303DC957DE4B385BF472108E27B054F14E2DA340F288928472B443A716EB795800CD8B885791827DEBDA0A7909C741286CEBD324DB9546BAB8AF03830A9F91792389303B3746D76FC57148830184C3E0506',
        3: 100
    },
    7: "test bond-tx",
    20: h'3B42C95589D73085882CF972C80B8C652DE6E89AE4268A37A6C2D3206019BF9B706E048A7555E77F926895F6DCCDB10F42EFCAF0008006A0A15B8C58D704A9A0F277C66D7C6F6E8BE1EFB50B509C32B3B4364B2B7FEB7EDA106164C7AD18408A',
    21: h'5A53C9E788896943587B594A2C2B930F2F9945ABDF12E1C16FAE8D235F74663A2F28D1B8FA442AF0781F13F7DE5A1C99'
}
```

Transaction id for above transaction is:

```
ID: de6aab10430fa115d59a72dbff5a046f8be9a200c1941106641a4b691a3bf0bc
```

Comments:

- Fee for bond transaction is zero
