### Filled sample
```<div class="daily">
    <div class="todayday">
        domingo 05
    </div>
    <div class="todaymonth">෴septiembre 2021෴</div>
</div>
<div class="bars">
    <div class="bars-progres">
        <div class="progres">
            <p>
                <a class="internal-link" id="big-link" href=" 21-w35.md">
                    week 35
                </a></br>
                <a class="internal-link" id="small-link" href=" 21-09-04.md">ayer</a>
                🟊 <a class="internal-link" id="small-link" href=" 21-09-06.md">mañana</a>
            </p>
            <progress value="0" max="7">
        </div>
        <div class="progres">
            <p><a class="internal-link" id="big-link" href=" 21-09-00.md">
                    septiembre
                </a></br>
                🝮 25 días restantes</p>
            <progress value=" 05" max="30">
        </div>
        <div class="progres">
            <p><a class="internal-link" id="big-link" href=" 21-Quarter3.md">
                    3ºQUARTER
                </a> </br>
                🝮 25 días
                restantes</p>
            <progress value="67" max="92">
        </div>
        <div class="progres">
            <p><a class="internal-link" id="big-link" href="_Index_00. Bitácora.md">
                    Día 248</a> </br>
                🝮 117 días restantes del 2021 </p>
            <progress value="248" max="365">
        </div>
    </div>
</div>
```


## Templater
```
<div class="daily">
    <div class="todayday">
        <% tp.date.now("dddd DD",0,tp.date.now("YY-MM-DD", 0, tp.file.title, "YY-MM-DD" ),"YY-MM-DD") %>
    </div>
    <div class="todaymonth">෴<% tp.date.now("MMMM YYYY",0,tp.date.now("YY-MM-DD", 0, tp.file.title, "YY-MM-DD"
            ),"YY-MM-DD") %>෴</div>
</div>
<div class="bars">
    <div class="bars-progres">
        <div class="progres">
            <p>
                <a class="internal-link" id="big-link" href="<% tp.date.now(" YY-[w]ww",0,tp.date.now("YY-MM-DD", 0,
                    tp.file.title, "YY-MM-DD" ),"YY-MM-DD") %>.md">
                    week <% tp.date.now("ww",0,tp.date.now("YY-MM-DD", 0, tp.file.title, "YY-MM-DD" ),"YY-MM-DD") %>
                </a></br>
                <a class="internal-link" id="small-link" href="<% tp.date.now(" YY-MM-DD",-1,tp.date.now("YY-MM-DD", 0,
                    tp.file.title, "YY-MM-DD" ),"YY-MM-DD") %>.md">ayer</a>
                🟊 <a class="internal-link" id="small-link" href="<% tp.date.now(" YY-MM-DD",1,tp.date.now("YY-MM-DD",
                    0, tp.file.title, "YY-MM-DD" ),"YY-MM-DD") %>.md">mañana</a>
            </p>
            <progress value="<% 
    moment(tp.file.title,'YY-MM-DD').day() %>" max="7">
        </div>
        <div class="progres">
            <p><a class="internal-link" id="big-link" href="<% tp.date.now(" YY-MM-00",0,tp.date.now("YY-MM-DD", 0,
                    tp.file.title, "YY-MM-DD" ),"YY-MM-DD") %>.md">
                    <% tp.date.now("MMMM",0,tp.date.now("YY-MM-DD", 0, tp.file.title, "YY-MM-DD" ),"YY-MM-DD") %>
                </a></br>
                🝮 <%
                    moment(moment(tp.file.title,'YY-MM-DD').endOf('month')).diff(moment(tp.file.title,'YY-MM-DD'),'days')
                    %> días restantes</p>
            <progress value="<% tp.date.now(" DD",0,tp.date.now("YY-MM-DD", 0, tp.file.title, "YY-MM-DD" ),"YY-MM-DD")
                %>" max="<% moment(tp.file.title,'YY-MM-DD').daysInMonth() %>">
        </div>
        <div class="progres">
            <p><a class="internal-link" id="big-link" href="<% tp.date.now(" YY-[Quarter]Q",0,tp.date.now("YY-MM-DD", 0,
                    tp.file.title, "YY-MM-DD" ),"YY-MM-DD") %>.md">
                    <% tp.date.now("Qo",0,tp.date.now("YY-MM-DD", 0, tp.file.title, "YY-MM-DD" ),"YY-MM-DD") %>QUARTER
                </a> </br>
                🝮 <% moment(moment("21-09-30",'YY-MM-DD')).diff(moment(tp.file.title,'YY-MM-DD'),'days') %> días
                restantes</p>
            <progress value="<% 
    moment(moment(tp.file.title,'YY-MM-DD')).diff(moment(" 21-06-30",'YY-MM-DD'),'days') %>" max="<%
                    moment(moment("21-09-30",'YY-MM-DD')).diff(moment("21-06-30",'YY-MM-DD'),'days') %>">
        </div>
        <div class="progres">
            <p><a class="internal-link" id="big-link" href="_Index_00. Bitácora.md">
                    Día <% moment(tp.file.title,'YY-MM-DD').dayOfYear() %></a> </br>
                🝮 <%
                    moment(moment(tp.file.title,'YY-MM-DD').endOf('year')).diff(moment(tp.file.title,'YY-MM-DD'),'days')
                    %> días restantes del 2021 </p>
            <progress value="<% moment(tp.file.title,'YY-MM-DD').dayOfYear() %>" max="365">
        </div>
    </div>
</div>
```
