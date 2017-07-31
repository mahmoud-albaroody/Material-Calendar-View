# Material-Calendar-View

Material-Calendar-View is a simple and customizable calendar widget for Android based on Material Design. The widget has two funcionalities: a date picker to select dates and a classic calendar.

We described a simple usage of the component [in this article](http://applandeo.com/blog/material-calendar-view-customized-calendar-widget-android/).

![device-2017-05-29-072746](https://user-images.githubusercontent.com/2614225/28766028-ef15ad58-75cd-11e7-8f11-1800d60d8bfc.png) ![device-2017-05-29-075947](https://user-images.githubusercontent.com/2614225/28766037-f49d0424-75cd-11e7-8671-2c9424f13ffd.png) ![device-2017-07-31-084300](https://user-images.githubusercontent.com/2614225/28766040-f70463d8-75cd-11e7-9e0d-ab247fd17749.png)


## Features
* Material Design
* Date picker mode
* Events icons
* Marks today


## How to use?
Make sure you have defined the **jcenter()** repository in project's **build.gradle** file:
```
allprojects {
    repositories {
        jcenter()
    }
}
```

Add the dependency to module's **build.gradle** file:
```
dependencies {
    compile 'com.applandeo:material-calendar-view:1.1.0'
}
```

To your **XML layout** file add:
```xml
<com.applandeo.materialcalendarview.CalendarView
    android:id="@+id/calendarView"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

### Adding events with icons:
```java
List<EventDay> events = new ArrayList<>();

Calendar calendar = Calendar.getInstance();
events.add(new EventDay(calendar, R.drawable.sample_icon));

CalendarView calendarView = (CalendarView) findViewById(R.id.calendarView);
calendarView.setEvents(events);
```

### Clicks handling:
```java
calendarView.setOnDayClickListener(new OnDayClickListener() {
    @Override
    public void onDayClick(EventDay eventDay) {
        Calendar clickedDayCalendar = eventDay.getCalendar();    
    }
});
```

### Getting a selected day in the picker mode:
```java
Calendar selectedDayCalendar = calendarView.getSelectedDate();
```

### Setting a current date:
```java
Calendar calendar = Calendar.getInstance();
calendar.set(2019, 7, 5);
        
calendarView.setDate(calendar);
```

## Customization
If you want to use calendar in the picker mode, in your XML layout set: ```app:datePicker="true"```

#### Colors customization:
* Header color: ```app:headerColor="[color]"```
* Header label color: ```app:headerLabelColor="[color]"```
* Previous button image resource: ```app:previousButtonSrc="[drawable]"```
* Forward button image resource: ```app:forwardButtonSrc="[drawable]"```
* Selection color in picker mode: ```app:selectionColor="[color]"```
* Today label color: ```app:todayLabelColor="[color]"```

#### Translations:
* Array of months names: ```app:monthsNames="[array]"``` (array must contains 12 names)
* Array of abbreviations of days of the week: ```app:daysNames="[array]"``` (array must contains 7 abbreviations)

## Changelog
#### Version 1.1.0:
* Added build-in DatePicker dialog

#### Version 1.0.1:
* Bugs fixes

#### Version 1.0.0:
* Initial build

## Get in touch
It would be great if you decide to use our component in your project. It’s open source, feel free. Write to us at hi@applandeo.com if you want to be listed and we will include your app in our repo. If you have any questions or suggestions just let us know.

#### Apps using Material-Calendar-View:
* [FreQuest](https://play.google.com/store/apps/details?id=com.applandeo.frequest)

## License
```
Copyright 2017, Applandeo sp. z o.o.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
