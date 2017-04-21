# PhoneByCountryPickerView

![alt tag](https://68.media.tumblr.com/ae3c238d9253d7257cf6313053c466da/tumblr_inline_oor57a9XtV1u3v231_500.gif)

# How to use:
**First**<br />
In your XML file, add follow code:
```
<ru.a3technology.countrypicker.View.CountryPickerView
        android:id="@+id/countryPickerView"
        android:layout_width="match_parent"/>
```        
**Next**<br />
In your activity, add CountryPickerView and override the follow interface

```
mCountryPickerView = (CountryPickerView)findViewById(R.id.countryPickerView);
mCountryPickerView.setOnGettingPhoneNumberListener(new CountryPickerView.OnGettingPhoneNumberListener() {
            /**
             * the method called before the user going to select a country from the countries list...
             */
            @Override
            public void onUserStartedChoosingCountry(){
                //do something...
            }

            /**
             * the method calls when the user selected a country from the countries list
             * @param phone number without speshal symbols such as "+", "-" " " etc, for sending to a server
             * @param countryCode code of the country in ISO format (RU, US...)
             */
            @Override
            public void onUserSelectedCountry(String phone, String countryCode) {   
                Log.i(TAG, "+" + PhoneNumberUtils.formatNumber(phone, countryCode));
            }

        });
```
