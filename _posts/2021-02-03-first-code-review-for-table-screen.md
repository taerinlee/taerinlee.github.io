---
title: "[2021-02-03] first code review for table screen"
date: 2021-02-03 22:26:28 -0400
categories: meeting
---

1. Meeting(Status call)
Got reviewd code for table
* Point 1. Mind all border and row state, use Switch
  e.g.
  switch (index) {
      case 0:
        className = `${className} ${styles.rightDivider}`;
        rowSpan = 2;
        break;
      case 1:
        className = `${className} ${styles.rightDivider}`;
        columnSpan = 5;
        break;
      default:
        break;
    }
    
* Point 2. Looping for all row. e.g. total, summary, use Switch(Do not loop whole data area)
  e.g.
  switch (index) {
      case 11:
        classNameBundle = `${classNameBundle} ${styles.rightNone}`;
        break;
      default:
    }
    
* Point 3. Use <br /> tag for 2 row of column
  <div className={styles.summaryHeader} dangerouslySetInnerHTML={{ __html: status.place }} />
  
* Point 4. Use key value for looping column
  e.g.
  const keys = Object.keys(data[0]).filter((d) => d !== 'placeNmKor' && d !== 'placeNmEng') as tableHeaderKeys[];
  
  keys.map((item, i) => renderDataRowWithIndex(item, status, className, i))
  
  const renderDataRowWithIndex(item, status, className, i) {
    return (
      <div>status[item]</div>
    )
  }
  
  
Check out item #1 Don't Repeat Yourself (DRY) principle.
5 Essential Takeaways From “The Pragmatic Programmer” | by Jamie Bullock | Better Programming | Feb, 2021 | Medium

As I got advice mostly I need to keep not make same or similar code loop for table to show data row.normal data set row, total row, summary row, balance row, It will be many kind of row and some different kind of style for column or header as well. Important to figure out to make short the code, but do not repeat same code.

-----------------------------------------------------------


09:30-10:30(1hour) jira GSF-82

10:30-11:30(1hour) Organize communication tool(mail, chat, blog, git, drive, jira, figma)

11:30-13:30(2hour) jira GSF-93

13:30-14:00(30minutes) Meeting(Standup): jira GSF-82

14:00-16:00(2hour) jira GSF-93

16:00-16:40(40minutes) Metting(Status call)

16:40-18:40(2hour) jira GSF-82
