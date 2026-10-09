# US bank and credit union email census, 2026

Now with a second table set: the US credit union market from the NCUA June 2026 call report (see [Credit union market census](#credit-union-market-census-june-2026)).

Aggregate tables from [Provena](https://www.provena-ai.com/)'s October 2026 census of how US banks and credit unions receive and authenticate email. Each table here is the downloadable form of the published study; the study page carries the full method, charts, limits and discussion.

Aggregate tables only. The underlying domain list is not published, and nothing here identifies a person.

## Headline figures

- 7,537 bank and credit union website domains that receive mail (3,947 banks, 3,590 credit unions), from the FDIC BankFind and NCUA June 2026 lists.
- 41% route inbound mail through a dedicated security gateway; 42% point straight at Microsoft 365; Google Workspace receives 2%.
- 60% enforce DMARC (quarantine or reject): banks 72%, credit unions 46%. US franchise car dealers enforce at 23%, so financial institutions are 2.6 times as likely to enforce.
- Proofpoint fronts 36% of gateway domains, then Barracuda (20%) and Mimecast (16%).
- 99% of mail-receiving .bank institution domains reject spoofed mail.

## Datasets

| File | Coverage | Rows |
| --- | --- | --- |
| [`data/bank-credit-union-email-census.csv`](data/bank-credit-union-email-census.csv) | Receiving provider, SPF and DMARC by cohort (all, institution type, asset band, charter, top-level domain, state) | 55 |
| [`data/bank-credit-union-gateway-vendors.csv`](data/bank-credit-union-gateway-vendors.csv) | Security gateway vendor share among the 3,107 gateway domains, overall and by cohort | 144 |
| [`data/credit-union-market-census.csv`](data/credit-union-market-census.csv) | Credit union market by asset band and charter, NCUA June 2026 | 8 |
| [`data/credit-union-networks.csv`](data/credit-union-networks.csv) | Shared branching and ATM networks credit unions name | 18 |

- **Study:** [US Bank and Credit Union Email Census: 7,537 Domains](https://www.provena-ai.com/blog/bank-credit-union-email-census)
- **Method:** DNS MX and TXT resolution of each institution's website domain against public resolvers; MX hosts classified by provider; SPF classified by its all mechanism, DMARC by its p tag; cohorts of at least 100 domains (50 within charter and asset band)
- **Period:** 2026-10-07; **area:** United States
- **Sources:** FDIC BankFind (banks) and NCUA call report data, June 2026 (credit unions)
- **Columns (census):** `cohort_type`, `cohort`, `domains`, `gateway_pct`, `microsoft365_pct`, `google_pct`, `other_mail_pct`, `has_spf_pct`, `spf_hardfail_pct`, `has_dmarc_pct`, `dmarc_p_none_pct`, `dmarc_quarantine_pct`, `dmarc_reject_pct`, `dmarc_enforced_pct`, `spf_without_dmarc_pct`, `dmarc_rua_pct`
- **Columns (vendors):** `table`, `cohort`, `gateway`, `domains`, `share_of_gateway_domains_pct`

Percentages are shares of the cohort's mail-receiving domains, rounded to one decimal place.

## Credit union market census, June 2026

Aggregates of the NCUA call report for the quarter ending 30 June 2026, all 4,299 credit unions that filed. Institution-level public fields only; officer and contact name fields were not read.

- 479 credit unions at $1 billion and over in assets (11%) hold 79% of credit union assets and 76% of members; 2,479 under $100 million (58%) hold 3%.
- Median staff: 5 under $100 million, 40 between $100 million and $500 million, 330 at $1 billion and over (full-time plus half of part-time).
- 61% of credit unions under $100 million offer a mobile app, against 98% or more in every larger band.
- 1,767 credit unions (41%) hold indirect new and used vehicle loans: 17.3 million loans, $270 billion, 78% of all indirect lending and 15% of all credit union loans.
- CO-OP is the network named most often: 937 credit unions for shared branching and 1,069 for surcharge-free ATMs.

- **Study:** [Selling to Credit Unions: What 4,299 Call Reports Show](https://www.provena-ai.com/blog/selling-to-credit-unions)
- **Columns (market):** `cohort_type`, `cohort`, `credit_unions`, `share_of_assets_pct`, `share_of_members_pct`, `median_members`, `median_fte_staff`, `median_branches`, `members_per_fte`, `online_banking_pct`, `mobile_app_pct`, `p2p_payments_pct`, `shared_branching_pct`, `surcharge_free_atm_network_pct`, `indirect_lending_pct`, `indirect_share_of_loans_pct`, `indirect_vehicle_lending_pct`, `vehicle_share_of_indirect_pct`, `indirect_vehicle_share_of_loans_pct`
- **Columns (networks):** `network_type`, `network`, `credit_unions_naming_it`
- **Limits:** service fields are self-reported yes or no answers; network names are free text grouped by name; the CUSO name fields are blank in the public June 2026 file, so CUSOs are not reported.

## Selling software to banks and credit unions?

These tables come out of Provena's own research into how financial institutions receive email. If you sell software or services to banks and credit unions, these guides use the same data to plan how you reach them:

- Selling to credit unions, who decides at each size and how to reach them: https://www.provena-ai.com/blog/selling-to-credit-unions
- How fintech companies sell to financial institutions: https://www.provena-ai.com/blog/how-to-sell-fintech-to-financial-institutions
- Fintech and financial services lead generation agencies compared: https://www.provena-ai.com/blog/best-fintech-lead-generation-agencies

## Related

- [US car dealership email and website census](https://github.com/danielmcgrattan2007/us-car-dealership-census), the same method applied to 17,659 dealer domains.
- [All Provena research](https://www.provena-ai.com/research)

## Licence and citation

[CC BY 4.0](LICENSE). Reuse freely with credit to Provena and a link to the [study page](https://www.provena-ai.com/blog/bank-credit-union-email-census). See [`CITATION.cff`](CITATION.cff).
