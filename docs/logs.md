```
例子1: 以下是卖蛋的参数
https://www.bscscan.com/tx/0x0b78a78ed81b16152e77e8fd459c92bc411327908277b39c78fc27b058d080f0#eventlog
发送交易DATA
0x467f963d sell方法
000000000000000000000000d40c03b8680d4b6a4d78fc3c6f6a28c854e94a79 nftAddress（蛋）
0000000000000000000000000000000000000000000000000000000000000000 tokenId
0000000000000000000000000000000000000000000000000000000000000002 count
00000000000000000000000012bb890508c125661e03b09ec06e404bc9289040 paymentToken(RACA)
00000000000000000000000000000000000000000001707596c91ce527800000 startingPrice(单价*数量)
0000000000000000000000000000000000000000000000000000000000000000 startDate
0000000000000000000000000000000000000000000000000000000000000000 endDate

0x467f963d
00000000000000000000000051353799f8550c9010a8b0cbfe6c02ca96e026e2
0000000000000000000000000000000000000000000000000000000000000000
000000000000000000000000000000000000000000000000000000000000043c
00000000000000000000000012bb890508c125661e03b09ec06e404bc9289040
00000000000000000000000000000000000000000008f77593d6328ac7000000
0000000000000000000000000000000000000000000000000000000000000000
0000000000000000000000000000000000000000000000000000000000000000

cancelAuction
0x96b5a755
be7b13a5a98b5b89849f42222b7fc3adb3a261176d05e640e497ddaf9bf9030b

对应的Logs
topic 0x6656db943f28baede9b164738dc5fa235b9da60d5c20a38b0eb0230c 21196254
000000000000000000000000c6090ee2184e4d0d425987432aaeb17fb39b4192 sellAddress
7770285f13d31daf82ae18cd75429100ce2b399dca3430c2e5699ed064e2be98 auctionId
000000000000000000000000d40c03b8680d4b6a4d78fc3c6f6a28c854e94a79 nftAddress(蛋的合约)

Data:
0000000000000000000000000000000000000000000000000000000000000000 tokenId
0000000000000000000000000000000000000000000000000000000000000002 count
00000000000000000000000012bb890508c125661e03b09ec06e404bc9289040 paymentToken(RACA)
00000000000000000000000000000000000000000001707596c91ce527800000 startingPrice
0000000000000000000000000000000000000000000000000000000000000000
0000000000000000000000000000000000000000000000000000000061a9f218 startDate
000000000000000000000000000000000000000000000000ffffffffffffffff endDate
00000000000000000000000000000000000000000000000000000000001f6f2a n/a

例子2：以下是卖元兽的参数
https://www.bscscan.com/tx/0x159da7dcee7e5d87d35ebc372cdb475bb4d8c2b7a843e5368836cacd82e12170
发送交易DATA
0x467f963d
000000000000000000000000f24bf668aa087990f1d40ababf841456e771913c nftAddress(元兽)
0000000000000000000000000000000000000000000000000000000000078e24 tokenId
0000000000000000000000000000000000000000000000000000000000000001 count
00000000000000000000000012bb890508c125661e03b09ec06e404bc9289040 paymentToken(RACA)
00000000000000000000000000000000000000000000a6953fd2d8e701680000 startingPrice
0000000000000000000000000000000000000000000000000000000000000000 startDate
0000000000000000000000000000000000000000000000000000000000000000 endDate

对应的Logs: 
topic 0x6656db943f28baede9b164738dc5fa235b9da60d5c20a38b0eb0230c21196254
0000000000000000000000000000000000000000000000000000000000078e24 tokenId
0000000000000000000000000000000000000000000000000000000000000001 count
00000000000000000000000012bb890508c125661e03b09ec06e404bc9289040 paymentToken(RACA)
00000000000000000000000000000000000000000000a6953fd2d8e701680000 startingPrice
0000000000000000000000000000000000000000000000000000000000000000
0000000000000000000000000000000000000000000000000000000061a8d2de startDate
000000000000000000000000000000000000000000000000ffffffffffffffff endDate
00000000000000000000000000000000000000000000000000000000001de4d3 n/a

================================================================
购买：executeAuction
发送交易DATA
0x25d377f7
5040d0c612d7ccb8c7617508c08f46d3b89230d7491b7b38e79b3baca643510a auctionId
00000000000000000000000000000000000000000000e185c403ec2b27a00000 amount(RACA)

0x25d377f7
6e8907be43e18a8fc497c6e6175b0f586708229fcd62b1d6b2981fe14e6a89ec
000000000000000000000000000000000000000000000a0efaebbe36ceb00000

0x25d377f7
80a8268dfb1df008c48f8c1f183d6dd3c4944bd75525c788496c5bae780a8745
0000000000000000000000000000000000000000000002c51176eb309d600000

对应的Log
0x1e58c00385b2026e41e3dcdd07c0117f1e182f8fd553676950d681ea12185b34 topic
0x000000000000000000000000fee560fd3e4b6a096bfc465304209598c70829de buyerAddress
0x5040d0c612d7ccb8c7617508c08f46d3b89230d7491b7b38e79b3baca643510a auctionId
0x000000000000000000000000f24bf668aa087990f1d40ababf841456e771913c nftAddress

Data
000000000000000000000000000000000000000000000000000000000006031d tokenId
00000000000000000000000000000000000000000000e185c403ec2b27a00000 amount(RACA)
0000000000000000000000000000000000000000000000000000000061a8bbd9 buyTimestamp

================================================================
1- 自动购买解决方案
- 侦听卖单log, topic: 0x6656db943f28baede9b164738dc5fa235b9da60d5c20a38b0eb0230c21196254
- 获取卖单信息
- 与自己设定的条件比较
- 符合条件的，下单

2- 自动卖出解决方案

================================================================
授权DATA
发起账号账号：0x8844A26344C97134B0D5bd8B8493C5Ab10799843
买蛋合约：
0x095ea7b3
000000000000000000000000e97fdca0a3fc76b3046ae496c1502c9d8dfef6fc
000000000000000000000000000000000000000000000fab8c4c3b325a400000


买药水
0x095ea7b3
000000000000000000000000e97fdca0a3fc76b3046ae496c1502c9d8dfef6fc
0000000000000000000000000000000000000000000020c58e70ee60dd200000
================================================================

```