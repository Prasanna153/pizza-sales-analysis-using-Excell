# Insights & recommendations

All figures below come from 48,620 order lines covering 1 January – 31 December 2015
($817,860 revenue, 21,350 orders). They can be regenerated with
`python analysis/generate_report.py`.

## 1. Time of day drives everything

| Hour | Orders |
| --- | --- |
| 12 pm | 2,520 |
| 1 pm | 2,455 |
| 6 pm | 2,399 |
| 5 pm | 2,336 |
| 7 pm | 2,009 |

Two peaks — a lunch rush at 12–1 pm and a dinner rush at 5–7 pm — account for the
bulk of the day. The 11 pm hour barely registers.

**Recommendation:** concentrate kitchen and delivery staff on those five hours;
consider closing the dead late hour or converting it to prep time.

## 2. The weekly curve is real but modest

Friday is the strongest day (3,538 orders), followed by Thursday (3,239) and Saturday
(3,158). Sunday is the weakest (2,624). The gap between best and worst day is about 35%.

**Recommendation:** shift promotions to Sunday and Monday rather than discounting on
Friday, when demand needs no help.

## 3. Size mix is where the margin is

| Size | Revenue | Share |
| --- | --- | --- |
| L | $375,319 | 45.9% |
| M | $249,382 | 30.5% |
| S | $178,077 | 21.8% |
| XL | $14,076 | 1.7% |
| XXL | $1,007 | 0.1% |

**Recommendation:** upsell S → M → L aggressively; review whether XL and XXL earn
their inventory and menu complexity.

## 4. Categories are balanced, individual pizzas are not

Category revenue is remarkably even — Classic $220,053, Supreme $208,197,
Chicken $195,920, Veggie $193,690 — so no category should be cut.

Individual items tell a different story:

| Best sellers | Revenue | Weakest | Revenue |
| --- | --- | --- | --- |
| Thai Chicken | $43,434 | Brie Carre | $11,589 |
| Barbecue Chicken | $42,768 | Green Garden | $13,956 |
| California Chicken | $41,410 | Spinach Supreme | $15,278 |
| Classic Deluxe | $38,181 | Mediterranean | $15,361 |
| Spicy Italian | $34,831 | Spinach Pesto | $15,596 |

The top pizza earns roughly 3.7× the bottom one. Chicken pizzas take three of the
top five slots.

**Recommendation:** feature the chicken line prominently; test replacing the bottom
two or three items before a menu reprint.

## 5. No seasonality to plan around

Monthly revenue ranges from $64,028 (October) to $72,558 (July) — a spread of about
13% with no sustained trend. July, May and March are marginally stronger; September,
October and December marginally weaker.

**Recommendation:** treat capacity planning as a weekly and hourly problem, not a
seasonal one.

## Caveats

- Single year of data, single location — no year-over-year comparison is possible.
- Revenue only; there is no cost data, so profitability by pizza cannot be computed.
  The "weakest items" above are weakest by revenue, not by margin.
- `total_price` is used throughout; it equals `quantity × unit_price` in this dataset.
