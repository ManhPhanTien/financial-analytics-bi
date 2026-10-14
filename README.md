# [POWER BI] Analyze the 2023 Financial Performance of a Sports Company to Guide the 2024 Budget

## 1. Objective

### 1.1. What is this project about?

This project builds a 3-page Power BI dashboard from the 2023 profit and loss (P&L) data of a sports company with three business lines: Sportswear, Sports equipment, and Nutrition & Food Supplements. The raw data is a simple table of 580 monthly P&L records. The dashboard turns it into one clear P&L view, from revenue down to net profit, by month and by business line. Users can also look deeper into the costs behind the margins.

The work followed three steps:

1. Brainstorm with the Design Thinking canvas (Excel) before working with the data: who will use the dashboard, what they need, which questions it must answer and which charts belong on each page.
2. Build the dashboard in Power BI based on that plan.
3. Analyse the dashboard and turn the findings into recommendations.

### 1.2. Who is this project for?

- **CFO / Finance Director (main user):** responsible for the P&L and the 2024 budget, and needs one place to see profit, margin trends and the main costs.
- **CEO / Board:** decides which business line to grow, fix or close.
- **Heads of the three business lines:** responsible for their own revenue and cost targets, and want to compare their line with the others.
- **FP&A / cost controllers:** compare each month's results with the plan.

### 1.3. Business Questions

1. How much profit do we make, and where does each dollar of revenue go?
2. Which months perform poorly, and why?
3. Which business line makes money, and which loses money?
4. Which costs matter most, and do they change with revenue or stay the same?

### 1.4. Project Outcome

- **A 3-page interactive dashboard:**
  - Overview: are we on track?
  - Line: where is the problem?
  - Cost: why?
- **Answers to the four questions:**
  1. 2023 was profitable: \$17.56M revenue, \$4.31M net profit, a 24.6% net margin.
  2. Profit depends heavily on sales. In the weakest month, September, the net margin was only 8.2%, compared with 35.6% in January.
  3. Sportswear earns 63% of group profit from 39% of revenue. Nutrition & Food Supplements lost \$0.71M.
  4. People costs (Labor + Payroll) are half of all costs, and most costs barely go down when revenue falls.

## 2. Design Thinking Process

The canvas was filled in before the dashboard was built. It only shows what was known at that time: the users, their needs, the structure of the raw data, the questions and ideas to test, and the planned pages and metrics. The results come later, in sections 4 and 5.

### Stage 1: Empathize

- **5W1H:** 
![5W1H](images/5w1h.png)

- **Empathy Map:** 
![Empathy Map](images/empathy_map.png)

### Stage 2: POV

One main question per page. For each page, the table lists the planned charts and the business questions they answer.

![POV](images/pov.png)

### Stage 3: Ideate

The metrics planned for each page, from the main KPIs (Layer 0) to more detailed breakdowns (Layers 1 and 2).

![Ideate](images/ideate.png)

## 3. Data Modeling

The raw CSV files were loaded into Power BI, cleaned in Power Query and organised as a star schema (one fact table linked to several dimension tables).

![Data Model](images/04_data_model.png)

## 4. Key Insights & Visualizations

All figures are for 2023, in USD, based on the source data as recorded.

### 4.1. Overview: Are we on track?

![Overview](images/01_overview.png)

- **Profitable year, but costs are high.**
  - Revenue of \$17.56M became \$10.85M of gross profit (61.8%), \$5.24M of EBIT (29.9%) and \$4.31M of net profit (24.6%).
  - Out of every \$1 of revenue, 38¢ goes to COGS, 32¢ to Opex and 5¢ to interest & tax.
  - For a company that sells physical products, COGS is usually much bigger than Opex. Here they are almost the same size, which suggests a large base of fixed costs such as staff, equipment and rent. The Cost page confirms this.
- **Profit moves much more than revenue.**
  - From January (best month) to September (worst month), revenue fell 42% (\$1.95M → \$1.12M), but net profit fell 87% (\$694.5K → \$91.6K). Net margin dropped from 35.6% to 8.2%.
  - Over the year, costs changed by only about 28¢ for every \$1 change in revenue. So each \$1 of lost sales cut net profit by about 64¢.
  - This is common for companies with their own staff, equipment and rented space: when sales grow, profit grows fast; when sales slow down, profit falls fast.
- **Sales follow the seasons, and the second half was weaker.**
  - Revenue is highest in January, May–June and December, and lowest in April and September. This matches the usual pattern for sports products: New Year fitness goals, the summer season and holiday gifts.
  - H2 revenue was 13% lower than H1, but H2 net profit was 36% lower, because costs fell only 3%.
  - The raw data shows that much of the H2 drop came from consulting income (−39%), not product sales (−6.5%). With only one year of data, this seasonal pattern should be checked before using it for the budget.
- **September: revenue fell, but costs did not.**
  - Revenue fell 14.1% MoM, while COGS fell only 2.0% and Opex rose 1.2%. As a result, COGS rose to 47.8% of revenue (from 41.9% in August).
  - Net profit dropped 66% to \$91.6K. Sports equipment caused most of this drop (−\$143K) and had its only loss-making month.
  - On the MoM chart the lines look close together, so the problem is easy to miss; it only shows in the margin. A chart of COGS as a % of revenue would make it clear.
- **MoM % can be misleading.**
  - October's "+222%" net profit only brought profit back to \$295K, close to August's level (\$269K). A big % change on a small base looks more dramatic than it is.
  - The KPI cards show margin changes as a % of the old margin. The EBIT margin's "+80%" is really a move from 20.5% to 37.0%, or +16.4 pp.

### 4.2. Line: Where is the problem?

![Line](images/02_business_line.png)

- **Sportswear brings in most of the profit.**
  - It makes 38.8% of revenue but \$2.74M of net profit, 63.4% of the group's profit.
  - It has the best margins at every level (gross 70.3%, EBIT 45.7%, net 40.2%) and made a profit every month, with a net margin of 29%–51%.
  - Clothing brands can often charge higher prices. Sportswear also spends less on labour: 20% of revenue, compared with 27% for Sports equipment.
- **Sports equipment is the biggest line, but less efficient.**
  - It makes 50.7% of revenue (\$8.91M) and \$2.29M of net profit, a 25.7% net margin.
  - Its gross margin is 11.6 pp lower than Sportswear's. Compared with Sportswear, it spends more of its revenue on labour (+6.9 pp), on the "Sales" cost line (+2.4 pp) and on shipping (+1.8 pp, mostly from one \$130K entry in January). Materials cost about the same share.
  - Equipment is large and heavy, and is often sold to gyms, schools and clubs, which adds handling, delivery and sales commission costs. So the way to improve is to work more efficiently and lower selling costs, not to buy materials more cheaply.
- **Sports equipment is also hit hardest in weak months.**
  - Its gross margin fell from 54.3% in August to 42.7% in September, with a \$15.1K net loss, its only loss of the year.
  - Its H2 revenue was 14% lower than H1, but its H2 net profit was 41% lower.
  - Its labour cost rose 30% for the summer (\$180K → \$234K a month) and only came back down to \$200K. So when sales dropped in the autumn, costs were still higher than at the start of the year.
- **Nutrition & Food Supplements loses money: −\$0.71M.**
  - Its gross margin is positive (44.8%), but Opex takes 75.7% of its revenue, compared with 24.6% for Sportswear and 28.4% for Sports equipment. Its EBIT margin is −30.9% and its net margin −38.7%.
  - Its biggest costs are Payroll (24.3% of revenue), R&D (19.5%) and Marketing (14.4%). It carries two-thirds of the group's R&D cost but brings in only 10.5% of revenue.
  - It lost money in 11 of 12 months, so this is a long-term problem, not one bad month. It looks like a young supplement brand that spends heavily on R&D and marketing before sales grow. But its sales did not grow: H2 revenue was about the same as H1.
- **Closing Nutrition would not simply add \$0.71M to profit.**
  - Its gross profit covers its own payroll, marketing and other Opex, with about \$0.10M left over.
  - The loss comes from R&D (\$0.36M) and from equipment, rent and interest & tax (\$0.45M). Some of these costs may be shared with the other lines and would not go away.
  - Depending on which costs would really disappear, closing it would change group profit by between −\$0.10M and +\$0.71M. To break even, it would need 69% more revenue or 41% less Opex.

### 4.3. Cost: Why?

![Cost](images/03_cost.png)

- **People are the biggest cost.**
  - Labor is about two-thirds of COGS. Payroll (31.9%), Equipment (23.8%) and Marketing (18.8%) together make up 74.5% of Opex.
  - Labor + Payroll = \$6.28M, 51% of all costs, while materials are only \$1.07M (6.1% of revenue).
  - Cutting labour cost by 10% would save about \$0.45M, compared with \$0.11M for materials. So better staff planning matters more than buying more cheaply.
- **COGS follows staff levels, not sales.**
  - In most months, COGS hardly changes when revenue changes. In March, revenue fell 16.2% while COGS rose 1.3%; in December, revenue rose 35.4% while COGS rose only 3.4%.
  - The exception is May (COGS +32.9%), when labour was increased by 24% for the summer (\$345K → \$429K a month). It was still \$380K in August–September.
  - January (\$1.95M) and December (\$1.73M) reached the same or higher revenue with the normal team, so the extra staff may not have been needed. Seasonal businesses usually hire temporary staff for busy periods.
- **Opex stays high and keeps rising.**
  - Opex barely changes with revenue (in February, revenue fell 19.6% while Opex rose 0.8%) and was highest in December (\$536.8K).
  - Rent rose 48% and equipment 33% during 2023, while H2 revenue fell 13%. Rent and equipment contracts are hard to cancel once signed.
  - Marketing is the only cost that goes up and down with the season (\$120K in busy months, \$50K–65K in slow months). So the charts cannot show whether marketing creates sales or just follows them.
- **Data check: the COGS Pareto chart is missing some costs.**
  - The bars add up to about \$6.45M, but total COGS is \$6.71M. The missing \$0.26M is "Other" COGS, which the Subgroup table puts under Opex.
  - Because of this, Labor shows as 69.7% of COGS instead of the correct 66.9%.
  - Two records also look like they have an extra zero: Sports equipment shipping in January (\$130K) and Nutrition consulting in August (\$90K).

## 5. Final Conclusion & Recommendation

2023 was profitable (24.6% net margin), but the profit is not stable:

- It depends on two business lines, Sportswear and Sports equipment, while Nutrition & Food Supplements loses money.
- Most costs are fixed, so a drop in sales leads to a much bigger drop in profit.
- Fixed costs (rent, equipment, summer staff) kept rising while H2 revenue fell.

| Aspect | Insight | Recommendation |
|---|---|---|
| **Profit sensitivity** | Each \$1 of lost revenue cut profit by about 64¢. From January to September, revenue fell 42% and net profit fell 87%. The estimated break-even point is about \$0.9M of revenue per month. | Check the break-even point every month. Plan the 2024 budget with a "bad month" scenario (like September) and decide in advance which costs to cut. |
| **Nutrition & Food Supplements** | Lost \$0.71M and made a loss in 11 of 12 months. Opex is 75.7% of its revenue. The loss comes from R&D and from equipment, rent and interest costs that may be shared with other lines. | Find out which costs would really go away if the line closed, and set a deadline for R&D to show results. Limit R&D and marketing to a fixed % of revenue and give the line 2 quarters to improve. If it does not improve and the costs can be removed, cut the product range or close the line. |
| **Sportswear** | Brings 63.4% of profit from 38.8% of revenue, with the best margins (40.2% net) and no loss-making month. | Give it priority for the growth budget and for stock in busy seasons. Grow with tested campaigns instead of discounts that would lower its margin. |
| **Sports equipment** | Makes half of revenue, but its gross margin is 11.6 pp lower than Sportswear's because of labour (+6.9 pp) and selling costs (+2.4 pp), not materials. It made a loss in September. | Review staff productivity and work schedules. Check what the "Sales" cost line pays for, and link sales commissions to profit instead of sales volume. |
| **Labour & staffing** | Labor + Payroll are 51% of costs. Labour was increased 24% for the summer and reduced slowly, while the January and December peaks used the normal team. | Use temporary or contract staff for busy months and end their contracts when demand drops. Track revenue per \$1 of labour every month for each line. |
| **Fixed costs** | Rent rose 48% and equipment 33% in 2023, and Opex was highest in December. H2 costs fell only 3% while revenue fell 13%. | Do not add new fixed costs in 2024 unless there is a clear plan for how they will pay off. Check whether all equipment and space are really being used. |
| **Revenue planning & marketing** | Sales are highest in January, May–June and December. Much of the H2 drop came from consulting (−39%). Marketing spending follows the season, so it is unclear whether it brings extra sales. | Plan product sales around the seasons, and plan consulting income from signed contracts. Add data from previous years, and test marketing in small trials before increasing the budget. |
| **Dashboard & data quality** | The Pareto chart misses \$0.26M of "Other" COGS, margin MoM is shown as % instead of pp, the NP Margin card has the wrong label, and two records look like typos (\$130K and \$90K). | Create a separate "Other COGS" account, check the two records with the accounting team, show margin changes in pp and fix the card label. Next, add COGS and Opex as % of revenue, revenue by type (products, consulting, other income), a year-over-year comparison and budget vs actual. |
