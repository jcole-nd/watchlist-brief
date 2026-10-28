# Evaluation test set

Fill this in after every refresh, before you publish. The agent is the system under test.
You are the grader. Nothing here is automated on purpose: the point is to decide, with a
source you trust, whether the agent told you the truth.

**Ground truth sources.** Pick one and use the same one every time, so your scores are
comparable week to week:

- Prices: Google Finance (google.com/finance), Yahoo Finance, or your brokerage app.
- News: the article itself. Open the link. Check the date on the page.
- Calendar: the company's investor relations page (search "TICKER investor relations
  events"), or the Fed's own meeting calendar for FOMC dates.

Refresh date: 2026-10-28    Grader: number-checker

## A. Prices (one row per ticker)

Pass if the dashboard's last price is within $0.10 of the ground truth for the same day
and the same price type (close vs intraday). If the agent recorded an intraday price,
compare against the intraday price at about the same time; do not compare it to a close.

Block dated 2026-10-28 (checker: number-checker). Google Finance returned "isn't supported on this device"
for all fetches (https://www.google.com/finance/quote/NVDA:NASDAQ), so no per-day closes were available there.
Every row below uses Stock Analysis history pages instead. Note: this is the same site the brief used as its
price source, so these rows are not an independent second source. The Oct 28 rows are intraday (page showed
10:07 or 10:08 AM EDT), compared with the intraday figure on the same page, not with a close.

| Ticker | Date shown | Price type shown | Dashboard price | Ground truth price | Source you used | Pass / Fail |
|---|---|---|---|---|---|---|
| NVDA | 2026-10-21 | close | 221.97 | 221.97 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| NVDA | 2026-10-22 | close | 212.21 | 212.21 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| NVDA | 2026-10-23 | close | 210.96 | 210.96 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| NVDA | 2026-10-26 | close | 216.00 | 216.00 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| NVDA | 2026-10-27 | close | 217.94 | 217.94 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| NVDA | 2026-10-28 10:07 | intraday | 217.97 | 217.97 (page time about 10:07 to 10:08 AM EDT) | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| JPM | 2026-10-21 | close | 335.19 | 335.19 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| JPM | 2026-10-22 | close | 336.54 | 336.54 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| JPM | 2026-10-23 | close | 331.58 | 331.58 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| JPM | 2026-10-26 | close | 334.04 | 334.04 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| JPM | 2026-10-27 | close | 335.79 | 335.79 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| JPM | 2026-10-28 10:07 | intraday | 336.82 | 336.82 (page time 10:07 AM EDT) | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| ACN | 2026-10-21 | close | 240.26 | 240.26 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| ACN | 2026-10-22 | close | 258.74 | 258.74 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| ACN | 2026-10-23 | close | 249.37 | 249.37 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| ACN | 2026-10-26 | close | 247.23 | 247.23 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| ACN | 2026-10-27 | close | 235.16 | 235.16 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| ACN | 2026-10-28 10:07 | intraday | 243.05 | 243.05 (intraday, market open) | https://stockanalysis.com/stocks/acn/history/ | Pass |
| WM | 2026-10-21 | close | 229.58 | 229.58 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| WM | 2026-10-22 | close | 239.10 | 239.10 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| WM | 2026-10-23 | close | 239.38 | 239.38 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| WM | 2026-10-26 | close | 241.02 | 241.02 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| WM | 2026-10-27 | close | 235.81 | 235.81 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| WM | 2026-10-28 10:08 | intraday | 229.43 | 229.43 (page time 10:08 AM EDT) | https://stockanalysis.com/stocks/wm/history/ | Pass |
| LLY | 2026-10-21 | close | 1270.75 | 1270.75 | https://stockanalysis.com/stocks/lly/history/ | Pass |
| LLY | 2026-10-22 | close | 1306.69 | 1306.69 | https://stockanalysis.com/stocks/lly/history/ | Pass |
| LLY | 2026-10-23 | close | 1273.46 | 1273.46 | https://stockanalysis.com/stocks/lly/history/ | Pass |
| LLY | 2026-10-26 | close | 1279.14 | 1279.14 | https://stockanalysis.com/stocks/lly/history/ | Pass |
| LLY | 2026-10-27 | close | 1281.91 | 1281.91 | https://stockanalysis.com/stocks/lly/history/ | Pass |
| LLY | 2026-10-28 10:07 | intraday | 1293.50 | 1293.50 (page time 10:07 AM EDT) | https://stockanalysis.com/stocks/lly/history/ | Pass |

RE-CHECK block dated 2026-10-28 (after the owner changed three "why" lines; checker: number-checker). Google Finance
was not retried; the earlier block found it unsupported (https://www.google.com/finance/quote/NVDA:NASDAQ). Rows use Stock
Analysis again, which is the same site the brief used, so this is not an independent second source. The Oct 28 quotes read
10:07 AM EDT (WM 10:08 AM EDT) and are intraday, compared with the intraday quote, not a close. Fetched again, values unchanged.

| Ticker | Date shown | Price type shown | Dashboard price | Ground truth price | Source you used | Pass / Fail |
|---|---|---|---|---|---|---|
| NVDA | 2026-10-21 | close | 221.97 | 221.97 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| NVDA | 2026-10-22 | close | 212.21 | 212.21 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| NVDA | 2026-10-23 | close | 210.96 | 210.96 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| NVDA | 2026-10-26 | close | 216.00 | 216.00 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| NVDA | 2026-10-27 | close | 217.94 | 217.94 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| NVDA | 2026-10-28 10:07 | intraday | 217.97 | 217.97 | https://stockanalysis.com/stocks/nvda/history/ | Pass |
| JPM | 2026-10-21 | close | 335.19 | 335.19 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| JPM | 2026-10-22 | close | 336.54 | 336.54 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| JPM | 2026-10-23 | close | 331.58 | 331.58 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| JPM | 2026-10-26 | close | 334.04 | 334.04 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| JPM | 2026-10-27 | close | 335.79 | 335.79 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| JPM | 2026-10-28 10:07 | intraday | 336.82 | 336.82 | https://stockanalysis.com/stocks/jpm/history/ | Pass |
| ACN | 2026-10-21 | close | 240.26 | 240.26 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| ACN | 2026-10-22 | close | 258.74 | 258.74 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| ACN | 2026-10-23 | close | 249.37 | 249.37 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| ACN | 2026-10-26 | close | 247.23 | 247.23 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| ACN | 2026-10-27 | close | 235.16 | 235.16 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| ACN | 2026-10-28 10:07 | intraday | 243.05 | 243.05 | https://stockanalysis.com/stocks/acn/history/ | Pass |
| WM | 2026-10-21 | close | 229.58 | 229.58 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| WM | 2026-10-22 | close | 239.10 | 239.10 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| WM | 2026-10-23 | close | 239.38 | 239.38 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| WM | 2026-10-26 | close | 241.02 | 241.02 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| WM | 2026-10-27 | close | 235.81 | 235.81 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| WM | 2026-10-28 10:08 | intraday | 229.43 | 229.43 | https://stockanalysis.com/stocks/wm/history/ | Pass |
| LLY | 2026-10-21 | close | 1270.75 | 1270.75 | https://stockanalysis.com/stocks/lly/history/ | Pass |
| LLY | 2026-10-22 | close | 1306.69 | 1306.69 | https://stockanalysis.com/stocks/lly/history/ | Pass |
| LLY | 2026-10-23 | close | 1273.46 | 1273.46 | https://stockanalysis.com/stocks/lly/history/ | Pass |
| LLY | 2026-10-26 | close | 1279.14 | 1279.14 | https://stockanalysis.com/stocks/lly/history/ | Pass |
| LLY | 2026-10-27 | close | 1281.91 | 1281.91 | https://stockanalysis.com/stocks/lly/history/ | Pass |
| LLY | 2026-10-28 10:07 | intraday | 1293.50 | 1293.50 | https://stockanalysis.com/stocks/lly/history/ | Pass |

## B. Weekly change (one row per ticker)

The page computes this from the five closes. Pass if it is within 0.3 percentage points of
your own calculation: (last price minus the close five trading days earlier) divided by
that earlier close.

Block dated 2026-10-28. Definition used by the page (`weekChange()` in index.html): (last point minus first
point) divided by first point, where the points are the five closes plus `latest.price` when `latest` exists.
First point is the 2026-10-21 close, which is five trading days before 2026-10-28, so it matches the task
definition. Last price is the intraday `latest.price`. The page displays one decimal; two decimals shown here.
Closes used are the ones verified in section A (source: https://stockanalysis.com/stocks/TICKER/history/).

| Ticker | Dashboard weekly change | Your calculation | Pass / Fail |
|---|---|---|---|
| NVDA | (217.97 - 221.97) / 221.97 = -1.80% (page shows -1.8%) | (217.97 - 221.97) / 221.97 = -1.80% | Pass |
| JPM | (336.82 - 335.19) / 335.19 = +0.49% (page shows +0.5%) | (336.82 - 335.19) / 335.19 = +0.49% | Pass |
| ACN | (243.05 - 240.26) / 240.26 = +1.16% (page shows +1.2%) | (243.05 - 240.26) / 240.26 = +1.16% | Pass |
| WM | (229.43 - 229.58) / 229.58 = -0.07% (page shows -0.1%) | (229.43 - 229.58) / 229.58 = -0.07% | Pass |
| LLY | (1293.50 - 1270.75) / 1270.75 = +1.79% (page shows +1.8%) | (1293.50 - 1270.75) / 1270.75 = +1.79% | Pass |

RE-CHECK block dated 2026-10-28. Same `weekChange()` definition as above: (last point minus first point) divided by first
point, with the 2026-10-21 close first and the intraday `latest.price` last. Closes re-verified in the re-check block of A
(source: https://stockanalysis.com/stocks/TICKER/history/).

| Ticker | Dashboard weekly change | Your calculation | Pass / Fail |
|---|---|---|---|
| NVDA | (217.97 - 221.97) / 221.97 = -1.80% | (217.97 - 221.97) / 221.97 = -1.80% (https://stockanalysis.com/stocks/nvda/history/) | Pass |
| JPM | (336.82 - 335.19) / 335.19 = +0.49% | (336.82 - 335.19) / 335.19 = +0.49% (https://stockanalysis.com/stocks/jpm/history/) | Pass |
| ACN | (243.05 - 240.26) / 240.26 = +1.16% | (243.05 - 240.26) / 240.26 = +1.16% (https://stockanalysis.com/stocks/acn/history/) | Pass |
| WM | (229.43 - 229.58) / 229.58 = -0.07% | (229.43 - 229.58) / 229.58 = -0.07% (https://stockanalysis.com/stocks/wm/history/) | Pass |
| LLY | (1293.50 - 1270.75) / 1270.75 = +1.79% | (1293.50 - 1270.75) / 1270.75 = +1.79% (https://stockanalysis.com/stocks/lly/history/) | Pass |

## C. News grounding (one row per news item, three per ticker)

Open every link. Pass only if all four are true: the link opens, the headline matches the
article, the article date is within the last seven days, and the "why it matters" line is
supported by the article (not just plausible).

Block dated 2026-10-28. Window is 2026-10-21 to 2026-10-28 inclusive. All 12 links opened on the first try.

| Ticker | Headline (first few words) | Link opens | Headline matches | Dated within 7 days | "Why" is supported | Source | Pass / Fail |
|---|---|---|---|---|---|---|---|
| NVDA | Nvidia to invest $3B in Meta's... | yes | yes | yes (page: 2026-10-27) | yes (Meta expands Nvidia deployment, financing context in article) | https://stockanalysis.com/news/nvidia-3-billion-meta-offering/ | Pass |
| NVDA | Nvidia, Oracle expand NVIDIA Vera Rubin... | yes | yes | yes (page: 2026-10-27) | yes (article cites rising customer demand and multi-gigawatt scale) | https://www.tipranks.com/news/the-fly/nvidia-oracle-expand-nvidia-vera-rubin-to-multi-gigawatt-scale-thefly-news | Pass |
| JPM | J.P. Morgan Asset Management Expands Access... | yes | yes | yes (page: 2026-10-22) | no: "a small but growing line in its asset management business" | https://www.prnewswire.com/news-releases/jp-morgan-asset-management-expands-access-to-its-tokenized-money-market-funds-on-solana-302917188.html | Fail (unsupported: "small", article says nothing about the size of the line) |
| ACN | Accenture awarded $151.46M Air Force... | yes | yes | yes (page: 2026-10-27) | no: "though it is small next to Accenture's total sales"; article also never says "multi-year" (it gives completion by 2030-06-30) | https://www.tipranks.com/news/the-fly/accenture-awarded-151-46m-air-force-task-order-thefly-news | Fail (unsupported: comparison to total sales) |
| ACN | Accenture downgraded to Neutral from Outperform... | yes | yes | yes (page: 2026-10-21) | no: "Baird said the stock looks fully valued"; article calls the multiple "reasonable" and says shares have more than doubled since June | https://www.tipranks.com/news/the-fly/accenture-downgraded-to-neutral-from-outperform-at-baird-thefly-news | Fail (unsupported: "fully valued", "cap further gains") |
| WM | WM reports Q3 EPS $2.15... | yes | yes | yes (page: 2026-10-27) | yes (revenue $6.85B vs $6.81B consensus; EPS $2.15 vs $2.18) | https://www.tipranks.com/news/the-fly/wm-reports-q3-eps-2-15-consensus-2-18-thefly-news | Pass |
| WM | WM sees FY26 revenue at high end... | yes | yes | yes (page: 2026-10-27) | yes (WM expects to meet full-year guidance, revenue at high end) | https://www.tipranks.com/news/the-fly/wm-sees-fy26-revenue-at-high-end-of-26-275b-26-475b-guidance-range-thefly-news | Pass |
| LLY | Lilly's retatrutide delivered greater A1C... | yes | yes | yes (page: 2026-10-28) | yes (Phase 3 TRANSCEND-T2D-2; discontinuation due to adverse events 7.9% at 12 mg vs 2.7% Ozempic). "Day before earnings" is not in the article but matches the verified 2026-10-29 date in D | https://www.prnewswire.com/news-releases/lillys-retatrutide-delivered-greater-a1c-reduction-and-more-than-double-the-weight-loss-of-ozempics-highest-approved-dose-in-head-to-head-trial-302921328.html | Pass |
| LLY | Patrik Jonsson to retire after 36 years... | yes | yes | yes (page: 2026-10-27) | yes (US and international businesses combine as Lilly Global Markets effective 2027-01-01) | https://www.prnewswire.com/news-releases/patrik-jonsson-to-retire-after-36-years-ilya-yuffa-named-president-lilly-global-markets-302921191.html | Pass |
| LLY | Lilly declares fourth-quarter 2026 dividend | yes | yes | yes (page: 2026-10-26) | yes ($1.73, record 2026-11-13, payable 2026-12-10) | https://www.prnewswire.com/news-releases/lilly-declares-fourth-quarter-2026-dividend-302919496.html | Pass |

RE-CHECK block dated 2026-10-28. The owner rewrote the "why" lines of the JPM tokenized funds, ACN Air Force and ACN Baird
items (the three Fails above stay as the record). All 12 links opened again on the first try. Window is 2026-10-21 to
2026-10-28 inclusive. The ACN CHANGELOG line now reads "Baird downgraded to Neutral; Air Force task order won" with no
"on valuation".

| Ticker | Headline (first few words) | Link opens | Headline matches | Dated within 7 days | "Why" is supported | Source | Pass / Fail |
|---|---|---|---|---|---|---|---|
| NVDA | Nvidia to invest $3B in Meta's... | yes | yes | yes (page: 2026-10-27) | yes (Nvidia $3B into Meta's stock sale; Meta to deploy more Nvidia infrastructure; article links it to financing AI spending) | https://stockanalysis.com/news/nvidia-3-billion-meta-offering/ | Pass |
| NVDA | Nvidia, Oracle expand NVIDIA Vera Rubin... | yes | yes | yes (page: 2026-10-27) | yes (OCI expansion on Vera Rubin NVL72, growing customer demand cited) | https://www.tipranks.com/news/the-fly/nvidia-oracle-expand-nvidia-vera-rubin-to-multi-gigawatt-scale-thefly-news | Pass |
| JPM | J.P. Morgan Asset Management Expands Access... | yes | yes | yes (page: 2026-10-22) | yes. New why: "widening access to its tokenized cash management products". Release: "This expansion broadens access for clients" and supports "growth of J.P. Morgan Asset Management's tokenized cash management platform". "Small" is gone | https://www.prnewswire.com/news-releases/jp-morgan-asset-management-expands-access-to-its-tokenized-money-market-funds-on-solana-302917188.html | Pass (re-check of earlier Fail) |
| ACN | Accenture awarded $151.46M Air Force... | yes | yes | yes (page: 2026-10-27) | yes. New why: "$151.46M, with completion set for 2030-06-30". Article: $151.46M task order, "expected to be completed by June 30, 2030". Sales comparison and "multi-year" are gone | https://www.tipranks.com/news/the-fly/accenture-awarded-151-46m-air-force-task-order-thefly-news | Pass (re-check of earlier Fail) |
| ACN | Accenture downgraded to Neutral from Outperform... | yes | yes | yes (page: 2026-10-21) | yes. New why: shares "more than doubled since June" and multiple "reasonable". Article: "The shares have over doubled since June" (Baird's view) and the multiple is "reasonable" for 7%-9% EPS growth. "Fully valued" and "cap further gains" are gone. Note: the article's main stated basis for the downgrade is valuation after the rally, so removing "on valuation" from the changelog loses detail but is not an error | https://www.tipranks.com/news/the-fly/accenture-downgraded-to-neutral-from-outperform-at-baird-thefly-news | Pass (re-check of earlier Fail) |
| WM | WM reports Q3 EPS $2.15... | yes | yes | yes (page: 2026-10-27) | yes (revenue $6.85B vs $6.81B consensus; EPS $2.15 vs $2.18) | https://www.tipranks.com/news/the-fly/wm-reports-q3-eps-2-15-consensus-2-18-thefly-news | Pass |
| WM | WM sees FY26 revenue at high end... | yes | yes | yes (page: 2026-10-27) | yes ("The Company expects to achieve its full-year financial guidance") | https://www.tipranks.com/news/the-fly/wm-sees-fy26-revenue-at-high-end-of-26-275b-26-475b-guidance-range-thefly-news | Pass |
| LLY | Lilly's retatrutide delivered greater A1C... | yes | yes | yes (page: 2026-10-28) | yes (Phase 3; discontinuation 7.9% at 12 mg vs 2.7% Ozempic). "Day before earnings" is not in the article but matches the 2026-10-29 date in D | https://www.prnewswire.com/news-releases/lillys-retatrutide-delivered-greater-a1c-reduction-and-more-than-double-the-weight-loss-of-ozempics-highest-approved-dose-in-head-to-head-trial-302921328.html | Pass |
| LLY | Patrik Jonsson to retire after 36 years... | yes | yes | yes (page: 2026-10-27) | yes ("Effective Jan. 1, 2027, Lilly's U.S. and international businesses will come together as Lilly Global Markets") | https://www.prnewswire.com/news-releases/patrik-jonsson-to-retire-after-36-years-ilya-yuffa-named-president-lilly-global-markets-302921191.html | Pass |
| LLY | Lilly declares fourth-quarter 2026 dividend | yes | yes | yes (page: 2026-10-26) | yes ($1.73, record 2026-11-13, payable 2026-12-10) | https://www.prnewswire.com/news-releases/lilly-declares-fourth-quarter-2026-dividend-302919496.html | Pass |

(Add rows as needed. Fifteen items is normal for five tickers.)

## D. Calendar (one row per event)

Pass if the event and its date appear on the source linked, and the date is in the future
relative to the refresh date.

Block dated 2026-10-28. NVDA, JPM, ACN, WM have empty `upcoming` lists, so there are no rows to check for them.
Only one event exists in the brief. Lilly's IR pages returned HTTP 403 (https://investor.lilly.com/events-and-presentations,
https://investor.lilly.com/node/55096, https://lilly.gcs-web.com/news-releases/news-release-details/lilly-confirms-date-and-conference-call-third-quarter-2026).
I used Lilly's own press release of 2026-10-15 as reproduced on BioSpace and Finviz. The brief cites only the Finviz copy (an aggregator).

| Ticker | Event | Date shown | Confirmed on source | Source | Pass / Fail |
|---|---|---|---|---|---|
| LLY | Third-quarter 2026 results; conference call at 10 a.m. ET | 2026-10-29 | yes, the release says Lilly "will announce its third-quarter 2026 financial results on October 29, 2026" with a 10 a.m. ET call; stated as fact, not "expected"; date is after asOf | https://www.biospace.com/press-releases/lilly-confirms-date-and-conference-call-for-third-quarter-2026-financial-results-announcement (also opened: https://finviz.com/news/403165/lilly-confirms-date-and-conference-call-for-third-quarter-2026-financial-results-announcement) | Pass (caveat: Lilly IR page and PR Newswire copy not opened; company press release text only seen on BioSpace and Finviz) |

RE-CHECK block dated 2026-10-28. Same single event. Lilly's IR page returned HTTP 403 again
(https://investor.lilly.com/events-and-presentations), so the BioSpace copy of Lilly's own press release was used.

| Ticker | Event | Date shown | Confirmed on source | Source | Pass / Fail |
|---|---|---|---|---|---|
| LLY | Third-quarter 2026 results; conference call at 10 a.m. ET | 2026-10-29 | yes, release dated 2026-10-15: Lilly "will announce its third-quarter 2026 financial results on October 29, 2026", call at 10 a.m. Eastern; stated as fact, not "expected"; date is after asOf | https://www.biospace.com/press-releases/lilly-confirms-date-and-conference-call-for-third-quarter-2026-financial-results-announcement | Pass (caveat: Lilly IR page not opened; the brief cites only the Finviz aggregator copy) |

## E. Omissions

Did the agent miss something a human analyst would have included? List anything you found
in the ground-truth sources that the brief does not mention (a big headline, an earnings
date inside the window). Each one counts as a Fail in the score below.

- 
- 

## F. Your own test cases

Write two tests of your own that none of the sections above cover. Examples students have
used: "the as-of date on the page matches the changelog date", "no ticker shows a flat
sparkline when the real stock moved", "the page still renders if I delete one ticker's
news list in the data". Write the test, run it, record the result.

| Test | How you checked | Pass / Fail |
|---|---|---|
| | | |
| | | |

## Score

| Section | Passes | Total | Rate |
|---|---|---|---|
| A. Prices | | | |
| B. Weekly change | | | |
| C. News | | | |
| D. Calendar | | | |
| E. Omissions (fails only) | 0 | | |
| F. Your own | | | |
| **Overall** | | | |

Publish only if A and B are 100% and C is at least 80% after fixes. If a row failed, tell
Claude exactly which row and what the correct value is, let it fix only that, rerun the
`qa-reviewer` agent, and regrade that row. Keep the original Fail in this file: a record of
what the agent got wrong is more useful than a clean sheet.
