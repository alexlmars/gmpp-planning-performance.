# GMPP Planning and Performance Reporting

**Status: In progress**

## Project purpose

Build a repeatable reporting process using published UK Government Major Projects Portfolio (GMPP) data to explore project costs, delivery confidence and portfolio changes.

This independent portfolio project develops skills relevant to planning and performance analysis: combining sources, checking data quality, defining consistent measures, building reports and documenting decisions.

It uses public government data and does not use internal Co-op data. It is not affiliated with or endorsed by Co-op or the UK Government.

## Initial scope

The first version covers two departments:

- Department for Work and Pensions (DWP)
- HM Revenue & Customs (HMRC)

It uses four departmental CSVs covering snapshots at **31 March 2023** and **31 March 2024**. These are snapshot dates, which can differ from publication dates.

This small scope allows the full workflow to be completed and explained before expanding it.

## Data sources and licence

The files come from the [GOV.UK major projects data collection](https://www.gov.uk/government/collections/major-projects-data):

- [DWP March 2023](https://www.gov.uk/government/publications/dwp-government-major-projects-portfolio-data-2023)
- [HMRC March 2023](https://www.gov.uk/government/publications/hmrc-government-major-projects-portfolio-data-2023)
- [DWP March 2024](https://www.gov.uk/government/publications/dwp-government-major-projects-portfolio-data-2024)
- [HMRC March 2024](https://www.gov.uk/government/publications/hmrc-government-major-projects-portfolio-data-2024)

Each publication page states that its content is available under the Open Government Licence v3.0, except where otherwise stated.

Source: DWP and HMRC, published on GOV.UK in support of Infrastructure and Projects Authority annual reporting. © Crown copyright.

Contains public sector information licensed under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).

Original downloads are preserved unchanged in `data/raw`.

## Planned workflow

1. Combine the source files using Excel Power Query, retaining source filenames and snapshot dates.
2. Profile data quality and document issues, affected records, handling decisions and fixes.
3. Create an Excel workbook with cleaned data, quality counts, lookup tables, a PivotTable and a data dictionary.
4. Build a Power BI star schema and documented DAX measures.
5. Create Overview, Department and Project Detail, and Data Quality report pages.
6. Independently recompute key results using pandas and reconcile them with Excel and Power BI.
7. Document refresh instructions, limitations and verified findings, and add report screenshots.

## Repository structure

- `data/raw`: untouched original downloads, organised by snapshot year
- `data/clean`: future cleaned exports
- `excel`: future Excel workbook
- `powerbi`: future Power BI report and screenshots
- `python`: future validation scripts
- `docs`: future data dictionary, source register and data quality log

## Progress

- [x] Select the initial departments and snapshot years
- [x] Download four original CSV files
- [ ] Build Power Query ingestion
- [ ] Complete data quality checks and Excel summaries
- [ ] Build the Power BI model and reports
- [ ] Validate results independently in Python
- [ ] Complete documentation and screenshots

## Limitations

This project covers a selected subset of the GMPP, not the entire portfolio.

Whole-life cost estimates are not annual spending. Unavailable or withheld values must not be treated as zero. Differences between snapshots may reflect portfolio membership, scope changes or revised estimates.

A project disappearing from a snapshot does not by itself prove completion or cancellation. Cross-year identifiers, cost comparability and rating definitions will be reviewed before drawing conclusions.