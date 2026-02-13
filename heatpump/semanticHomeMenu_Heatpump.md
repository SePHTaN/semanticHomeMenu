# The different Parts of the Widget
This Widget is intended for use with a Viessmann Vitocal 250A heatpump.
It is trying to bring the same functionality to Openhab that the original ViCareAPP from Viessmann has.

## The Widget itself

<img alt="Heatpump" src="/heatpump/Images/Heatpump.png" width="inherit"></img>  
The Widget shows some Item-States for a quick overview, also the Button **Schnell Wahlen** (Fast Choices) for some heatpump settings that might be needed more often.  
<img src="https://api.iconify.design/mdi/outside-temperature.svg?color=`#000000`></img>
![Grafik](https://api.iconify.design/mdi/outside-temperature.svg?color=`#000000`)

## The "Fast-Choices" aka "Schnell Wahlen" Part (Popup)

<img alt="Schnell Wahlen" src="/heatpump/Images/Heatpump_Schnellwahlen.png" width="inherit"></img>  
The popup opens sliders for _Betriebsart_, _Zeitphase verlängern_, _Ferien_ and _FerienZuHause_.  
_Einmalige Warmwassererwärmung_ and _Einmal Zeitphase verlängern_ show checkmarks if enabled.
As soon as _Ferien_ and _FerienZuHause_ are functional, the checkmark feature gets added.

## The Subsections of "Schnell Wahlen" (Sliders within this Popup):

<img alt="Schnell Wahlen Betriebsart" src="/heatpump/Images/Heatpump_Schnellwahlen_Betriebsart.png" width="32%"><img alt="Schnell Wahlen Zeitphase" src="/heatpump/Images/Heatpump_Schnellwahlen_Zeitphase.png" width="32%">
<img alt="Schnell Wahlen Ferien" src="/heatpump/Images/Heatpump_Schnellwahlen_Ferien.png" width="32%"></img>  

Betriebsart uses directly the Items of the Heatpump.  
Zeitphase can handle up to 4 heating circuits at the moment.  
Ferien and Ferien-Zuhause (Holiday and HolidayAtHome) is ready but not functional due to an problem with the ViessmannBinding or the ViessmannAPI itself.  

## The Widget Tabs

<img alt="Heatpump Tab1" src="/heatpump/Images/Heatpump_Tab1.png" width="32%"><img alt="Heatpump Tab1 Heizkurve" src="/heatpump/Images/Heatpump_Tab1_Heizkurve.png" width="32%"></img>  


<img alt="Heatpump Tab2" src="/heatpump/Images/Heatpump_Tab2.png" width="32%">

<img alt="Heatpump Tab3 WW" src="/heatpump/Images/Heatpump_Tab3_WW.png" width="32%"><img alt="Heatpump Tab3 Zirk" src="/heatpump/Images/Heatpump_Tab3_Zirkulation.png" width="32%">

<img alt="Heatpump Tab3 Hysterese" src="/heatpump/Images/Heatpump_Tab3_Hysterese.png" width="32%"><img alt="Heatpump Tab3 Hygiene" src="/heatpump/Images/Heatpump_Tab3_Hygiene.png" width="32%">

<img alt="Heatpump Tab4" src="/heatpump/Images/Heatpump_Tab4.png" width="inherit">
