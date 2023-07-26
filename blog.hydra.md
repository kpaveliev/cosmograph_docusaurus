# Title: Tracing the Footprints of Bitcoin Transactions: Unveiling Surprising Connections

Remember that study that revealed traces of cocaine on 90% of US banknotes? Curiosity led us to wonder: what about bitcoin transactions? Can we uncover intriguing connections through the blockchain? A few months ago, we conducted an experiment to find out. We engaged in buying and selling on a peer-to-peer exchange and drew a network graph to reveal the paths our coins traversed. The objective was to determine how many steps separated our transactions from the largest dark markets, other peer-to-peer networks, or accounts with significant turnovers. The results were eye-opening.

![01 All graph](https://github.com/kpaveliev/cosmograph_docusaurus/assets/6072307/5adab105-0543-484d-b062-ec5dcf25855b)

### The Experiment

We selected randomly a p2p exchange and executed two transactions: a purchase and a subsequent sale. Upon completion, we gathered comprehensive data encompassing our two transactions and the transactions associated with the addresses involved. Utilizing this data, we built a network graph seen above to visually chart the intricate connections between these addresses, precisely mapping their interrelationships based on the sequence of transactions.

Our graph vividly represented the blockchain addresses related to the address that sold us bitcoin and the address that bought it back from us. Each node in the graph corresponded to a unique BTC address, while edges represented one or several transactions between these addresses. The visual portrayal provided a striking insight into the intricate flow of bitcoin transactions.

![01 All graph (3)](https://github.com/kpaveliev/cosmograph_docusaurus/assets/6072307/3aef57e6-243b-47f1-8f5f-0250fdaaa7a0)
*Pic 1: Graph Overview with the structures identified

As we scrutinized the graph, we were taken aback by the revealing connections. The address that bought bitcoin from us turned out to be directly linked to the famous [Hydra Market] (https://en.wikipedia.org/wiki/Hydra_Market), one of the largest dark markets in the world. The discovery added a layer of complexity and raised questions about the interplay between cryptocurrencies and illicit activities.

![03 Buying address (1)](https://github.com/kpaveliev/cosmograph_docusaurus/assets/6072307/451184dd-fe2f-4e8a-84af-462d828e1d37)
*Pic 2: Hydra

Beyond the Hydra Market link, we discovered other intriguing structures just a few steps away. These connections involved prominent entities such as Binance, CoinDCX, and various peer-to-peer exchanges. The interconnectivity within the bitcoin network offered a glimpse into the vast web of transactions occurring within the cryptocurrency space.

### Conclusion

Our experiment opened a window into the fascinating realm of bitcoin transactions. The network graph revealed unexpected connections, including a direct link to Hydra Market.

Acknowledgements: 
• Transaction data was obtained using the API of [http://blockchain.com](https://t.co/GySxU889R5)
• Address identification by [http://oxt.me](https://t.co/PrnYJU3JHs)
• Graph visualization by [http://cosmograph.app](https://t.co/yBSx36PTQX)

PS. You can explore the interactive version of the graph [here](https://cosmograph.app/run/?data=https://cosmograph.app/data/3PS8N_dataset.csv) (note: it may take up to 1 minutes to fully load and it’s better to be opened with Safari).
