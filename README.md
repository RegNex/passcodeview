# PassCodeView
This is a custom view with keyboard and character display that can be used for authentication purpose.
#
There are some customization options that can be used...
## Demo
<img src="https://developerbryte.files.wordpress.com/2018/01/gif_20180126133123114_by_gifguru.gif" width="250" /> 

## Add to build.grade (project)
```
   dependencies {
        classpath 'com.android.tools.build:gradle:3.0.1'
        classpath 'com.github.dcendents:android-maven-gradle-plugin:1.4.1'
        classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.4'
        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
```

## Add gradle dependency
```
##build.gradle(app)
dependencies {
    implementation project(':passcodeview')
}

```

## Usage
 Add the view in the layout file

 ```xml
 <io.github.regnex.passcodesample.PassCodeView
    android:id="@+id/pass_code_view"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:digits="4"
    app:digit_size="30.0dp"
    app:key_text_size="30.0sp"
    android:padding="25.0dp"
    app:empty_drawable="@drawable/empty_dot"
    app:filled_drawable="@drawable/filled_dot"/>

 ```

View attributes that can be included in xml are


`digits` - number of digits in passcode

`filled_drawable` - drawable to be show for filled digits

`empty_drawable` - drawable to be show for empty digits

`key_text_size` - size of text in keyboard's key

`digit_spacing` - horizontal space between each digit

`digit_vertical_padding` - vertical padding of digits

`divider_visible` - boolean to show or hide divider between digits and keyboard


Other customisations options available are

```java
PassCodeView passCodeView = findViewById(R.id.pass_code_view);
Typeface typeFace = Typeface.createFromAsset(getAssets(), "fonts/Font-Bold.ttf");

/**
 *Set TypeFace for the font in keys of keypad
 */
passCodeView.setTypeFace(typeFace);

/**
 * Set color for the keypad text
 * @param color - Resource id of the color to be set
 */
passCodeView.setKeyTextColor(getResources.getColor(R.color.black));

/**
 * Set size of keypad text
 * @param size - Text size value to be set
 */
passCodeView.setKeyTextSize(30);

/**
 * Set passcode digit lenght
 * @param length - digit length to be set
 */
passCodeView.setDigitLength(6);


/**
 * Set current passcode text
 * @param code - {@code String} passcode string to be set
 */
public void setPassCode("8854")

/**
 * Reset the code to empty
 */
passCodeView.reset();

/**
 * Set drawable for empty digits programmatically
 */
 passCodeView.setEmptyDrawable(R.drawable.empty);

/**
 * Set drawable for filled digits programmatically
 */
 passCodeView.setFilledDrawable(R.drawable.filled);

/**
 * Attach {@code TextChangeListener} to get notified on text changes
 * @param listener - {@Code TextChangeListener} object to be attached and notified
 */
passCodeView.setOnTextChangeListener(new PassCodeView.TextChangeListener() {
            @Override
            public void onTextChanged(String text) {
                Log.i("Passcode", "text");
            }
        }); 
```

