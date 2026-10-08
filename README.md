# US bank and credit union email census, 2026

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

- **Study:** [US Bank and Credit Union Email Census: 7,537 Domains](https://www.provena-ai.com/blog/bank-credit-union-email-census)
- **Method:** DNS MX and TXT resolution of each institution's website domain against public resolvers; MX hosts classified by provider; SPF classified by its all mechanism, DMARC by its p tag; cohorts of at least 100 domains (50 within charter and asset band)
- **Period:** 2026-10-07; **area:** United States
- **Sources:** FDIC BankFind (banks) and NCUA call report data, June 2026 (credit unions)
- **Columns (census):** `cohort_type`, `cohort`, `domains`, `gateway_pct`, `microsoft365_pct`, `google_pct`, `other_mail_pct`, `has_spf_pct`, `spf_hardfail_pct`, `has_dmarc_pct`, `dmarc_p_none_pct`, `dmarc_quarantine_pct`, `dmarc_reject_pct`, `dmarc_enforced_pct`, `spf_without_dmarc_pct`, `dmarc_rua_pct`
- **Columns (vendors):** `table`, `cohort`, `gateway`, `domains`, `share_of_gateway_domains_pct`

Percentages are shares of the cohort's mail-receiving domains, rounded to one decimal place.

## Selling software to banks and credit unions?

These tables come out of Provena's own research into how financial institutions receive email. If you sell software or services to banks and credit unions, these guides use the same data to plan how you reach them:

- How fintech companies sell to financial institutions: https://www.provena-ai.com/blog/how-to-sell-fintech-to-financial-institutions
- Fintech and financial services lead generation agencies compared: https://www.provena-ai.com/blog/best-fintech-lead-generation-agencies

## Related

- [US car dealership email and website census](https://github.com/danielmcgrattan2007/us-car-dealership-census), the same method applied to 17,659 dealer domains.
- [All Provena research](https://www.provena-ai.com/research)

## Licence and citation

[CC BY 4.0](LICENSE). Reuse freely with credit to Provena and a link to the [study page](https://www.provena-ai.com/blog/bank-credit-union-email-census). See [`CITATION.cff`](CITATION.cff).
