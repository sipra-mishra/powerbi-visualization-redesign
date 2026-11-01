Visualisation Redesign: From Cluttered Pie Chart to Clear Bar Chart

📌 Executive Summary

This project demonstrates how applying core visual design principles can transform an ineffective, cluttered business visualization into a clear, actionable dashboard visual.

Using Microsoft Power BI Desktop, a 17-slice pie chart displaying sales revenue across product subcategories was redesigned into a descending-sorted horizontal bar chart. The redesign reduced time-to-insight from ~20 seconds to under 3 seconds and uncovered a key 80/20 revenue concentration pattern (Pareto principle) that was previously obscured.

🛠️ Tools & Dataset

BI Tool: Microsoft Power BI Desktop

Dataset: Sample Superstore Dataset (Kaggle)

Key Fields Analyzed: Sub-Category (Categorical) and Sales (Continuous)

🔍 The Problem (Before: 17-Slice Pie Chart)

The original visualization mapped total sales revenue across 17 distinct subcategories using a standard pie chart.

Identified Design Flaws:

Format-Data Mismatch: Pie charts are ineffective when comparing more than 2–5 categories. Evaluating 17 slices forces the viewer to judge subtle differences in slice areas and angles—tasks the human visual system performs poorly.

Visual Noise: 17 distinct color fills created distracting clutter without encoding any meaningful data.

Absence of Ranking: The categories appeared in arbitrary order, requiring manual back-and-forth comparison across slices to rank performance.

Label Overlap: Small slices (e.g., Fasteners at $3K) caused leader lines and percentage text to overlap, rendering low-volume categories unreadable.

✨ The Solution (After: Sorted Horizontal Bar Chart)

The visualization was rebuilt as a Horizontal Clustered Bar Chart applying perceptual accuracy and Gestalt principles:

Key Design Enhancements:

Perceptual Accuracy: Encoded sales values using bar length along an aligned common scale, enabling instant visual comparison.

Descending Sort: Sorted subcategories from highest to lowest sales, making ranking immediately visible without reading numerical labels.

Single Accent Color: Replaced the multi-color palette with a uniform blue fill to eliminate visual distraction.

Direct Data Labeling: Added exact values directly to the end of each bar formatted in thousands (K) for immediate readability.

📊 Feature Comparison Table

Design Aspect

Before (Pie Chart)

After (Horizontal Bar Chart)

Visual Encoding

Angles & Slice Areas

Position along Aligned Scale (Bar Length)

Category Sorting

Unsorted / Arbitrary Order

Sorted Descending by Sales Volume

Color Usage

17 Colors (Visual Noise)

Single Uniform Accent Blue

Data Labels

Overlapping Leader Lines

Direct End-of-Bar Labels (Formatted in $K)

Time-to-Insight

~15–20 Seconds

~2–3 Seconds

Self-Sufficiency

Low (Requires calculation)

High (Self-explanatory)

💡 Key Business Insights (Pareto 80/20 Analysis)

Beyond improving visual readability, the redesigned chart immediately highlighted a critical revenue pattern:

Sub-Category

Revenue ($K)

% of Total Sales

Cumulative %

Phones

$330K

14.4%

14.4%

Chairs

$328K

14.3%

28.7%

Storage

$224K

9.8%

38.5%

Tables

$207K

9.0%

47.5%

Binders

$203K

8.8%

56.3%

Machines

$189K

8.2%

64.5%

Accessories

$167K

7.3%

71.8%

Copiers

$150K

6.5%

78.3%

Remaining 9 Categories

$495K

21.7%

100.0%

Strategic Takeaway:

The 80/20 Rule: The top 8 out of 17 subcategories generate ~78.3% of total revenue.

Actionable Recommendation: Supply chain and marketing resources should focus primarily on maintaining inventory and promotion for these top 8 drivers. Low-volume subcategories (e.g., Fasteners at $3K) can be bundled or streamlined to optimize warehouse space.

📁 Repository Structure

├── Sample_Superstore.csv        # Source dataset file
├── Visualization_Redesign.pbix  # Power BI report file
├── screenshot.png               # Before vs. After dashboard preview
└── README.md                    # Project documentation


🚀 How to Run This Project

Clone or download this repository.

Open Visualization_Redesign.pbix using Microsoft Power BI Desktop.

(Optional) Re-link Sample_Superstore.csv if prompted during dataset refresh.
