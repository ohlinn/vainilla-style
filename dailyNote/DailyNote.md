## Templater
- My Title format: 'YY-MM-DD'
- Manually replace the {{}} text with your template of your periodic notes. 

| Replace this  |   with your personalized template as usual. Example:|
|-|-|
|{{yourMonth}}  |`<% moment(tp.file.title,'YY-MM-DD').format('YY-MM-00') %>`      |
|{{yourWeek}}   |`<% moment(tp.file.title,'YY-MM-DD').format('YY-[w]ww') %>`      |
|{{yourQuarter}}|`<% moment(tp.file.title,'YY-MM-DD').format('YY-[Q]Q') %>` |
|{{yourYear}}   |`<% moment(tp.file.title,'YY-MM-DD').format('YYYY') %>`          |
|{{yourPrevD}}  |`<% moment(tp.file.title,'YY-MM-DD').subtract(1,'d').format('YY-MM-DD') %>`     |
|{{yourNextD}}  |`<% moment(tp.file.title,'YY-MM-DD').add(1,'d').format('YY-MM-DD') %>`      |

### HTML Templater
```
<div class='daily'>
<div class='todayday'>
    <% <% moment(tp.file.title,'YY-MM-DD').format('dddd DD') %></div>
<div class='todaymonth'>
    ෴<% moment(tp.file.title,'YY-MM-DD').format('MMMM YYYY') %>෴</div>
</div>
<div class='bars'>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='{{yourWeek}}.md'>
            week <% moment(tp.file.title,'YY-MM-DD').format('ww') %></a>
    </div>
    <div class='left'><a class='internal-link' id='small-link'
            href='{{yourPrevD}}.md'>yesterday</a>
        🟊 <a class='internal-link' id='small-link'
            href='{{yourNextD}}.md'>tomorrow</a>
    </div>
    <progress value='<% moment(tp.file.title, 'YY-MM-DD').isoWeekday() %>' max='7'>
</div>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='{{yourMonth}}.md'><% moment(tp.file.title,'YY-MM-DD').format('MMMM') %></a>
    </div>
    <div class='left'>🝮
        <% moment(moment(tp.file.title, 'YY-MM-DD').endOf('month')).diff(moment(tp.file.title, 'YY-MM-DD'), 'days') %>
        days left</div>
    <progress value='<% moment(tp.file.title,'YY-MM-DD').format('DD') %>'
        max='<% moment(tp.file.title, 'YY-MM-DD').daysInMonth() %>'>
</div>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='{{yourQuarter}}.md'><% moment(tp.file.title,'YY-MM-DD').format('Qo [quarter]') %></a>
    </div>
    <div class='left'>🝮
        <% moment(moment(tp.file.title, 'YY-MM-DD').endOf('quarter')).diff(moment(tp.file.title,'YY-MM-DD'),'days')  %> days left</div>
    <progress value='<% moment(tp.file.title,'YY-MM-DD').diff(moment(tp.file.title, 'YY-MM-DD').startOf('quarter'),'days')  %>'
        max='<% moment(moment(tp.file.title, 'YY-MM-DD').endOf('quarter')).diff(moment(moment(tp.file.title,'YY-MM-DD').startOf('quarter')), 'days')  %>'>
</div>
<div class='bars-progres'>
    <div class='time'><a class='internal-link' id='big-link'
            href='{{yourYear}}.md'>Day
            #<% moment(tp.file.title, 'YY-MM-DD').dayOfYear() %></a></div>
    <div class='left'>🝮
        <% moment(moment(tp.file.title, 'YY-MM-DD').endOf('year')).diff(moment(tp.file.title, 'YY-MM-DD'), 'days') %>
        days left</div>
    <progress value='<% moment(tp.file.title, 'YY-MM-DD').dayOfYear() %>' max='<% moment(moment(tp.file.title,'YY-MM-DD').endOf('year')).diff(moment(tp.file.title,'YY-MM-DD').startOf('year'),'days') %>'>
</div></div>
```

### Mine
```<div class='daily'>
<div class='todayday'>
    <% moment(tp.file.title,'YY-MM-DD').format('dddd DD') %></div>
<div class='todaymonth'>
    ෴<% moment(tp.file.title,'YY-MM-DD').format('MMMM YYYY') %>෴</div>
</div>
<div class='bars'>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='<% moment(tp.file.title,'YY-MM-DD').format('YY-[w]ww') %>.md'>
            week <% moment(tp.file.title,'YY-MM-DD').format('ww') %></a>
    </div>
    <div class='left'><a class='internal-link' id='small-link'
            href='<% moment(tp.file.title,'YY-MM-DD').subtract(1,'d').format('YY-MM-DD') %>.md'>yesterday</a>
        🟊 <a class='internal-link' id='small-link'
            href='<% moment(tp.file.title,'YY-MM-DD').add(1,'d').format('YY-MM-DD') %>.md'>tomorrow</a>
    </div>
    <progress value='<% moment(tp.file.title, 'YY-MM-DD').isoWeekday() %>' max='7'>
</div>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='<% moment(tp.file.title,'YY-MM-DD').format('YY-MM-00') %>.md'>
            <% moment(tp.file.title,'YY-MM-DD').format('MMMM') %></a>
    </div>
    <div class='left'>🝮
        <% moment(moment(tp.file.title, 'YY-MM-DD').endOf('month')).diff(moment(tp.file.title, 'YY-MM-DD'), 'days') %>
        days left</div>
    <progress value='<% moment(tp.file.title,'YY-MM-DD').format('DD') %>'
        max='<% moment(tp.file.title, 'YY-MM-DD').daysInMonth() %>'>
</div>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='<% moment(tp.file.title,'YY-MM-DD').format('YY-[Q]Q') %>.md'><% moment(tp.file.title,'YY-MM-DD').format('Qo [quarter]') %></a>
    </div>
    <div class='left'>🝮
        <% moment(moment('21-09-30', 'YY-MM-DD')).diff(moment(tp.file.title, 'YY-MM-DD'), 'days') %> days left</div>
    <progress value='<% moment(moment(tp.file.title, 'YY-MM-DD')).diff(moment('21-06-30', 'YY-MM-DD'), 'days') %>'
        max='<% moment(moment('21-09-30', 'YY-MM-DD')).diff(moment('21-06-30', 'YY-MM-DD'), 'days') %>'>
</div>
<div class='bars-progres'>
    <div class='time'><a class='internal-link' id='big-link'
            href='<% moment(tp.file.title,'YY-MM-DD').format('YYYY') %>.md'>Day
            #<% moment(tp.file.title, 'YY-MM-DD').dayOfYear() %></a></div>
    <div class='left'>🝮
        <% moment(moment(tp.file.title, 'YY-MM-DD').endOf('year')).diff(moment(tp.file.title, 'YY-MM-DD'), 'days') %>
        days left</div>
    <progress value='<% moment(tp.file.title, 'YY-MM-DD').dayOfYear() %>' max='365'>
</div></div>
```


### Filled sample
```
<div class='daily'>
    <div class='todayday'>sábado 24</div>
    <div class='todaymonth'>෴julio 2021෴</div>
</div>
<div class='bars'><div class='bars-progres'>
    <div class='time'><a class='internal-link' id='big-link' href='21-w29.md'>week 29</a></div>
    <div class='left'><a class='internal-link' id='small-link' href='21-07-23.md'>yesterday</a>
    🟊 <a class='internal-link' id='small-link' href='21-07-25.md'>tomorrow</a></div>
    <progress value='6' max='7'></div>
<div class='bars-progres'>
    <div class='time'><a class='internal-link' id='big-link' href='21-07-00.md'>julio</a></div>
    <div class='left'>🝮 7 days left</div>
    <progress value='24' max='31'></div>
<div class='bars-progres'>
    <div class='time'><a class='internal-link' id='big-link' href='21-Quarter3.md'>3º quarter</a></div>
    <div class='left'>🝮 68 days left</div>
    <progress value='24' max='92'></div>
<div class='bars-progres'>
    <div class='time'><a class='internal-link' id='big-link' href='2021.md'>Day #205</a></div>
    <div class='left'>🝮 160 days left</div>
    <progress value='205' max='365'>
</div></div>
```

