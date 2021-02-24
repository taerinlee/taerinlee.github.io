---
title: "[2021-02-22] Border in table component"
date: 2021-02-22 22:26:28 -0400
categories: codereview
---


1. Border in table component

* Original code

      let className = styles.dataRow;

      if (array.length - 1 === index) { 
        className = `${className} ${styles.bottomRow}`;
      }

      <td className={className}> column</td>
 


* Improved code

      <td className={clsx({ [styles.bottomRow]: x >= array.length - 1 })}column</td>
  
  
-> reason: It is for reduce redundant code generally.


** Need to change many place in each table components continue.


-----------------------------------------------------------


9:30-10:00 (30minutes) Meeting(All-hands Engineering)

10:00-12:30(2hours 30minutes) Bug fixes

13:30-14:00(30minutes) Meeting(Standup)

14:00-16:00(2hours) Meeting(sprint)

16:00-16:30(30minutes) Meeting(status)

16:30-18:30(2hours) Bug fixes(change local function to common component)
