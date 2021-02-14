---
title: "[2021-02-12] Don't repeat code"
date: 2021-02-12 22:26:28 -0400
categories: meeting codereview
---


1. Meeting(status call) 



* Eslint error

-> First writing

    <div onClick={() => setIsExpanded(!isExpanded)}>
      {!isExpanded ? <img className={styles.icon} src={upImg} alt="Up" /> : <img className={styles.icon} src={downImg} alt="Down" />}
    </div>

-> then, I got a eslint error like belorrow.

Visible, non-interactive elements with click handlers must have at least one keyboard listener     jsx-a11y/click-events-have-key-events



-> Solved!

    use <IconButton>contents</IconButton> instead of <div>contents</div>

    <IconButton onClick={() => setIsExpanded(!isExpanded)}>
      {!isExpanded ? <img className={styles.icon} src={upImg} alt="Up" /> : <img className={styles.icon} src={downImg} alt="Down" />}
    </IconButton>
	
	
* Tab

Original:


      const tabActive0 = clsx({ [styles.tabActive]: value === 0 });
      const tabActive1 = clsx({ [styles.tabActive]: value === 1 });
      const tabActive2 = clsx({ [styles.tabActive]: value === 2 });
      const tabActive3 = clsx({ [styles.tabActive]: value === 3 });

      <button type="button" onClick={() => handleClick(0)} className={clsx(styles.tab, tabActive0)}>Tab1</button>
      <span className={styles.tabBar}>|</span>
      <button type="button" onClick={() => handleClick(1)} className={clsx(styles.tab, tabActive1)}>Tab2</button>
      <span className={styles.tabBar}>|</span>
      <button type="button" onClick={() => handleClick(2)} className={clsx(styles.tab, tabActive2)}>Tab3</button>
      

Improved:


      const tabArray = [
        'Tab1',
        'Tab2',
        'Tab3'
      ];


       function renderTabWithIndex(tabName, index, tabs): React.ReactElement {
        const tabActive = clsx({ [styles.tabActive]: value === index });

        return (
          <span key={`tab-${tabName}`}>
            <button type="button" onClick={() => handleClick(index)} className={clsx(styles.tab, tabActive)}>{tabName}</button>
            {tabs.length - 1 !== index && <span className={styles.tabBar}>|</span>}
          </span>
        );
      }


      {tabArray.map((tabName, index, tabs) => (renderTabWithIndex(tabName, index, tabs)))}
  

-> I repeated the code in the original code, then it's improved by a guide from the team.



-----------------------------------------------------------



9:30-12:30(3hours)

13:30-14:00(30minutes) Meeting(Standup)

14:00-16:00(2hour)

16:00-16:40(40minutes) Meeting(status call)

16:40-18:40(2hours)
