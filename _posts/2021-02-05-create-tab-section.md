---
title: "[2021-02-05] Create tab section"
date: 2021-02-05 22:26:28 -0400
categories: meeting
---

1. Meeting(Client)

Important thing is keep in mind about schedule of project and mount of screen

2. Meeting(Status call)

Task is making a tab in a page. First question was should I use open UI library or raw Html button.As current initial theme is material ui, I used from official website(https://material-ui.com/components/tabs/).


Style 1:  material ui tab components

Real button Html is inside several div, it was difficult to customizing design.


    function TabPanel(props: ITabPanelProps): React.ReactElement {
      const {
        children, value, index, ...other
      } = props;

      return (
        <div hidden={value !== index} {...other}>
          {
            value === index && (
              <div>{children}</div>
            )
          }
        </div>
      );
    }

    export default function TabComponent() {
    
      const [value, setValue] = React.useState(0);
      
      const handleChange = (event: React.ChangeEvent<unknown>, newValue: number):void => {
        setValue(newValue);
      };

      <Tabs value={value} onChange={handleChange}>
        <Tab label="Tab1" />
        <Tab label="Tab2" />
      </Tabs>
      
      
      <TabPanel value={value} index={0}>
        <TrendTable />
      </TabPanel>
      <TabPanel value={value} index={1}>
        <CurrentMonthTable />
      </TabPanel>
    }


Style 2: Raw Html Button

I only made two function, as this button only needs to data with  'useState'.
Add 'className={clsx(styles.tab, { [styles.tabActive]: value === 0 })}' to customazing design.

    
    function TabPanel(props: ITabPanelProps): React.ReactElement {
      const {
        children, value, index, ...other
      } = props;

      return (
        <div hidden={value !== index} {...other}>
          {
            value === index && (
              <div>{children}</div>
            )
          }
        </div>
      );
    }


    export default function TabComponent() {
      const [value, setValue] = React.useState(0);

      const handleClick = (newValue: number):void => {
        setValue(newValue);
      };

      <button type="button" onClick={() => handleClick(0)} className={clsx(styles.tab, { [styles.tabActive]: value === 0 })}>Tab1</button>
      <button type="button" onClick={() => handleClick(1)} className={clsx(styles.tab, { [styles.tabActive]: value === 1 })}>Tab2</button>

      <TabPanel value={value} index={0}>
        <TrendTable />
      </TabPanel>
      <TabPanel value={value} index={1}>
        <CurrentMonthTable />
      </TabPanel>
    }



GLADLY I have confirmed code in one time in merge request!!


-----------------------------------------------------------


7:30-11:30(4hour) jira GSF-83(Table Section)

11:30-12:00(30minutes) Organize communication tool(mail, chat, blog, git, drive, jira, figma)

12:00-13:30(1hour 30minutes) jira GSF-83(Tab Section)

13:30-14:00(30minutes) Meeting(Standup): jira GSF-82/GSF-93

14:00-15:00(1hour) jira GSF-83(Tab Section)

15:00-15:30(30minutes) Meeting(Client)

15:30-16:00(30minutes) jira GSF-83(Tab Section)

16:00-16:40(40minutes) Meeting(Status call)

16:40-20:40(2hours) jira GSF-83(Tab Section)
