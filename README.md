SuperToolTips (no longer discontinued!)
===========
[![Build Status](https://travis-ci.org/spyhunter99/supertooltips.svg?branch=master)](https://travis-ci.org/spyhunter99/supertooltips)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.spyhunter99/super-tooltip-aar/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.github.spyhunter99/super-tooltip-aar)


*This project was forked from https://github.com/ryanjohn1/onboarding, which was forked from https://github.com/nhaarman/supertooltips

SuperToolTips is an Open Source Android library that allows developers to easily create Tool Tips for views.
Feel free to use it all you want in your Android apps provided that you cite this project and include the license in your app.

Changes/Delta from the original forks
 - No layouts changes are necessary
 - Significant reduction in boilerplate code
 - Simpler and easier to use
 - Fix for adding tooltips on list view items
 - Most APIs remain the same so migration should be straight forward
 - Fix for memory leaks
 - Multiple tool tip click listeners
 - MinSdkVersion is 8


Setup
-----
*Note: SuperToolTips now uses the gradle build structure. If you want to use this project in Eclipse, you should make the necessary changes.*

Add the following to your `build.gradle`:

# Last version

Published 11/18/2017, v4.0.2

```groovy
dependencies {
    compile 'com.github.spyhunter99:super-tooltip-aar:4.0.2'
}

```
Usage
-----

In your activity, add this
````
import com.spyhunter99.supertooltips.ToolTipManager;

public class MyActivity extends Activity {
    ToolTipManager tooltips;


    public void onCreate(Bundle saved) {
        super.onCreate(saved);
        //setContentView(...);

        tooltips = new ToolTipManager(this);
        //your stuff goes here....
    }

    public void onDestroy() {
        super.onDestroy();
        tooltips.onDestroy();
        tooltips = null;
    }

    //....
 }

````

Then if you had a button somewhere in your layout that you wanted a tooltip on long press...

````
//in onCreate
findViewById(R.id.listview_activity).setOnLongClickListener(new View.OnLongClickListener() {
    @Override
    public boolean onLongClick(View v) {
        ToolTip toolTip = new ToolTip()
            .withText("A demo for tooltips on list view items")
            .withColor(Color.RED) //or whatever you want
            .withAnimationType(ToolTip.AnimationType.FROM_MASTER_VIEW)
            .withShadow();
        tooltips.showToolTip(toolTip, v);
        return true;
    }
});

````
	

ToolTip customization
-----
You can customize the `ToolTip` in several ways:

* Specify a content text using `ToolTip.setText()`.
* Set a color using `ToolTip.setColor()`.
* Specify whether to show a shadow or not with `ToolTip.setShadow()`.
* Specify how to animate the ToolTip: from the view itself or from the top, using `ToolTip.setAnimationType()`.
* Set your own custom content View using `ToolTip.setContentView()`.

See the examples.

Developed By
-----
* Alex O'Ree - this fork
* Niek Haarman https://github.com/nhaarman/supertooltips
* Ryan John https://github.com/ryanjohn1/onboarding

License
-----

	Licensed under the Apache License, Version 2.0 (the "License");
	you may not use this file except in compliance with the License.
	You may obtain a copy of the License at

	http://www.apache.org/licenses/LICENSE-2.0

	Unless required by applicable law or agreed to in writing, software
	distributed under the License is distributed on an "AS IS" BASIS,
	WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
	See the License for the specific language governing permissions and
	limitations under the License.

