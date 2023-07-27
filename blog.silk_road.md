# Unraveling Silk Road: A Graph Visualization Journey into Cryptocurrency's Most Notorious Marketplace

Blockchain, inherently free of copyright, offers some of the most interesting and rich graph structures. Our focus shifted to one of the most iconic cases in blockchain history: Silk Road.

> [Wikipedia](https://en.wikipedia.org/wiki/Silk_Road_(marketplace)):
> 
> *Silk Road as an online black market and the first modern darknet market. As part of the dark web, it was operated as a Tor hidden service, such that online users were able to browse it anonymously
> and securely without potential traffic monitoring.*
> 
> *Buyers and sellers conducted all transactions with bitcoins (BTC). Silk Road held buyers’ bitcoins in escrow until the order had been received and a hedging mechanism allowed sellers to opt
> for the value of bitcoins held in escrow to be fixed to their value in US$ at the time of the sale to mitigate against Bitcoin’s volatility.*
> 
> *The website was launched in February 2011. In October 2013, the Federal Bureau of Investigation (FBI) shut down the website and arrested Ross Ulbricht who was alleged to be the founder and owner of Silk Road.*
> 
> *The FBI initially seized 26,000 bitcoins from accounts on Silk Road. In October 2013, the FBI reported that it had seized 144,000 bitcoins.
> On 27 June 2014, the U.S. Marshals Service sold 29,657 bitcoins in 10 blocks in an online auction. Tim Draper bought the bitcoins at the auction with an estimated worth of $17 million.
> In November 2020, the United States government seized more than $1 billion worth of bitcoin connected to Silk Road.*

To delve into the underlying structure of Silk Road, we identified specific bitcoin addresses connected to the platform using OXT, a blockchain explorer with the ability 
to identify addresses likely controlled by the same entity. Armed with this data, we collected transactions associated with these addresses using blockchain.info API and constructed network graphs for deeper insights. 
Utilizing Cosmograph, we meticulously analyzed one such graph associated with the address 184R7cFGqAZaZBuj2rsuExDAJ6iCEs3hXi.

In the graph, we expected to observe structures linked to exchanges (buyers acquiring coins for purchases), addresses related to buyers' Silk Road accounts, and patterns arising from vendors' cashouts. 
The key elements of the Silk Road payment system are best described by an exhibit displayed in Ross Ulbricht’s trial (please see Pic. 1).

![image](https://github.com/kpaveliev/cosmograph_docusaurus/assets/6072307/753e7217-9c12-413a-8ecf-b626d84eadb6)
*Pic. 1 Exhibit from Ross Ulbricht’s trial showing Silk Road payment system (source: [Wikipedia](https://en.wikipedia.org/wiki/Silk_Road_(marketplace)#/media/File:Silk_road_payment.jpg))*

### Overview of what we got

In Pic. 2 you can see a graph built from all the transactions to or from the address **184R7c*** and all connected addresses up to the 4th depth level. 
Addresses are represented by nodes and BTC transfers between these addresses by edges. The 4th depth level means that on the graph you will see all the addresses our initial address transacted with, 
all the addresses the previous step addresses transacted with and so on two more times.

![01 Graph overview](https://github.com/kpaveliev/cosmograph_docusaurus/assets/6072307/7b0023fa-936c-411e-9cb3-a58be7aa677f)
*Pic. 2 Graph for **184R7c** address with depth level 4 (source: Cosmograph)
For the interactive version of the graph **[click here](https://cosmograph.app/run/?data=https%3A%2F%2Fcosmograph.app%2Fdata%2F184R7cFG-4lv.csv).***

We got some interesting structures on the graph so let’s try and identify their nature. We would you use a basic understanding of the bitcoin blockchain and OXT.
Actually, we got what we expected but also some unexpected structures (see Pic. 3): (1) lots of Silk Road addresses; (2) FBI seizure (2013); (3) coin mixers (possibly); 
(4) exchanges/wallets used to transfer bitcoins (BitPay, BTC-e/BitPay, Bitstamp); (5) dark markets (Sheep Marketplace).

![03_graph_highlights (2)](https://github.com/kpaveliev/cosmograph_docusaurus/assets/6072307/c42c9dec-8555-47b3-8e24-bc6925565db4)
*Pic. 3 Graph for **184R7** address with structures highlights (source: Cosmograph)*

### Central structure

At the graph's core, we observed address 1BRz3S*, which exhibited 2479 connections and processed 7,187 BTC. While unable to pinpoint the exact entity, 
it likely represented a cryptocurrency exchange integrated into Silk Road's payment system. 
Transactions involving this address consistently exhibited specific patterns, indicating its role in facilitating transactions between exchanges and buyers.

(1) A typical incoming transaction would consist of 1 input and 2 outputs (with the larger output going to **1BRz3S***). The input and the larger output would belong to an exchange, the smaller output would belong to a buyer.

![image (2)](https://github.com/kpaveliev/cosmograph_docusaurus/assets/6072307/525ec077-3f66-4b43-9a8e-aaf136610874)
*Ex. 1 A typical incoming transaction (source [blockchain.info](http://blockchain.info/))*

(2) A typical outgoing transaction would consist of 1 or several inputs and 2 outputs. The larger output would belong to the same exchange and the smaller output would belong to a buyer.

![image (1)](https://github.com/kpaveliev/cosmograph_docusaurus/assets/6072307/c3ace32d-e5df-4086-9a0a-61a5762a2578)
*Ex. 2 A typical outgoing transaction (source [blockchain.info](http://blockchain.info/))*

(3) If you trace the transactions backward or forward you will see the same pattern (1 input with 2 outputs, one is smaller, the other is larger).

![05 2_central_structure (1)](https://github.com/kpaveliev/cosmograph_docusaurus/assets/6072307/b276958e-7154-4e1a-a6dd-87e7df1719da)
*Pic. 4 Schematic view of typical transactions involving the central structure (source: Cosmograph)*

Other observations making us to believe that we see the actual Silk Road payment system:
1. Many of the addresses around central structure relate to Silk Road, which could be sellers cashing out or buyers buying BTC to later purchase something on Silk Road.
2. One of the outputs belongs to Bitstamp, which could be someone buying BTC for cash and transferring them to exchange.
3. Some of the corresponding addresses are quite large with single transactions of over 40 000 BTC, we weren’t able to identify their nature with sufficient accuracy.

### FBI seizure

We believe that what we see in Pic. 5 is the first major legally authorized seizure. 
It happened just after Ross Ulbricht’s arrest in October 2013 and involved more than 29 000 BTC of Silk Road user funds (>1,3 bln USD as of today). 
**1F1tAa*** — the address which is believed to be tied to the FBI and where Silk Road funds were transferred to.

![06_fbi_seizure (1)](https://github.com/kpaveliev/cosmograph_docusaurus/assets/6072307/5129ce61-d4f3-4a7a-bf59-f9bf0a0145e8)
*Pic 5. Close-up view for structures around address **1F1tAa*** which is believed to be tied to the FBI (source: Cosmograph)*

### Conclusion

Graph visualization enabled us to uncover higher-level structures and relationships, providing crucial insights for formulating hypotheses and guiding further investigations. This approach is applicable beyond Silk Road, empowering analysis of various transaction types across the blockchain landscape. As we continue our explorations, Cosmograph remains at the forefront of visual analytics, unlocking valuable insights from millions of transactions in real-time.
