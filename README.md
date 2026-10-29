# Amazon Scraping Benchmark

AIMultiple benchmark of five Amazon scraper APIs (Apify, Bright Data, Decodo, Nimble and Zyte) on product and search pages across 11 Amazon domains. The study measures success rate and end-to-end completion time.

> [Read the benchmark on AIMultiple](https://aimultiple.com/amazon-scraper)

## Workload

The run covers 2,750 requests on amazon.com, .ca, .com.mx, .com.br, .co.uk, .de, .fr, .it, .es, .co.jp and .in. These results are the Amazon subset of AIMultiple's e-commerce scraping benchmark, which tested 5 providers across 100 e-commerce domains.

A request counted as a success only when its content passed a validation check against ground truth. Completion time is the end-to-end time of a request in seconds.

Providers used different routes: Bright Data a separate dataset per page type, Decodo its amazon_search endpoint for search and its Site Unblocker (rendered HTML) for product pages, Zyte automatic extraction in a headless browser, and Apify its E-commerce Scraping Tool actor.

## Benchmark results

Success rate and completion time, averaged across the 11 domains:

| Provider | Success rate (%) | Completion time (s) |
| --- | ---: | ---: |
| Apify | 95 | 43 |
| Bright Data | 93 | 14 |
| Decodo | 91 | 19 |
| Zyte | 91 | 34 |
| Nimble | 26 | 5 |

Nimble had the shortest time but returned usable data only on amazon.com (92%), .com.br (98%) and .com.mx (94%). Every provider scored lower on search pages than on product pages, and Apify took 64 s on search against 23 s on product pages.

## Scope

Results cover product and search pages only, and single domains moved far from the averages (Bright Data 48% on amazon.com.mx, Zyte 58% on amazon.fr). Amazon's anti-scraping technology keeps getting harder to bypass, so results can shift. Success rate does not measure data depth: on product pages Bright Data returned 88 fields, Apify 10, and Decodo HTML rather than structured JSON.

## Ownership

The benchmark implementation was developed for AIMultiple and belongs to AIMultiple. This repository contains a documentation summary. Source code and benchmark datasets are not distributed here.
