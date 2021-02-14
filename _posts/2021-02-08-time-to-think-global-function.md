---
title: "[2021-02-08] Time to think global function"
date: 2021-02-08 22:26:28 -0400
categories: meeting
---


1. Meeting(Status call)



Question 1: Material ui? Antd ui? Its up to component
 

It is a table and tab component for now that I use, but I need to use select, switch, calendar soon. Select and Calendar made by the team already. I can use it as they already made it well.

There are some interactions I need to make a collapsible table, modal with mouseHover on data in table. It is possible to make a raw table or UI library as well.

As the current project uses Material ui as the main theme, ant ui for each component, I need to figure out what would be good for the table as well.




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
