

```python
from nltk.corpus import reuters
import pandas as pd
```


```python
File_list = reuters.fileids()
```


```python
category = []
Raw_text = []
Type = []

for FileName in File_list:
    if len(reuters.categories(FileName)) == 1:
        if FileName.startswith("train"):
            category.append(reuters.categories(FileName))
            Raw_text.append(reuters.raw(FileName))
            Type.append('train')
        else:
            category.append(reuters.categories(FileName))
            Raw_text.append(reuters.raw(FileName))
            Type.append('test')
```


```python
Categorydf = pd.DataFrame(category, Raw_text)
```


```python
Categorydf['Type'] = Type
```


```python
Categorydf['index'] = Categorydf.index
```


```python
Categorydf.shape
```




    (9160, 3)




```python
Categorydf.head()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>Type</th>
      <th>index</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ASIAN EXPORTERS FEAR DAMAGE FROM U.S.-JAPAN RIFT\n  Mounting trade friction between the\n  U.S. And Japan has raised fears among many of Asia's exporting\n  nations that the row could inflict far-reaching economic\n  damage, businessmen and officials said.\n      They told Reuter correspondents in Asian capitals a U.S.\n  Move against Japan might boost protectionist sentiment in the\n  U.S. And lead to curbs on American imports of their products.\n      But some exporters said that while the conflict would hurt\n  them in the long-run, in the short-term Tokyo's loss might be\n  their gain.\n      The U.S. Has said it will impose 300 mln dlrs of tariffs on\n  imports of Japanese electronics goods on April 17, in\n  retaliation for Japan's alleged failure to stick to a pact not\n  to sell semiconductors on world markets at below cost.\n      Unofficial Japanese estimates put the impact of the tariffs\n  at 10 billion dlrs and spokesmen for major electronics firms\n  said they would virtually halt exports of products hit by the\n  new taxes.\n      "We wouldn't be able to do business," said a spokesman for\n  leading Japanese electronics firm Matsushita Electric\n  Industrial Co Ltd &amp;lt;MC.T&gt;.\n      "If the tariffs remain in place for any length of time\n  beyond a few months it will mean the complete erosion of\n  exports (of goods subject to tariffs) to the U.S.," said Tom\n  Murtha, a stock analyst at the Tokyo office of broker &amp;lt;James\n  Capel and Co&gt;.\n      In Taiwan, businessmen and officials are also worried.\n      "We are aware of the seriousness of the U.S. Threat against\n  Japan because it serves as a warning to us," said a senior\n  Taiwanese trade official who asked not to be named.\n      Taiwan had a trade trade surplus of 15.6 billion dlrs last\n  year, 95 pct of it with the U.S.\n      The surplus helped swell Taiwan's foreign exchange reserves\n  to 53 billion dlrs, among the world's largest.\n      "We must quickly open our markets, remove trade barriers and\n  cut import tariffs to allow imports of U.S. Products, if we\n  want to defuse problems from possible U.S. Retaliation," said\n  Paul Sheen, chairman of textile exporters &amp;lt;Taiwan Safe Group&gt;.\n      A senior official of South Korea's trade promotion\n  association said the trade dispute between the U.S. And Japan\n  might also lead to pressure on South Korea, whose chief exports\n  are similar to those of Japan.\n      Last year South Korea had a trade surplus of 7.1 billion\n  dlrs with the U.S., Up from 4.9 billion dlrs in 1985.\n      In Malaysia, trade officers and businessmen said tough\n  curbs against Japan might allow hard-hit producers of\n  semiconductors in third countries to expand their sales to the\n  U.S.\n      In Hong Kong, where newspapers have alleged Japan has been\n  selling below-cost semiconductors, some electronics\n  manufacturers share that view. But other businessmen said such\n  a short-term commercial advantage would be outweighed by\n  further U.S. Pressure to block imports.\n      "That is a very short-term view," said Lawrence Mills,\n  director-general of the Federation of Hong Kong Industry.\n      "If the whole purpose is to prevent imports, one day it will\n  be extended to other sources. Much more serious for Hong Kong\n  is the disadvantage of action restraining trade," he said.\n      The U.S. Last year was Hong Kong's biggest export market,\n  accounting for over 30 pct of domestically produced exports.\n      The Australian government is awaiting the outcome of trade\n  talks between the U.S. And Japan with interest and concern,\n  Industry Minister John Button said in Canberra last Friday.\n      "This kind of deterioration in trade relations between two\n  countries which are major trading partners of ours is a very\n  serious matter," Button said.\n      He said Australia's concerns centred on coal and beef,\n  Australia's two largest exports to Japan and also significant\n  U.S. Exports to that country.\n      Meanwhile U.S.-Japanese diplomatic manoeuvres to solve the\n  trade stand-off continue.\n      Japan's ruling Liberal Democratic Party yesterday outlined\n  a package of economic measures to boost the Japanese economy.\n      The measures proposed include a large supplementary budget\n  and record public works spending in the first half of the\n  financial year.\n      They also call for stepped-up spending as an emergency\n  measure to stimulate the economy despite Prime Minister\n  Yasuhiro Nakasone's avowed fiscal reform program.\n      Deputy U.S. Trade Representative Michael Smith and Makoto\n  Kuroda, Japan's deputy minister of International Trade and\n  Industry (MITI), are due to meet in Washington this week in an\n  effort to end the dispute.\n  \n\n</th>
      <td>trade</td>
      <td>test</td>
      <td>ASIAN EXPORTERS FEAR DAMAGE FROM U.S.-JAPAN RI...</td>
    </tr>
    <tr>
      <th>CHINA DAILY SAYS VERMIN EAT 7-12 PCT GRAIN STOCKS\n  A survey of 19 provinces and seven cities\n  showed vermin consume between seven and 12 pct of China's grain\n  stocks, the China Daily said.\n      It also said that each year 1.575 mln tonnes, or 25 pct, of\n  China's fruit output are left to rot, and 2.1 mln tonnes, or up\n  to 30 pct, of its vegetables. The paper blamed the waste on\n  inadequate storage and bad preservation methods.\n      It said the government had launched a national programme to\n  reduce waste, calling for improved technology in storage and\n  preservation, and greater production of additives. The paper\n  gave no further details.\n  \n\n</th>
      <td>grain</td>
      <td>test</td>
      <td>CHINA DAILY SAYS VERMIN EAT 7-12 PCT GRAIN STO...</td>
    </tr>
    <tr>
      <th>AUSTRALIAN FOREIGN SHIP BAN ENDS BUT NSW PORTS HIT\n  Tug crews in New South Wales (NSW),\n  Victoria and Western Australia yesterday lifted their ban on\n  foreign-flag ships carrying containers but NSW ports are still\n  being disrupted by a separate dispute, shipping sources said.\n      The ban, imposed a week ago over a pay claim, had prevented\n  the movement in or out of port of nearly 20 vessels, they said.\n      The pay dispute went before a hearing of the Arbitration\n  Commission today.\n      Meanwhile, disruption began today to cargo handling in the\n  ports of Sydney, Newcastle and Port Kembla, they said.\n      The industrial action at the NSW ports is part of the week\n  of action called by the NSW Trades and Labour Council to\n  protest changes to the state's workers' compensation laws.\n      The shipping sources said the various port unions appear to\n  be taking it in turn to work for a short time at the start of\n  each shift and then to walk off.\n      Cargo handling in the ports has been disrupted, with\n  container movements most affected, but has not stopped\n  altogether, they said.\n      They said they could not say how long the disruption will\n  go on and what effect it will have on shipping movements.\n  \n\n</th>
      <td>ship</td>
      <td>test</td>
      <td>AUSTRALIAN FOREIGN SHIP BAN ENDS BUT NSW PORTS...</td>
    </tr>
    <tr>
      <th>WESTERN MINING TO OPEN NEW GOLD MINE IN AUSTRALIA\n  Western Mining Corp Holdings Ltd\n  &amp;lt;WMNG.S&gt; (WMC) said it will establish a new joint venture gold\n  mine in the Northern Territory at a cost of about 21 mln dlrs.\n      The mine, to be known as the Goodall project, will be owned\n  60 pct by WMC and 40 pct by a local W.R. Grace and Co &amp;lt;GRA&gt;\n  unit. It is located 30 kms east of the Adelaide River at Mt.\n  Bundey, WMC said in a statement\n      It said the open-pit mine, with a conventional leach\n  treatment plant, is expected to produce about 50,000 ounces of\n  gold in its first year of production from mid-1988. Annual ore\n  capacity will be about 750,000 tonnes.\n  \n\n</th>
      <td>gold</td>
      <td>test</td>
      <td>WESTERN MINING TO OPEN NEW GOLD MINE IN AUSTRA...</td>
    </tr>
    <tr>
      <th>SUMITOMO BANK AIMS AT QUICK RECOVERY FROM MERGER\n  Sumitomo Bank Ltd &amp;lt;SUMI.T&gt; is certain to\n  lose its status as Japan's most profitable bank as a result of\n  its merger with the Heiwa Sogo Bank, financial analysts said.\n      Osaka-based Sumitomo, with desposits of around 23.9\n  trillion yen, merged with Heiwa Sogo, a small, struggling bank\n  with an estimated 1.29 billion dlrs in unrecoverable loans, in\n  October.\n      But despite the link-up, Sumitomo President Koh Komatsu\n  told Reuters he is confident his bank can quickly regain its\n  position.\n      "We'll be back in position in first place within three\n  years," Komatsu said in an interview.\n      He said that while the merger will initially reduce\n  Sumitomo's profitability and efficiency, it will vastly expand\n  Sumitomo's branch network in the Tokyo metropolitan area where\n  it has been relatively weak.\n      But financial analysts are divided on whether and how\n  quickly the gamble will pay off.\n      Some said Sumitomo may have paid too much for Heiwa Sogo in\n  view of the smaller bank's large debts. Others argue the merger\n  was more cost effective than creating a comparable branch\n  network from scratch.\n      The analysts agreed the bank was aggressive. It has\n  expanded overseas, entered the lucrative securities business\n  and geared up for domestic competition, but they questioned the\n  wisdom of some of those moves.\n      "They've made bold moves to put everything in place. Now\n  it's largely out of their hands," said Kleinwort Benson Ltd\n  financial analyst Simon Smithson.\n      Among Sumitomo's problems are limits placed on its move to\n  enter U.S. Securities business by taking a share in American\n  investment bank Goldman, Sachs and Co.\n      Sumitomo last August agreed to pay 500 mln dlrs for a 12.5\n  pct limited partnership in the bank, but for the time being at\n  least, the Federal Reserve Board has forbidden them to exchange\n  personnel, or increase the business they do with each other.\n      "The tie-up is widely looked on as a lame duck because the\n  Fed was stricter than Sumitomo expected," said one analyst.\n      But Komatsu said the move will pay off in time.\n      "U.S. Regulations will change in the near future and if so,\n  we can do various things. We only have to wait two or three\n  years, not until the 21st century," Komatsu said.\n      Komatsu is also willing to be patient about possible routes\n  into the securities business at home.\n      Article 65 of the Securities and Exchange Act, Japan's\n  version of the U.S. Glass-Steagall Act, separates commercial\n  from investment banking.\n      But the walls between the two are crumbling and Komatsu\n  said he hopes further deregulation will create new\n  opportunities.\n      "We need to find new business chances," Komatsu said. "In some\n  cases these will be securities related, in some cases trust\n  bank related. That's the kind of deregulation we want."\n      Until such changes occur, Sumitomo will focus on such\n  domestic securities business as profitable government bond\n  dealing and strengthening relations with Meiko Securities Co\n  Ltd, in which it holds a five pct share, Komatsu said.\n      He said Sumitomo is cautiously optimistic about entering\n  the securities business here through its Swiss universal bank\n  subsidiary, Banca del Gottardo.\n       The Finance Ministry is expected to grant licences to\n  securities subsidiaries of U.S. Commercial banks soon,\n  following a similar decision for subsidiaries of European\n  universal banks in which the parent holds a less than 50 pct.\n      But Komatsu is reluctant to push hard for a similar\n  decision on a Gottardo subsidiary.\n      "We don't want to make waves. We expect this will be allowed\n  in two or three years," he said.\n      Like other city banks, Sumitomo is also pushing to expand\n  lending to individuals and small and medium businesses to\n  replace disappearing demand from big business, he added.\n      The analysts said Sumitomo will have to devote a lot of\n  time to digesting its most recent initiatives, including the\n  merger with ailing Heiwa Sogo.\n      "It's (Sumitomo) been bold in its strategies," said\n  Kleinwort's Smithson.\n      "After that, it's a question of absorbing and juggling\n  around. It will be the next decade before we see if the\n  strategy is right or wrong."\n  \n\n</th>
      <td>acq</td>
      <td>test</td>
      <td>SUMITOMO BANK AIMS AT QUICK RECOVERY FROM MERG...</td>
    </tr>
  </tbody>
</table>
</div>


