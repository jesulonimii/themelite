# ThemeLite
A Java library for implementing dark theme easily in android apps.

# Features
* Easy Implentation
* Saves the theme even when app restart



# Implementation
* ####Step 1. Add this in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
* ###Step 2. Add the dependency

	dependencies {
	        implementation 'com.github.erliteHq:themelite:1.1.0'
	}
	
* ###Step 3. Duplicate your Values folder in res and rename as "values-night"

* ###Step 4. In your colors xml file, set the corresponding dark theme colors.
	
* ###Step 5. Create a Switch in your layout xml file

* ###Step 6.  Add this to your activity

```
  @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_###);

        //initialize ThemeLite
      themeLite = new ThemeLite(this);

      //declare
      darkSwitch = findViewById(R.id.darkSwitch);


      //set theme
        themeLite.setTheme();

        //set switch state dependent on theme
        if (themeLite.getTheme == themeLite.dark){
            darkSwitch.setChecked(true);
        }

        //switch listener
        darkSwitch.setOnCheckedChangeListener(new CompoundButton.OnCheckedChangeListener() {
            @Override
            public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {

                if(isChecked){
                    themeLite.dark();
                } else {
                    themeLite.light();
                }

            }
        });


    }

    //save theme for app restart in splash or main activity
    @Override
    protected void onSaveInstanceState(@NonNull Bundle outState) {
        super.onSaveInstanceState(outState);

        themeLite.saveTheme(this);

    }
  ```
 ### et Voila!

# Preview
![Preview screenshot]()



