# SmoothDateRangePicker
Based on [SmoothDateRangePicker by leavjenn] (https://github.com/leavjenn/SmoothDateRangePicker)

Smooth Date Range Picker is an android widget for selecting date range quickly and easily, following Material Design principle. This library is based on [datetimepicker from Android frameworks](https://android.googlesource.com/platform/frameworks/opt/datetimepicker/) and [Material DateTime Picker by wdullaer](https://github.com/wdullaer/MaterialDateTimePicker).

Date Range Picker | Duration Number Pad | Date Range Picker Dark Theme | Date Range Picker Landscape
---- | ----| ----| ----
![Date Range Picker](https://raw.githubusercontent.com/wsbak/SmoothDateRangePicker/gh-pages/screenshots/date_range_picker.png) | ![Duration Number Pad](https://raw.githubusercontent.com/wsbak/SmoothDateRangePicker/gh-pages/screenshots/date_duration_number_pad.png) | ![Date Range Picker Dark Theme](https://raw.githubusercontent.com/wsbak/SmoothDateRangePicker/gh-pages/screenshots/date_range_picker_dark_theme.png) | ![Date Range Picker Landscape](https://raw.githubusercontent.com/wsbak/SmoothDateRangePicker/gh-pages/screenshots/date_range_picker_landscape.png)

Date Disable Enable Controls | Start Date Disabled | End Date Disabled | End Date Disabled Landscape Dark Theme
---- | ----| ----| ----
![Date Disable Enable Controls](https://raw.githubusercontent.com/wsbak/SmoothDateRangePicker/gh-pages/screenshots/Date_disable_enable_controls.png) | ![Start Date Disabled](https://raw.githubusercontent.com/wsbak/SmoothDateRangePicker/gh-pages/screenshots/Start_date_disabled.png) | ![End Date Disabled](https://raw.githubusercontent.com/wsbak/SmoothDateRangePicker/gh-pages/screenshots/End_date_disabled.png) | ![End Date Disabled Landscape Dark Theme](https://raw.githubusercontent.com/wsbak/SmoothDateRangePicker/gh-pages/screenshots/End_date_disabled_landscape_dark_theme.png)

## Setup

**Gradle:**

Add jitpack repository into project `build.gradle`:
```
repositories {
    maven { url "https://jitpack.io" }
}
```

Add the following into app `build.gradle`:
```
dependencies {
  implementation 'com.github.wsbak:SmoothDateRangePicker:0.4.1'
}
```

## Usage

Since SmoothDateRangePickerFragment is a subclass of DialogFragment, the usage is just like other DialogFragment.

**Instantiation, the default selected date is set to today:**
```
SmoothDateRangePickerFragment.newInstance(SmoothDateRangePickerFragment.OnDateRangeSetListener callBack)
```


After instantiation, remember to call

`show (FragmentManager manager, String tag)`

Example:
```
SmoothDateRangePickerFragment smoothDateRangePickerFragment = SmoothDateRangePickerFragment.newInstance(
new SmoothDateRangePickerFragment.OnDateRangeSetListener() {
                    @Override
                    public void onDateRangeSet(SmoothDateRangePickerFragment view,
                                               Calendar calendarStart,
                                               Calendar calendarEnd) {
                        // grab the date range, do what you want
                        // calendarStart or calendarEnd can be null if user disable it
                    }
                });
                
smoothDateRangePickerFragment.show(getFragmentManager(), "smoothDateRangePicker");
```


## Additional options

### Style
**Change picker accent color:**

`setAccentColor(int color)`

**Change picker theme to dark:**

`setThemeDark(true)`


### Date
**Set selectable minimal date:**

`setMinDate(Calendar calendar)`

**Set selectable max date:**

`setMaxDate(Calendar calendar)`

**Set the default selected start date:**

`setStartDate(Calendar calendar)`

**Set the default selected end date:**

`setEndDate(Calendar calendar)`


### Disable/Enable Date
**Show disable/enable date control:**

`setShowDateEnableDisable(true)`

**Disable start date:**

`enableStartDate(false)`

**Disable end date:**

`enableEndDate(false)`


### Duration
**Hide duration:**

`setShowDuration(false)`


## License
    Copyright (c) 2015 Leav Jenn

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
