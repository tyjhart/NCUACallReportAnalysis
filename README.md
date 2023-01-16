# NCUA Call Report Analysis

Hopefully my analysis can be helpful for you as well. If you have any questions or would like to use my analysis or images in your own reports, feel free to reach out to me using info in the [Contact](#Contact) section.

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

## Data Notes
Raw Call Report data is sourced from the NCUA.gov website. It's then filtered down a bit so numbers match up with NCUA summary reports. Only CU types 1 and 2 are included in my analysis, since the NCUA doesn't include non-Federally Insured organizations in theirs. Data is also filtered by asset value to exclude outliers when making visualizations. Very large credit unions like Navy Federal and others skew things quite a bit - there's simply no good comparison to be made unless you're also a massive institution. Any credit union whose assets (ACCT_010) have a Z-score greater than 3 are generally filtered out of visualizations. Refer to footnotes and subtitles for additional filtering information.

## Background

In early 2022 I took a job with a credit union, the first time I'd ever worked for that kind of financial institution before. The compensation was fair, people seemed great, and the CU passed the smell test when I researched it during the interview process. But after settling in to my new role I realized that I didn't have a great feel for the position of the CU within the greater ecosystem. I knew our asset value, member count, number of branches, etc. but had no idea where we ranked against others in our area. Did we have more delinquent loans than the credit union down the street? Had we made meaningful gains in member count? Did our rations meet or exceed what the regulators expected? I had no idea, and that's the origin of this project.

The NCUA's FRP tool is great but it doesn't give me kind of comparative analysis I want to see. It's also pretty light on visualizations that help me understand data better. So I downloaded raw Call Report data, pulled it into R and started the process of analyzing and visualizing the data. The images and data below are what I use to determine where my credit union is at in the industry. It helps me have better conversations with our senior leaders, Board members, and examiners from the NCUA and DFI. It lets me feel good about investing my time and talents in an organization because I can see we're headed in the right direction.

## License

The contents of this project is copyrighted 2023 by Tyler Hart, all rights reserved. See [the license file](./LICENSE.md) for more information.

## Contact
Feel free to contact me about this project at tyler[@]manitonetworks.com. Please include "NCUA" or "Call Report" somewhere in the subject line.
