# NCUA Call Report Analysis

This project is my attempt to understand the credit union system - of which I'm now both member and employee - better. Find more information about that in the [Project Background](#Project-Background) section. Over time I might spin up a newsletter on Substack with more detailed analysis. Most of the analysis in this project is performed using R and RStudio. 

If you have any questions or would like to use my analysis or images in your own reports, feel free to reach out to me using info in the [Contact](#Contact) section.

## Overview

To better understand the credit union system I'm analyzing [Members](#Members), [Assets](#Assets), and [Ratios](#Ratios) right now. Analysis of [Loans](#Loans) is something I'll get to in the future as well.

## Assets

Dollars continue to flow into the credit union system.

![](./Figures/plot.TotalAssetsOverTime.png)

The majority of asset growth in the system has been happening in peer group 6:

![](./Figures/plot.TotalAssetsOverTimeByPeer.png)

Filtering out peer group 6 gives additional context for groups 1-5:

![](./Figures/plot.TotalAssetsOverTimeByPeerNoSix.png)

Assets continue flowing into groups 1-4, albeit at a much more sedate rate than groups 5 and 6:

![](./Figures/plot.TotalAssetsOverTimeByRegion.png)



## Members

Membership continues to grow overall within the credit union system:
![](./Figures/plot.MembersOverTime.png)

The rate of growth is fairly steady at about 1% per-cycle ([table](./Tables/MemberCountByCycle.md)): 

|Cycle      |Members     |Percentage Change |
|:----------|:-----------|:-----------------|
|2017-03-31 |109,384,648 |NA%               |
|2017-06-30 |110,636,772 |1.14%             |
|2017-09-30 |111,860,849 |1.11%             |
|2017-12-31 |112,657,493 |0.71%             |
|2018-03-31 |114,054,672 |1.24%             |
|2018-06-30 |115,377,804 |1.16%             |
|2018-09-30 |116,758,943 |1.2%              |
|2018-12-31 |117,552,551 |0.68%             |
|2019-03-31 |118,656,887 |0.94%             |
|2019-06-30 |119,700,948 |0.88%             |
|2019-09-30 |120,943,833 |1.04%             |
|2019-12-31 |121,746,941 |0.66%             |
|2020-03-31 |122,739,428 |0.82%             |
|2020-06-30 |123,695,931 |0.78%             |
|2020-09-30 |125,115,562 |1.15%             |
|2020-12-31 |125,695,985 |0.46%             |
|2021-03-31 |127,098,933 |1.12%             |
|2021-06-30 |128,584,248 |1.17%             |
|2021-09-30 |130,026,066 |1.12%             |
|2021-12-31 |130,952,969 |0.71%             |
|2022-03-31 |132,311,173 |1.04%             |
|2022-06-30 |133,919,345 |1.22%             |
|2022-09-30 |135,654,038 |1.3%              |

However, that growth is not evenly distributed between peer groups. Most growth is happening in peer group six. The long-term trend for peer groups 1-5 is small or negative member growth.

![](./Figures/plot.MembersOverTimeByPeer.png)

Filtering out peer group 6 gives some context:

![](./Figures/plot.MembersOverTimeByPeerNoSix.png)

Filtering out peer groups 5 and 6 shows the decline of members in 1-4 in better detail:

![](./Figures/plot.MembersOverTimeByPeerNoFiveSix.png)

Region 8, where the largest of peer group 6 credit unions are located, sees the most growth overall.

![](./Figures/plot.MembersOverTimeByRegion.png)

## Ratios

* [Assets to Members](#Assets-to-Members)
* [Assets to Employees](#Assets-to-Employees)
* [Members to Employees](#Members-to-Employees)

### Assets to Members
This ratio uses account codes ACCT_010 for assets and ACCT_083 for member headcount. View a table of [assets to members by peer group and region](./Tables/AssetsToMembersByPeerRegion.md). There's separate tables for assets to members by both [peer group](./Tables/AssetsToMembersByPeerGroup.md) and [CU region](./Tables/AssetsToMembersByRegion.md) as well.

![](./Figures/plot.AssetsToMembers.png)

### Assets to Employees
This ratio uses accounts ACCT_010 for assets and (ACCT_564A + (564B / 2)) for employee headcount.

![](./Figures/plot.AssetsToEmployees.png)

### Members to Employees
This ratio uses accounts (ACCT_564A + (564B / 2)) for employee headcount and ACCT_083 for member headcount.

![](./Figures/plot.MembersToEmployees.png)

## Loans

Working on it!

### Auto Loans

Vroom-vroom!

New vehicle loans over time:
![](./Figures/plot.AmountNewVehLoansOverTime.png)

By peer group:
![](./Figures/plot.AmountNewVehLoansOverTimeByPeer.png)

By region:
![](./Figures/plot.AmountNewVehLoansOverTimeByRegion.png)


### Payday Loans

Still working on it!

## Data Notes
Raw Call Report data is sourced from the NCUA.gov website. It's then filtered down a bit so numbers match up with NCUA summary reports. Only CU types 1 and 2 are included in my analysis, since the NCUA doesn't include non-Federally Insured organizations in theirs. Data is also filtered by asset value to exclude outliers when making visualizations. Very large credit unions like Navy Federal and others skew things quite a bit - there's simply no good comparison to be made unless you're also a massive institution. Any credit union whose assets (ACCT_010) have a Z-score greater than 3 are generally filtered out of visualizations. Refer to footnotes and subtitles for additional filtering information.

## Project Background

In early 2022 I took a job with a credit union, the first time I'd ever worked for that kind of financial institution before. The compensation was fair, people seemed great, and the CU passed the smell test when I researched it during the interview process. But after settling in to my new role I realized that I didn't have a great feel for the position of the CU within the greater ecosystem. I knew our asset value, member count, number of branches, etc. but had no idea where we ranked against others in our area. Did we have more delinquent loans than the credit union down the street? Had we made meaningful gains in member count? Did our rations meet or exceed what the regulators expected? I had no idea, and that's the origin of this project.

The NCUA's FRP tool is great but it doesn't give me kind of comparative analysis I want to see. It's also pretty light on visualizations that help me understand data better. So I downloaded raw Call Report data, pulled it into R and started the process of analyzing and visualizing the data. The images and data below are what I use to determine where my credit union is at in the industry. It helps me have better conversations with our senior leaders, Board members, and examiners from the NCUA and DFI. It lets me feel good about investing my time and talents in an organization because I can see we're headed in the right direction.

## License

The contents of this project is copyrighted 2023 by Tyler Hart, all rights reserved. See [the license file](./LICENSE.md) for more information.

## Contact
Feel free to contact me about this project at tyler[@]manitonetworks.com. Please include "NCUA" or "Call Report" somewhere in the subject line.
