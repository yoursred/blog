# The Evolution and Inner Workings of Blockchain Technology

Originally submitted on: 15 December 2023

## Table of Contents

* TOC
{:toc}


## 	EXECUTIVE SUMMARY

This computer science research paper provides a comprehensive exploration of blockchain technology, covering its historical evolution, intricate inner mechanisms, ethical considerations, and a forward-looking examination of its future trajectory. The target audience for this paper is readers with little experience in the matter who are interested in gaining a multi-faceted understanding of blockchain technology's past, present, and potential future evolution and use cases. The paper begins by discussing the cryptographic and distributed nature of blockchain technology and its suitability for secure record-keeping, followed by an overview of its history and evolution. The paper then reviews the seminal contributions of David Lee Chaum, Satoshi Nakamoto, Stuart Haber, W. Scott Stornetta, Dave Bayer, and Ralph Merkle, whose work laid the foundation for the remarkable advancements witnessed in blockchain technology. The paper concludes with a discussion of the ethical considerations and future trajectory of blockchain technology.


## 1	INTRODUCTION

While most known for cryptocurrency, especially Bitcoin, all the components of blockchain technology individually and collectively predate the mentioned use case. With our everyday lives becoming increasingly digitized, it’s only logical for secure record-keeping to take part. Due to their cryptographic and distributed nature along with their immutability, they make for a perfect, or at the very least, most optimal solution. The basis for modern-day blockchains was patented in 1979 by Ralph Merkle in the US and later granted to him in 1982 (Merkle, 1982). 

This research delves into a comprehensive exploration of blockchain technology, covering its historical evolution, intricate inner mechanisms, ethical considerations, and a forward-looking examination of its future trajectory. We aim to untangle the rich history of blockchain technology, offering a multi-faceted understanding of its past, present, and potential future evolution and use cases.


## 2	LITERATURE REVIEW

Research into multi-party trusted ledgers has been quite the problem to solve for computer scientists. "Computer Systems Established, Maintained, and Trusted by Mutually Suspicious Groups." by David Lee Chaum was the genesis of blockchains as we know them today. “Bitcoin: A Peer-to-Peer Electronic Cash System” by Satoshi Nakamoto was a crucial starting point for this study because of how monumental Bitcoin was, and still is, for blockchains. It provides insight into the birth of blockchains and other supporting technologies while giving us a revolutionary use case for them, one that changed the face of the internet, if not the earth, as we know it. The article “How to time-stamp a digital document” by Stuart Haber and W. Scott Stornetta reignited interest in trustable ledger systems so much so that Dave Bayer worked with the two to publish and present “Improving the Efficiency and Reliability of Digital Time-Stamping” just over a year later. The latter kept interest in the topic going by providing meaningful improvements to the design. Ralph Merkle’s 1982 patent, “Method of providing digital signatures”, was a key factor in optimizing blockchain technology without compromising the cryptographic integrity of the system.

The sources mentioned above provide valuable insights into the evolution and development of multi-party trusted ledgers, laying the foundation for the remarkable advancements witnessed in blockchain technology. Chaum's work emphasized the need for establishing trust in systems where mutual suspicion prevails, paving the way for the conceptualization of decentralized and tamper-resistant ledgers. The subsequent contributions by Haber, Stornetta, Bayer, and Merkle further fueled the momentum by addressing critical challenges in timestamping, efficiency, and digital signatures. Satoshi Nakamoto's groundbreaking paper introduced the world to the transformative potential of cryptocurrencies, demonstrating a practical application of the blockchain model that disrupted traditional financial paradigms. 

These pivotal works collectively fostered a comprehensive understanding of the principles underlying blockchain technology. They not only shed light on the historical context of its inception but also highlight the continuous efforts to enhance its efficiency and reliability. The amalgamation of these seminal ideas has propelled the evolution of blockchains beyond their initial conceptualization, shaping the landscape of decentralized and secure systems. As researchers build upon these foundations, the potential applications of blockchain technology continue to expand, influencing diverse sectors and fundamentally altering the way we approach trust and security in the digital age.


## 3	METHODOLOGY

With blockchains having become part of computer history, all the research for this paper was secondary. The starting point for this study was Nakamoto’s original Bitcoin paper as it had been the most prominent use of blockchains up to that point, if not ever. The terminology and sources used by Satoshi Nakamoto in the paper were used to trace the concept of blockchains, and any precursors, to provide a complete timeline, as the term itself was not used in Nakamoto’s original paper. It was, however, became more popular later in 2016 (Johnsen, 2020).

This backtracking approach does have its problems, however. For one, there is always the possibility of running into a dead-end due to poor referencing and record keeping. That is why multiple sources were followed to make sure of data accuracy, especially older sources. Additionally, the evolving nature of computer science and the multi-ended development of blockchain technology makes it necessary to branch off of Nakamoto’s paper.


## 4	RESULT

A blockchain is a chain of data structures in which each constituent element contains the hash of the one before it, linking the two. Alongside the previous hash is data encoding a transaction with its timestamp. The transaction could be a legal document (contract, lawsuit, decree…) being checked into the record or it could be a monetary transaction. Cryptographic hashing algorithms take in data of any length and output a fixed-size value that is unique to the input. Any change in the input gives an entirely different value as output. Due to their nature, if any block has an invalid hash, all blocks that come after it are considered invalid. This allows anyone to verify the chain's integrity using a computationally inexpensive process. (The Economist, 2015) Multiple transactions can be encoded in one block while still guaranteeing integrity with the use of a Merkle tree, consolidating multiple transactions and keeping the time complexity low. (Nakamoto, 2008)

The aforementioned Merkle tree, also known as a hash tree, is not dissimilar to a blockchain itself. Transaction and timestamp data for every transaction is hashed then every two hashes are hashed together to make the parent node. The process is repeated to build a binary tree from the roots up. A branch of the tree can then be checked without the need for the whole tree by building the branch to the topmost hash and comparing it with the actual one (Merkle, 1982). This also means there is no need for the data blocks during the integrity check, optimizing things even further.

The patent mentioned in the introduction, while not quite a blockchain in today’s sense, was crucial for the development that ensued. Later that same year, David Lee Chaum published a paper outlining his vault model comprising all elements of a blockchain (Chaum, 1982), with one of them being different from the equivalent found in Bitcoin. Bitcoin uses a “proof-of-work” mechanism where a peer proves the expenditure of computational power to the network while requiring minimal computer power to verify (Nakamoto, 2008). 

Blockchains were being investigated by a different group of people, Stuart Haber and W. Scott Stornetta, with their first endeavor being an early system where time-stamped documents could be kept in a record in a secure and tamper-proof manner (Haber and Stornetta, 1991). Dave Bayer would later join them in 1992 to incorporate Merkel trees in the design, allowing multiple documents to be kept in a single block (Bayer, Haber, and Sotrnetta, 1992). The three of them would form the company Surety, specializing in secure, public document keeping. They had been publishing their hashes as early as 1995 in the New York Times weekly as an advertisement (Oberhaus, 2018).

Satoshi Nakamoto published his Bitcoin paper on October 31st, 2008, in which he outlines a “peer-to-peer electronic cash system”, the first of its kind. His creation would be implemented a year later, revolutionizing the electronic payment field and changing the internet as we know it. It also kept the light on blockchain technology ever since, inspiring countless similar digital currencies both successful and not. Popular ones include Ethereum and Litecoin, which were launched in 2015 and 2011, respectively.

With these systems being trustless, decentralized, and peer-to-peer, the need for what’s known as a consensus mechanism arises in the case of digital currencies. Bitcoin uses a proof-of-work consensus mechanism alongside a difficulty adjustment algorithm. A peer on the network has to solve a computationally hard cryptographic challenge to add blocks to the chain while keeping it easy for others to verify the work done. The computational effort deters subversion of the network by bad actors. (Nakamoto, 2008)

## 5	DISCUSSION

With any new technology comes ethical concerns, and they are justified in the case of cryptocurrency. Due to their trustless and anonymous nature, they are practically untraceable. Everything from Child Sexual Abuse Material and sex trafficking to illegal drugs and firearms can all be funded under complete anonymity using blockchain-based digital currencies. The issues at hand, however, are inevitable if complete anonymity is to be achieved. It’s why the dark web, for example, is riddled with the crimes mentioned above. It’s also why the two go hand-in-hand. Financial crimes are also a given when dealing with any form of currency, especially ones with such an extreme absence of regulations. 

Due to the extreme levels of anonymity afforded by cryptocurrency, data collection is not a concern. No one has ownership of it, and it’s all publicly accessible. As contradictory as that might seem at first, cryptocurrency blockchains do not store any personally identifying information on them, the only identifier is randomly generated and there is no central store linking it to an individual or group (Nakamoto, 2008). The dark web, once again, affords similar levels of anonymity to its users. It is an unfortunate side effect of such levels of anonymity, a double-edged sword if you will.

Another concern with cryptocurrencies is an environmental one. Bitcoin and many others use a proof-of-work consensus mechanism, it’s computationally expensive and therefore consumes a substantial amount of energy. Due to the financial incentive that comes with mining crypto, a lot of people jumped on the mining train and most of them are expectedly going to come from less economically advanced countries. These countries are less likely to have clean energy as a big concern, leading to extraneous consumption for the sole purpose of financial gain. It is estimated that Bitcoin mining has resulted in 0.4% of global energy consumption as of 2022 (Messina, 2023). It also results in a surplus of electronic waste as the hardware used has its useful lifespan run through concurrently (de Vries and Stoll, 2021).

Regarding the trajectory that lies ahead for blockchain technology, it’s either enhancements or alternate uses. Expectable improvements in cryptographic hashing algorithms brought on by parallel improvements in computer processor technology, with complexity and speed being the prominent ones, power efficiency is also present and important. Computer hardware has been evolving at a fairly consistent and predictable pace over the last few years, and it is expected to keep up that pace for a short while (Moore, 1995). Once we hit the physical limits of transistor scale getting close to the scale of the electrons and atoms being worked with, quantum computers, which are considered a possible future alternative to transistor-transistor-logic, alternatives will have to be used. However they might be used in the space of cryptography is not entirely clear as they break traditional encryption as we know it. They might possibly remove the need for blockchains, only time can tell. Such a combination has much untapped potential, but is unfortunately beyond the scope of this study. 

Other future considerations are new use cases, either being adapted to fit blockchains or the other way around. Ironically, one potential future transition is that of traditional, government-backed currency. The blockchain needed for such a feat wouldn’t necessarily be as public or open as a typical cryptocurrency, it might even be controlled entirely by whatever existing monetary authority wishes to eventually make the switch. The Swedish Central Bank, or Riksbank, has been investigating a comparable transition with promising results (Riksbank, 2017). The immutable record-keeping aspect of blockchains could be deployed anywhere documents would need to be kept in such a manner, inventory management and patient records are a few examples.

## 6	CONCLUSION

In conclusion, exploring the origins of blockchain by following the Bitcoin paper gave us invaluable insight and understanding of decentralized digital ledgers. By tracking down the terminology and sources employed by Satoshi Nakamoto, this research primarily focused on Bitcoin and the events and developments leading to its inception. Other cryptocurrencies did not bring much in terms of innovation to the space of blockchain technology due to them making minimal changes to the Bitcoin model, thus the focus. This focused approach allowed for a comprehensive analysis of the birth and evolution of blockchain technology, while giving insight on the most prominent use of it. Ethical concerns were acknowledged and addressed, with the funding of crime being the most critical as well as environmental ones. The data privacy and ownership aspect of the technology, which plays a part in the association with crime, was also covered.

## 7	REFERENCES

- Bayer, D., Haber, S. and Stornetta, W.S. (1993). ‘Improving the Efficiency and Reliability of Digital Time-Stamping.’ _Sequences II_, pp.329–334. doi:[https://doi.org/10.1007/978-1-4613-9323-8_24](https://doi.org/10.1007/978-1-4613-9323-8_24).

- Chaum D.L. (1982). ‘Computer Systems Established, Maintained and Trusted by Mutually Suspicious Groups.’ California: Electronics Research Laboratory, University of California.

- de Vries, A., Gallersdörfer, U., Klaaßen, L. and Stoll, C. (2022). ‘Revisiting Bitcoin’s carbon footprint.’ _Joule_, 6(3). doi:[https://doi.org/10.1016/j.joule.2022.02.005](https://doi.org/10.1016/j.joule.2022.02.005).

- The Economist. (2015). ‘The great chain of being sure about things.’ [online] Available at: [https://www.economist.com/news/briefing/21677228-technology-behind-bitcoin-lets-people-who-do-not-know-or-trust-each-other-build-dependable](https://www.economist.com/news/briefing/21677228-technology-behind-bitcoin-lets-people-who-do-not-know-or-trust-each-other-build-dependable).

- Haber, S. and Stornetta, W. Scott. (1991). ‘How to time-stamp a Digital Document. Journal of Cryptology’, _J. Cryptology 3(2)_. doi:[https://doi.org/10.1007/bf00196791](https://doi.org/10.1007/bf00196791).

- Johnsen, M. (2020). ‘Blockchain in Digital Marketing.’ Maria Johnsen.

- Merkle, R. (1982). ‘Method of Providing Digital Signatures.’

- Messina, I. (2023). ‘Bitcoin electricity consumption: an improved assessment - News & insight.’ [online] Cambridge Judge Business School. Available at: [https://www.jbs.cam.ac.uk/2023/bitcoin-electricity-consumption/ ](https://www.jbs.cam.ac.uk/2023/bitcoin-electricity-consumption/)[Accessed 14 Dec. 2023].

- Moore, G.E. (1998). ‘Cramming More Components onto Integrated Circuits.’ Proceedings of the IEEE, 86(1), pp.82–85. doi:[https://doi.org/10.1109/jproc.1998.658762](https://doi.org/10.1109/jproc.1998.658762).

- Nakamoto, S. (2008). ‘Bitcoin: a Peer-to-Peer Electronic Cash System.’ [online] bitcoin.org. Available at: [https://bitcoin.org/bitcoin.pdf](https://bitcoin.org/bitcoin.pdf).

- Oberhaus, D. (2018). ‘The World’s Oldest Blockchain Has Been Hiding in the New York Times Since 1995.’ [online] vice.com. - Available at: [https://www.vice.com/en/article/j5nzx4/what-was-the-first-blockchain](https://www.vice.com/en/article/j5nzx4/what-was-the-first-blockchain).

- ‘The Riksbank’s e-krona project.’ (2017). [online] Riksbank. Available at: [https://www.riksbank.se/globalassets/media/rapporter/e-krona/2017/rapport_ekrona_uppdaterad_170920_eng.pdf](https://www.riksbank.se/globalassets/media/rapporter/e-krona/2017/rapport_ekrona_uppdaterad_170920_eng.pdf) [Accessed 14 Dec. 2023].
