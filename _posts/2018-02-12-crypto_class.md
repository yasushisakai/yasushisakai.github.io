---
title: crypto class notes
layout:post
---
## 2/12

1. cant intersept
2. spend money w/o authorization
3. double spend
4. equivocate? 

cant undo = tamper proof (tamper with history

**distributed consensus** (method)
  Problem of multiple computers agreeing on a value
  distributed database
  ordered
  ex Paxos, Viewtamped Replication
  tollerate computer crashes
  1982 **byzantine fault tolerant** distributed concensus 1/3?
  -> relatively old idea?
  these protocols needs to know identity -> attacker can create a lot of identity -> **sybil attack**
  make identities costly
  totall async + w/o randomcoins

---

How to prevent sybil attacks?
いたちごっこになりやすい

pset 1
many attemps 3min 2billion

memoryless

"proof" of work

31 bits
hash cash (1997")

echo "yasushi n" >> sha256sum
00000000sdfkjsahfjsfhsf

hash (m, n)

m = m, hash

blockchain 
block contains 


----hash: 00db--
prev: 00ce
msg: hi
nonce: 5ffc

connects to
---hash: 002c---
prev: 00db
msg: oh hi
nonce: 8c90


you cant change the message, because the chain will be broken
unless chain forks

the fork with most work (more chain) wins

very hard to rewrite history even if everyone agrees to change.


## 2/14

### Signature

### Lamport
  + hash
  - one time use
  - kind of big ~8k

  make two keys inside public key 


## 2/28
what is the message
who amount payee auth(sign)

what is signed?
sign everthing except the signature, which is hashed

### accountbased model
- etheruim uses this 
straight forward way.
- replay attack

### unspent transaction outputs

## 2/21
syncronization

merkle trees

## 4/3

### conditional payment
### oracles
  ### 第三者が必要

### k-collision

can the oracles can be like 1000? -> voting?

