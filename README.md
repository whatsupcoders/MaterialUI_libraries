# MaterialUI_libraries

# Overview
Material Design is a design standard for creating and designing websites and apps. Material design was introduced to bring order and unity to web design.

Material design concept was inspired by paper and ink in the physical world. As paper exists in three dimensions having shadows and can be structured in different ways same way material design works. It removed the flat UI's with three dimensional designs.

<img src="screenshots/materialUI.png" >

# What is MaterialUI?
# Benefits
# Typical Use Cases
# Usage Instructions
# List of Libraries

# 1. Buttons
# 2. Radio Buttons

A **radio button** is a component used to select only one option from a predefined set of options, therefore it is also called as ***option button***.

Radio buttons are used where users need to select only one option out of 2 or more options. These options contain circular white space. If any option is selected then circular white space is getting filled with a dot.
If any option is already selected and you will click on any other option then the first option will be deselected.

In the image below **One** is *selected*, **Two** & **Three** are *deselected*.

<img src="screenshots/RadioButtonExample.png" width="100" height="100">

## 2. Benefits

* Offers an element of flexibility.
* Material Design provides a clean and intuitive interface.
* Can be applied to complex and rare use cases.
* Having a vast set of guidelines and documentation.

## 3. Typical UseCases:

MaterialRadio library can be implemented in most of the commonly used applications where users have to select only one option out of many. Below are some of the examples:

<img src="screenshots/usecase1.png" width="200" height="200"><img src="screenshots/usecase2.png" width="200" height="200"><img src="screenshots/usecase3.png" width="200" height="200">

## 4. List of Features:

There are few features of Radio buttons listed below:

***1. Enabled:*** Radio button can be selected. (Vastly used in application)
```
RadioButton({
    model: this.radioModel1,
    onCheckChange: this.onRadioCheck
})
```

***2. Disabled:*** Radio button can't be selected.
```
aboutToAppear() {
    this.radioModel2.setDisabled(true);
}
RadioButton({
    model: this.radioModel2,
    onCheckChange: this.onRadioCheck
})
```

***3. Checked and Enabled:*** Radio button will be selected by default. While clicking the dot will show some ripple effect.
```
RadioButton({
    model: this.radioModel3,
    checked: true,
    onCheckChange: this.onRadioCheck
})
```

***4. Checked and Disabled:*** Radio button will be selected and can't be deselected. This button appears a little bit off color.
```
aboutToAppear() {
    this.radioModel4.setDisabled(true);
}
RadioButton({
    model: this.radioModel4,
    checked: true,
    onCheckChange: this.onRadioCheck
})
```

Please refer below Image: 

<img src="screenshots/Types.png" width="300" height="300">

## 5. Download & Install:

Install using npm: 
```
npm i ohos-material-radio
```

Details about OpenHarmony NPM environment configuration, click [here](https://gitee.com/openharmony-tpc/docs/blob/master/OpenHarmony_npm_usage.md). 

<hr/>

## 6. Usage Instructions:

1. Import files and code dependencies

```ets
import { RadioButton, RadioGroup, RadioOption, RadioModel }  from '@ohos/material-radio'
```

2. Initialize model data

```
private radioModel: RadioModel = new RadioModel(1, "Radio Label")
```

3. Code for creating radio button

```
RadioButton({
    checked: true,
    model: this.radioModel,
    onCheckChange: (selectedRadioId) => {
        console.log("Selected Radio Button Id:: " + selectedRadioId);
    }
})
```

<img src="screenshots/Radio%20Buttons.png" width="300" height="500">

4. Code for creating radio group

```
RadioGroup(
    {
        selectedRadioId: 1,
        options: [new RadioOption(1, "Option 1"), new RadioOption(2, "Option 2")],
        onCheckChange: (selectedRadioId) => {
            console.log("Selected Radio Button Id:: " + selectedRadioId);
        }
    }
)
```

<img src="screenshots/Radio%20Group.png" width="300" height="500">

## 7. Library Features:

### Feature-1: 

***Description:*** User needs to provide radioId, radiolabel, selectedRadioId to create material radio button. Apart from those, users can also send checked and disabled properties also.

***Code Snippet:***

```
private radioModel: RadioModel = new RadioModel(1, “Radio Button”)
radioModel.setRingColor(Color.Blue);
radioModel.setDisabled(false);

RadioButton({
        model: this.radioModel,
        checked: false,
        onCheckChange: (id: number) => {
            console.log(“Radio button selected:: ” + id);
})
```
***Explanation:***

In above code one radio button was created, where button color was set to blue and was enabled for selection. By default it was deselected. While clicking button one toast will appear giving message "Radio button selected::*buttonid*"


Below are list of properties available:

|Properties|Description|
 |:-:|:-:|
 | `setRingColor`|Changing color of radio button circle|
 | `setDisabled` |making radio button enabled or disabled|
 | `checked`|showing radio button is selected or deselected by default|
 |||

***Screenshot:***

<img src="screenshots/feature1.png" width="300" height="300">

<br>

### Feature-2: 

***Description:*** User needs to provide a radio options list to create a material radio group.

***Code Snippet:***

```
private radioOptions: RadioOption [] = [
    new RadioOption(1, “Option 1”),
    new RadioOption(2, “Option 2”),
    new RadioOption(3, “Option 3”)
]

RadioGroup({
        options: this.radioOptions,
        onCheckChange: (id: number) => {
            console.log(“Selected radio button id:: ” + id);
      })
```

***Explanation:***

In the above code one Radio Group was created with 3 sets of options. By default all buttons will be deselected. If you click any option one toast will appear giving the message "Radio button selected::*buttonid*". Again if you click any other option then previous selected option will be deselected and one toast will appear "Radio button selected::*buttonid*"

***Screenshot:***

<img src="screenshots/feature-2.jpg" width="300" height="500">

# 2. Sliders

Sliders allow users to make selections from a range of values. We can adjust volume, brightness or use it for selection in e-commerce application. Lets see how to create Slider.

![MaterialSlider](https://user-images.githubusercontent.com/107906555/177477579-f558e7ee-9740-44a2-8788-aa4742e75f86.gif)


#### Import
```js
import { MaterialSlider, SliderModel, SliderType } from '@ohos/materialslider'
```

#### Usage
Access slider attributes through a object of SliderModel and customize the slider(if needed) using setter functions and finally pass the object to MaterialSlider.

 Below are list of properties available.
 | Properties   | Description | Type |
 | -------------| ------------| -----|
 | SliderType     |   Defined the type of the Slider         | SliderType Enum (Continue, Discrete)  |
 | SliderStyle |    Defines the style of the Slider       | SliderStyle Enum (InSet, OutSet)  |
 | min, max|    Defines the minimum and maximun values of the Slider       |  number           |
 |  step         |   Step of the slider              |   number    |
 | showSteps  |  Whether to display the current step    |   boolean (Default: false)   |
 | showTips   |  Displays the bubble to indicate the percentage while sliding   | boolean (Default: false)  |
 | showMin, showMax | Displays the minimum and maximum values on the screen  | boolean   |
 |  showValue  | Displays the value of the Slider on the screen  |  boolean  |
 | trackThickness  |  Defines the thickness of the track  |  number   |
 |  reverse   | Whether to display the slider values in reverse  |  boolean (Default: false)  |
 |  direction  |  Defines the direction of the slider (Horizontally or Vertically)  | Axis Enum (Horizontal, Vertical)   |
 | currentValue  |  Current progress of the slider   |  number   |
 |  blockColor   |  Color of the Slider   |  ResourceColor  |
 |  trackColor   |  Background color of the Slider   |  ResourceColor  |
 |  selectedColor   |  Color of the Slider rail that has been slid |  ResourceColor  |
 |           |             |              |
 
 Below are the events that are supported by Slider
 | Properties   | Description |
 | -------------| ------------|
 | onSliderChange(callback: (value: number, mode: SliderChangeMode) => void)   |  Callback is invoked when the slider slides  <br /> **value** - Current Value of the Slider <br /> **mode** - Dragging state or Mode of the Slider (SliderChangeMode Enum - Begin, Moving, End)    |
 
#### Continuous Slider - Usage
Continuous sliders allow users to make selections that don’t require a specific value. These sliders are often used to adjust brightness or volume.

##### OutSet

```js
//Creating object of the SliderModel class with Slider type as Continue
private sliderModel: SliderModel = new SliderModel(SliderType.Continue)

//Customization of the SliderModel object and mentioning the SliderStyle as OutSet
aboutToAppear(){
    this.sliderModel.setSliderStyle(SliderStyle.OutSet)
    this.sliderModel.setMin(100)
    this.sliderModel.setMax(1000)
    this.sliderModel.setStep(1)
    this.sliderModel.setCurrentValue(500)
    this.sliderModel.setShowSteps(false)
    this.sliderModel.setShowTips(true)
    this.sliderModel.setTrackThickness(8)
    this.sliderModel.setReverse(false)
    this.sliderModel.setDirection(Axis.Horizontal)
    this.sliderModel.setShowValue(true)
    this.sliderModel.setShowMin(false)
    this.sliderModel.setShowMax(false)
    this.sliderModel.setBlockColor("#ff0477ff")
    this.sliderModel.setTrackColor("#D0D0D0")
    this.sliderModel.setSelectedColor("#ff0477ff")
}    

//Passing SliderModel object to MaterialSlider and defining the Event onSliderChange
MaterialSlider({
      obj: this.sliderModel1,
      onSliderChange:((value: number, mode: SliderChangeMode) => {
           console.log("Value: " + value + " Mode: " + mode);
      })
})
```

![ContinuousOutset](https://user-images.githubusercontent.com/107906555/177507023-7415aa49-1236-4663-b893-fc96d76d5664.jpg)

##### InSet

```js
//Creating object of the SliderModel class with Slider type as Continue 
private sliderModel: SliderModel = new SliderModel(SliderType.Continue)

//Customization of the SliderModel object and mentioning the SliderStyle as InSet
aboutToAppear(){
    this.sliderModel.setSliderSliderStyle(SliderStyle.InSet)
    this.sliderModel.setMin(0)
    this.sliderModel.setMax(100)
    this.sliderModel.setStep(1)
    this.sliderModel.setCurrentValue(40)
    this.sliderModel.setShowSteps(false)
    this.sliderModel.setShowTips(true)
    this.sliderModel.setTrackThickness(15)
    this.sliderModel.setReverse(false)
    this.sliderModel.setDirection(Axis.Horizontal)
    this.sliderModel.setShowValue(true)
    this.sliderModel.setShowMin(false)
    this.sliderModel.setShowMax(false)
    this.sliderModel.setBlockColor(Color.White)
    this.sliderModel.setTrackColor("#D0D0D0")
    this.sliderModel.setSelectedColor("#ff0477ff")
}    

//Passing SliderModel object to MaterialSlider and defining the Event onSliderChange
MaterialSlider({
      obj: this.sliderModel1,
      onSliderChange:((value: number, mode: SliderChangeMode) => {
           console.log("Value: " + value + " Mode: " + mode);
      })
})
```
![ContinuousInset](https://user-images.githubusercontent.com/107906555/177507103-2f7b4bbb-84a6-41ee-ad4d-f36e6f0d2362.jpg)

#### Discrete Slider - Usage
Discrete sliders display a numeric value label upon pressing the thumb, allowing users to input an exact value. Discrete sliders only allow predefined sets of options or values to be selected. These sliders are often used in scenarios where there are pre-defined values are available like choosing shoe size or any clothing size, etc.

##### OutSet

```js
//Creating object of the SliderModel class with Slider type as Discrete 
private sliderModel: SliderModel = new SliderModel(SliderType.Discrete)

//Customization of the SliderModel object and mentioning the SliderStyle as OutSet
aboutToAppear(){
    this.sliderModel.setSliderStyle(SliderStyle.OutSet)
    this.sliderModel.setMin(1000)
    this.sliderModel.setMax(10000)
    this.sliderModel.setStep(1000)
    this.sliderModel.setCurrentValue(3000)
    this.sliderModel.setShowSteps(true)
    this.sliderModel.setShowTips(true)
    this.sliderModel.setTrackThickness(8)
    this.sliderModel.setReverse(false)
    this.sliderModel.setDirection(Axis.Horizontal)
    this.sliderModel.setShowValue(true)
    this.sliderModel.setShowMin(false)
    this.sliderModel.setShowMax(false)
    this.sliderModel.setBlockColor("#ff0477ff")
    this.sliderModel.setTrackColor("#D0D0D0")
    this.sliderModel.setSelectedColor("#ff0477ff")
}    

//Passing SliderModel object to MaterialSlider and defining the Event onSliderChange
MaterialSlider({
      obj: this.sliderModel1,
      onSliderChange:((value: number, mode: SliderChangeMode) => {
           console.log("Value: " + value + " Mode: " + mode);
      })
})
```
![DiscreteOutset](https://user-images.githubusercontent.com/107906555/177507151-c2e55b30-3e3a-48fc-92b7-20f9cb4be7a8.jpg)

##### InSet

```js
//Creating object of the SliderModel class with Slider type as Discrete 
private sliderModel: SliderModel = new SliderModel(SliderType.Discrete)

//Customization of the SliderModel object and mentioning the SliderStyle as InSet
aboutToAppear(){
    this.sliderModel.setSliderStyle(SliderStyle.InSet)
    this.sliderModel.setMin(0)
    this.sliderModel.setMax(100)
    this.sliderModel.setStep(10)
    this.sliderModel.setCurrentValue(50)
    this.sliderModel.setShowSteps(true)
    this.sliderModel.setShowTips(true)
    this.sliderModel.setTrackThickness(15)
    this.sliderModel.setReverse(false)
    this.sliderModel.setDirection(Axis.Horizontal)
    this.sliderModel.setShowValue(true)
    this.sliderModel.setShowMin(true)
    this.sliderModel.setShowMax(true)
    this.sliderModel.setBlockColor(Color.White)
    this.sliderModel.setTrackColor("#D0D0D0")
    this.sliderModel.setSelectedColor("#ff0477ff")
}    

//Passing SliderModel object to MaterialSlider and defining the Event onSliderChange
MaterialSlider({
      obj: this.sliderModel1,
      onSliderChange:((value: number, mode: SliderChangeMode) => {
           console.log("Value: " + value + " Mode: " + mode);
      })
})           
```
![DiscreteInset](https://user-images.githubusercontent.com/107906555/177507177-f524121a-2845-4914-85c8-6176fe8e4483.jpg)

# 3. Switches
# 4. Checkboxs
# 5. TextFields
# 6. Select Menus
# 7. Lists
# 8. Dialogs
# 9. Progress Indicators
# 10. Tabs
# 11. Snackbar

# 13. Cards
# 14. Fab
# 15. Chips
# 16. Date Picker
# 17. Time Picker
# 18. Bottom Bar
# 19. Banners
# 20. Navigation Drawer
# 21. Navigation Bar
# 22. backdrop
# 23. ImageList
# 24. Bottom Sheets
# 25. Select
# 26. Business Hour Picker
# 27. CalendarView
# 28. Top Bar
# 29. Side Sheet

# Conclusion

# Open source License

This project is based on <a href="https://github.com/whatsupcoders/MaterialUI_libraries/blob/main/LICENSE"> Apache License 2.0 </a> ，please enjoy and participate in open source freely.
