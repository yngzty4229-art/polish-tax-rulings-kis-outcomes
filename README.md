# Polish Tax Rulings (KIS) with Outcomes

2,206 official Polish tax rulings labeled correct/incorrect, Sep–Oct 2026.

Also on Kaggle: https://www.kaggle.com/datasets/krzysztoffilipiak/polish-tax-rulings-kis-outcomes

Data file: `polish_tax_rulings_2026_09_28_to_10_25.csv.gz` (gzip-compressed CSV, UTF-8).

Official **individual tax interpretations** issued by the Polish National Tax Information (KIS) and published in the Ministry of Finance's **EUREKA** database between 28 September and 25 October 2026 (2,206 documents), with an automatically detected **outcome**: was the taxpayer's position correct?

**Use it for:** predicting the outcome from the facts and the taxpayer's position (legal NLP in Polish), evaluating RAG pipelines and AI assistants on Polish tax law, or analysing which positions the tax authority accepts.

### Columns
| column | meaning |
|---|---|
| id, url | EUREKA document id and link to the official text |
| signature | case signature (sygnatura), e.g. 0114-KDIP4-2.4012.626.2026.3.MC |
| tax | tax area from the signature code: VAT, PIT, CIT, PCC, inheritance and gift tax (spadki i darowizny), excise (akcyza), other (inne) |
| issue_date, publication_date | when KIS issued the ruling and when it appeared in EUREKA |
| issuing_authority | issuing authority (usually Dyrektor Krajowej Informacji Skarbowej) |
| thesis | official one-sentence summary (teza) |
| outcome, outcome_sentence | correct / incorrect / partly-correct / refusal (empty when not detected) and the sentence it comes from |
| question, facts, applicant_position | the taxpayer's question, the facts and the taxpayer's own position (in Polish, up to 6,000 characters each) |

### Labels
correct (stanowisko prawidłowe) 67% · incorrect (nieprawidłowe) 22% · partly-correct (w części prawidłowe) 11% · other or not detected 0%.
Outcomes are detected automatically from the authority's assessment – check `outcome_sentence` before relying on a label.

### Source and license
Data from [EUREKA](https://eureka.mf.gov.pl), the public database of the Ministry of Finance of Poland. Official documents are not protected by copyright in Poland (art. 4 of the Copyright Act); the Ministry anonymises them before publication. This compilation is released under CC BY 4.0. Not affiliated with the Ministry of Finance.

### Full and fresh data
This is a sample. All 560,000+ EUREKA documents (including binding VAT rate information – WIS), full text in Markdown and live search by phrase or signature are available as an API on Apify: https://apify.com/kris_fili/poland-tax-interpretations – it also works from Claude, ChatGPT or Cursor through the Apify MCP server.
