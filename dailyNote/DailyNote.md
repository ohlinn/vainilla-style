## Templater
- My Title format: 'YY-MM-DD'
- Manually replace the {{}} text with your template of your periodic notes. 

| Replace this  |   with your personalized template as usual. Example:|
|-|-|
|{{yourMonth}}  |`<% tp.date.now('YY-MM-00', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>`      |
|{{yourWeek}}   |`<% tp.date.now('YY-[w]ww', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>`      |
|{{yourQuarter}}|`<% tp.date.now('YY-[Quarter]Q', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>` |
|{{yourYear}}   |`<% tp.date.now('YYYY', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>`          |
|{{yourPrevD}}  |`<% tp.date.now('YY-MM-DD', -1, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>`     |
|{{yourNextD}}  |`<% tp.date.now('YY-MM-DD', 1, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>`      |

### HTML Templater
```
<div class='daily'>
<div class='todayday'>
    <% tp.date.now('dddd DD', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %></div>
<div class='todaymonth'>
    ෴<% tp.date.now('MMMM YYYY', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>෴</div>
</div>
<div class='bars'>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='{{yourWeek}}.md'>
            week <% tp.date.now('ww', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %></a>
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
            href='{{yourMonth}}.md'><% tp.date.now('MMMM', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %></a>
    </div>
    <div class='left'>🝮
        <% moment(moment(tp.file.title, 'YY-MM-DD').endOf('month')).diff(moment(tp.file.title, 'YY-MM-DD'), 'days') %>
        days left</div>
    <progress value='<% tp.date.now('DD', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>'
        max='<% moment(tp.file.title, 'YY-MM-DD').daysInMonth() %>'>
</div>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='{{yourQuarter}}.md'><% tp.date.now('Qo [quarter]', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %></a>
    </div>
    <div class='left'>🝮
        <% moment(moment('21-09-30', 'YY-MM-DD')).diff(moment(tp.file.title, 'YY-MM-DD'), 'days') %> days left</div>
    <progress value='<% moment(moment(tp.file.title, 'YY-MM-DD')).diff(moment('21-06-30', 'YY-MM-DD'), 'days') %>'
        max='<% moment(moment('21-09-30', 'YY-MM-DD')).diff(moment('21-06-30', 'YY-MM-DD'), 'days') %>'>
</div>
<div class='bars-progres'>
    <div class='time'><a class='internal-link' id='big-link'
            href='{{yourYear}}.md'>Day
            #<% moment(tp.file.title, 'YY-MM-DD').dayOfYear() %></a></div>
    <div class='left'>🝮
        <% moment(moment(tp.file.title, 'YY-MM-DD').endOf('year')).diff(moment(tp.file.title, 'YY-MM-DD'), 'days') %>
        days left</div>
    <progress value='<% moment(tp.file.title, 'YY-MM-DD').dayOfYear() %>' max='365'>
</div></div>
```

### Mine
```<div class='daily'>
<div class='todayday'>
    <% tp.date.now('dddd DD', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %></div>
<div class='todaymonth'>
    ෴<% tp.date.now('MMMM YYYY', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>෴</div>
</div>
<div class='bars'>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='<% tp.date.now('YY-[w]ww', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>.md'>
            week <% tp.date.now('ww', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %></a>
    </div>
    <div class='left'><a class='internal-link' id='small-link'
            href='<% tp.date.now('YY-MM-DD', -1, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>.md'>yesterday</a>
        🟊 <a class='internal-link' id='small-link'
            href='<% tp.date.now('YY-MM-DD', 1, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>.md'>tomorrow</a>
    </div>
    <progress value='<% moment(tp.file.title, 'YY-MM-DD').isoWeekday() %>' max='7'>
</div>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='<% tp.date.now('YY-MM-00', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>.md'>
            <% tp.date.now('MMMM', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %></a>
    </div>
    <div class='left'>🝮
        <% moment(moment(tp.file.title, 'YY-MM-DD').endOf('month')).diff(moment(tp.file.title, 'YY-MM-DD'), 'days') %>
        days left</div>
    <progress value='<% tp.date.now('DD', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>'
        max='<% moment(tp.file.title, 'YY-MM-DD').daysInMonth() %>'>
</div>
<div class='bars-progres'>
    <div class='time'>
        <a class='internal-link' id='big-link'
            href='<% tp.date.now('YY-[Quarter]Q', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>.md'><% tp.date.now('Qo [quarter]', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %></a>
    </div>
    <div class='left'>🝮
        <% moment(moment('21-09-30', 'YY-MM-DD')).diff(moment(tp.file.title, 'YY-MM-DD'), 'days') %> days left</div>
    <progress value='<% moment(moment(tp.file.title, 'YY-MM-DD')).diff(moment('21-06-30', 'YY-MM-DD'), 'days') %>'
        max='<% moment(moment('21-09-30', 'YY-MM-DD')).diff(moment('21-06-30', 'YY-MM-DD'), 'days') %>'>
</div>
<div class='bars-progres'>
    <div class='time'><a class='internal-link' id='big-link'
            href='<% tp.date.now('YYYY', 0, tp.date.now('YY-MM-DD', 0, tp.file.title, 'YY-MM-DD'), 'YY-MM-DD') %>.md'>Day
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

