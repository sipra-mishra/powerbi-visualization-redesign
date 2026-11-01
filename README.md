# Visualization Redesign: From a Cluttered Pie Chart to a Clear Bar Chart

A Power BI project that redesigns a 17-slice pie chart of sales by product sub-category into a sorted horizontal bar chart. The clearer chart shows that **8 of 17 sub-categories generate 78.3% of total sales**.

## Before and after

**Before: cluttered pie chart (17 slices)**

![Before: cluttered pie chart](Before%20Chart%20%28Cluttered%20Pie%20Chart%29.png)

**After: sorted horizontal bar chart**

![After: sorted horizontal bar chart](After%20Chart%20%28Sorted%2C%20Clean%20Horizontal%20Bar%20Chart%29.png)

## Project context
Built as part of my MBA (Business Analytics) capstone, using the "Visualization Redesign" problem from the Coursera course *Data Visualization Capstone* (Johns Hopkins University).

- **Tool:** Microsoft Power BI Desktop
- **Dataset:** Sample Superstore (Kaggle), 9,994 rows and 13 columns
- **Fields used:** Sub-Category (17 categories) and Sales

## The problem (before)
- **Too many slices:** pies are reliable for roughly 2 to 5 categories, and 17 slices are hard to compare by angle and area.
- **Visual noise:** 17 colors that carry no extra meaning.
- **No ranking:** categories appear in arbitrary order.
- **Unreadable labels:** small slices such as Fasteners ($3K) have overlapping leader lines.

## The solution (after)
- **Bar length on a common scale:** the easiest way to compare many categories accurately.
- **Descending sort:** the ranking is visible without reading any numbers.
- **One accent color:** removes the legend and the clutter.
- **Direct labels:** exact values at the end of each bar, formatted in thousands (K).

## Design comparison

| Aspect | Before (pie chart) | After (bar chart) |
|---|---|---|
| Visual encoding | Angles and slice areas | Bar length on an aligned scale |
| Sorting | Arbitrary order | Descending by sales |
| Colors | 17 colors with no meaning | One accent blue |
| Labels | Overlapping leader lines | Direct end-of-bar labels |
| Time to rank the top 3 (estimated*) | ~15-20 seconds | ~2-3 seconds |

*Informal self-timed test, not a controlled usability study.

## Key insight: the 80/20 pattern
Total sales are about $2.30M. The top 8 of 17 sub-categories contribute about $1.80M (78.3%). The bottom 5 (Supplies, Art, Envelopes, Labels, Fasteners) contribute only 4.6%.

| Sub-Category | Sales ($K) | % of total | Cumulative % |
|---|---|---|---|
| Phones | 330 | 14.4% | 14.4% |
| Chairs | 328 | 14.3% | 28.7% |
| Storage | 224 | 9.7% | 38.4% |
| Tables | 207 | 9.0% | 47.4% |
| Binders | 203 | 8.9% | 56.3% |
| Machines | 189 | 8.2% | 64.5% |
| Accessories | 167 | 7.3% | 71.8% |
| Copiers | 150 | 6.5% | 78.3% |
| Other 9 sub-categories | 498 | 21.7% | 100.0% |

**Takeaway:** inventory and promotion effort can focus on the top sales drivers, and the lowest-selling sub-categories can be bundled or carried in smaller quantities.

**Caveat:** this view uses sales only. In this dataset, Tables (4th by sales) has a negative total profit (about -$17.7K), as do Bookcases and Supplies. Profit should be checked before deciding where to focus.

## What I did
1. Imported the Superstore CSV into Power BI and checked the data types.
2. Built the original pie chart (Sub-Category as legend, Sum of Sales as values).
3. Documented its design problems.
4. Rebuilt it as a horizontal bar chart, sorted descending.
5. Applied a single color and direct data labels.
6. Compared both charts and calculated the cumulative (Pareto) contribution.

## Limitations
- The reading-time comparison was a self-test, not a study with other people.
- Only one category field (Sub-Category) was compared against one measure (Sales).
- Results reflect Power BI's default chart rendering.

## Repository contents
- `Visualization_Redesign_Capstone.pbix`: the Power BI report
- `SampleSuperstore.csv`: source dataset
- `Before Chart (Cluttered Pie Chart).png` and `After Chart (Sorted, Clean Horizontal Bar Chart).png`: chart screenshots

## How to open
Download the repository, open `Visualization_Redesign_Capstone.pbix` in Power BI Desktop, and re-link `SampleSuperstore.csv` if Power BI asks for the data source.

## Future work
- Add profit and compare it with sales for each sub-category
- Break the analysis down by region and segment
- Build an interactive drill-down dashboard
- Test the two charts with a small group of people
- Check the color scheme for color-blind readers
