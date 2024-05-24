<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Ev
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Electric vehicles and all their suppliers will outgrow combustion engines and their suppliers.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| AAPL | Apple, rumored to be entering the EV market, could bring its significant resources and innovation to electric vehicles. | chat_gpt |
| ALB | Albemarle is a leading producer of lithium, a critical component in EV batteries, benefiting from the surge in EV production. | chat_gpt,claude,google |
| BLNK | Blink Charging is expanding its network of electric vehicle charging stations, essential infrastructure for the growing EV market. | chat_gpt,claude,google |
| BYD | BYD is not only a major electric vehicle producer but also a large battery manufacturer, benefiting from the EV trend. | chat_gpt |
| CHPT | ChargePoint operates one of the largest networks of EV charging stations, benefiting from increased EV adoption. | chat_gpt,claude,google |
| ENPH | Enphase Energy, a leader in solar microinverters, benefits from the trend as EV owners seek sustainable charging options. | chat_gpt |
| F | Ford has committed to electrifying its fleet, introducing electric versions of popular models like the F-150. | chat_gpt,twitter,google |
| GM | General Motors is making significant investments in electric vehicles and autonomous driving technologies. | chat_gpt |
| LI | Li Auto is another Chinese EV manufacturer, specializing in electric SUVs and benefiting from China's push for electric vehicles. | chat_gpt,claude,google |
| NIO | NIO is a prominent electric vehicle manufacturer in China, showing rapid growth and expansion. | chat_gpt,claude,twitter,google |
| PLUG | Plug Power is involved in hydrogen fuel cell technology, which could power future electric vehicles and infrastructure. | chat_gpt,claude |
| QS | QuantumScape is developing solid-state battery technology, which could revolutionize battery efficiency and safety for EVs. | chat_gpt,claude,google |
| RIVN | Rivian focuses on electric trucks and SUVs, a segment with significant growth potential in the EV market. | chat_gpt,claude,twitter,google |
| SEDG | SolarEdge Technologies provides solar inverters and technology, indirectly benefiting from the demand for green EV charging solutions. | chat_gpt |
| SQM | Sociedad Quimica y Minera is a major supplier of lithium, benefiting from the global increase in demand for EV batteries. | chat_gpt,claude |
| TSLA | Tesla is a leader in electric vehicles, constantly innovating in both vehicle technology and battery production. | chat_gpt,claude,twitter,google |
| XPEV | XPeng is a Chinese electric vehicle manufacturer with strong growth potential, focusing on smart, technology-driven EVs. | chat_gpt,claude,google |
| EVGO |  | claude,google |
| LCID |  | claude |
| NKLA |  | claude,google |
| SLDP |  | claude,google |
| AKBA |  | twitter |
| BP |  | twitter |
| ES |  | twitter |
| ALV |  | google |
| FCX |  | google |
| GNTX |  | google |
| WBX |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/ev/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/ev" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
