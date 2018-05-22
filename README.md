## Important note

This project is [due to be handed over](https://github.com/nhnent/tui.calendar/issues/82) to the Toast UI folks.

The information below is for whoever wants to try it in the meantime.

### Installation

#### Package
npm install ngx-tui-calendar --save

#### Stylesheets
Add the Tui.Calendar stylesheet (eg. '../node_modules/tui-calendar/style.css')  to **one** of these:

- Angular CLI configuration json file; 
- global 'styles' stylesheet of your project, or 
- import as a style tag in index.html (this option will most likely require that the file be hosted somewhere)

### Usage

#### In app module:

~~~
...
import { NgxTuiCalendarModule } from 'ngx-tui-calendar';
...

@NgModule({
  ...
	imports: [
    ...
		NgxTuiCalendarModule.forRoot(),
    ...
  ]
  ...
})
~~~


#### in component.ts:
~~~
import { Component, ViewChild, ... } from '@angular/core';
...

export class CalendarComponent implements OnInit {
  ...
	@ViewChild('exampleCalendar') exampleCalendar: NgxTuiCalendarComponent;
  ...

  	onTuiCalendarCreate($event) {
      /* at this point the calendar has been created and it's methods are available via the ViewChild defined above, so for example you can do */
      this.exampleCalendar.createSchedules([/* populated schedules array*/]);
	  }
}
~~~

#### in component.html:
~~~
...
      <ngx-tui-calendar #exampleCalendar id="example-calendar" (tuiCalendarCreated)="onTuiCalendarCreate($event)"></ngx-tui-calendar>
...
~~~



#### Note on container dimensions

The container for your calendar must have explicit width and height. For example, if giving an id of "#calendar-view":

~~~
      <ngx-tui-calendar #calendarView id="example-calendar"></ngx-tui-calendar>
~~~

~~~
    #example-calendar {
        ...
        width: 100%;
        height: 100vh;
        ...
    }
~~~
