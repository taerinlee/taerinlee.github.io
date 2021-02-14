---
title: "[2021-02-10] Eslint error"
date: 2021-02-10 22:26:28 -0400
categories: meeting codereview
---



1. Meeting(Developer week call)

 Topic to discussion

 * suggested to make Global function by other developer

 * what kind of json will delivery might be issue to make table

 Tip from the team!

 * If I want to make a dynamic function, I can also return '<></>' in order to not return any data.
 
 


2. Meeting(status call) 

 * Eslint error
 
 When I made collapsible row in other demo project, It didnt make error with eslint.
 
 But When I worked on real project I met a eslint problem keyboard up/down react button need to make(even though I didnt mean to have the function), I need to care more web standard more.


 -> First writing

    <div onClick={() => setIsExpanded(!isExpanded)}>
      {!isExpanded ? <img className={styles.icon} src={upImg} alt="Up" /> : <img className={styles.icon} src={downImg} alt="Down" />}
    </div>

 -> then, I got a eslint error like belorrow.

    Visible, non-interactive elements with click handlers must have at least one keyboard listener     jsx-a11y/click-events-have-key-events


I need to solve it.


-----------------------------------------------------------



9:30-12:30(3hours) GSF-211 Rowspan in table body

13:30-14:00(30minutes) Meeting(Standup): jira GSF-211, GSF-212, GSF-87

14:00-14:40(40minutes) Meeting(Develper week call) 

14:40-16:00(1hour 20minutes) GSF-212

16:00-17:00(1hour) Meeting(status call)

17:00-18:30(1hour 30minutes) GSF-212
