---
title: "[2021-02-08] Time to think global function"
date: 2021-02-08 22:26:28 -0400
categories: meeting
---


1. Meeting(Status call)

Question 1: Material ui? Antd ui? Its up to component

It is table and tab component for now that I use, but I need to use select, switch, calendar soon.Select and Calendar made by team already. I can use it as they already made well.

There are some interaction I need to concern about table, collapsible row, modal with mouseHover.It is possible to make as raw table or UI library.

When I made collapsible row in other demo project, It didnt make error with eslint.

      {otherProps.index === 2 && <div onClick={() => setIsExpanded(!isExpanded)}>
        {isExpanded ? <img src={upImg} alt="Up" /> : <img src={downImg} alt="Down" />}
      </div>}

But When I worked on real project I met a eslint problem keyboard up/down react button need to make(even though I didnt mean to have the function), I need to care more web standard more.

Original source(https://codesandbox.io/s/expandable-table-row-material-ui-tr3ut?file=/demo.js) I had idea to make is Meterial UI also made KeyboardArrowDownIcon, KeyboardArrowUpIcon functions.

It will be other case I need to follow current eslint's rule I didnt explore yet, and there are some interactions left also, my team decided to consider other ui library for table.


* List

1. Raw table

2. Material UI table

3. Antd Ui table


* Module

1. Table

2. Switch

* Interaction

1. Collapsible row in table

2. Make modal when hover to data in table

3. switch data when clicked switch 


Question 2: Global functions?

I finished to make table for 3 times now. As I followed team's develop way, All function repeated 3 times as well in index.tsx.It is time to think to keep this way to develop or make global common functions.

I got answer that just keep current style in order to react faster to various screen from team.

        |--- src

        |     |-- components

        |     |-- tableA

        |           |-- dummydata.ts

        |           |-- index.tsx

        |           |-- styles.ts

        |     |-- views

        |     |-- viewA 

        |          |-- index.tsx
        |          |-- styles.ts



-----------------------------------------------------------



9:00-10:00(1hour) Organize communication tool(mail, chat, blog, git, jira)

10:00-12:30(2hours 30minutes) jira GSF-92

13:30-14:00(30minutes) Meeting(Standup): jira GSF-83, jira GSF-92

14:00-14:45(45minutes) Meeting(Sprint)

14:45-15:30(45minutes) Meeting(Sprint)

15:30-16:30(30minutes) Meeting(Status call)

16:30-17:30(1hour) Meeting(UI Interaction)

17:30-19:00(1hour 30minutes) jira GSF-92
