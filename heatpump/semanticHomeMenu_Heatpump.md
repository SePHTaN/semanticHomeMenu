# The different Parts of the Widget
This Widget is intended for use with a Viessmann Vitocal 250A heatpump.
It is trying to bring the same functionality to Openhab that the original ViCareAPP from Viessmann has.

## The Widget itself

<img alt="Heatpump" src="/heatpump/Images/Heatpump.png" width="inherit"></img>  
The Widget shows some Item-States for a quick overview, also the Button **Schnell Wahlen** (Fast Choices) for some heatpump settings that might be needed more often.  
![Grafik](https://api.iconify.design/mdi/outside-temperature.svg?color=`#000000`) Shows the outside temperature beneath.  
<img src="/heatpump/Images/fan-circled-on.svg" width="16px"></img>  Indicates that the heatpump is running when animated.  
![Grafik](https://api.iconify.design/mdi/defrost.svg?color=`#000000`)  When colored $${\color{green}green}$$ the outdoor unit is defrosting.  
![Grafik](https://api.iconify.design/mdi/radiator-coil.svg?color=`#000000`)  When colored $${\color{green}green}$$ the heatpump is in heating mode.  
![Grafik](https://api.iconify.design/material-symbols-light/water-pump-rounded.svg?color=`#000000`)  When colored $${\color{green}green}$$ indicates that the heating circulation pump is running.  
![Grafik](https://api.iconify.design/lucide-lab/faucet.svg)  When colored $${\color{green}green}$$ the heatpump is in DomesticHotWater mode.  
![Grafik](https://api.iconify.design/material-symbols-light/water-pump-rounded.svg?color=`#000000`)  When colored $${\color{green}green}$$ indicates that the DHW circulation pump is running.  

## The "Fast-Choices" aka "Schnell Wahlen" Part (Popup)

<img alt="Schnell Wahlen" src="/heatpump/Images/Heatpump_Schnellwahlen.png" width="inherit"></img>  
The popup opens sliders for _Betriebsart_, _Zeitphase verlängern_, _Ferien_ and _FerienZuHause_.  
_Einmalige Warmwassererwärmung_ and _Einmal Zeitphase verlängern_ show checkmarks if enabled.  
As soon as _Ferien_ and _FerienZuHause_ are functional, the checkmark feature gets added.  

## The Subsections of "Schnell Wahlen" (Sliders within this Popup):

<img alt="Schnell Wahlen Betriebsart" src="/heatpump/Images/Heatpump_Schnellwahlen_Betriebsart.png" width="32%"> <img alt="Schnell Wahlen Zeitphase" src="/heatpump/Images/Heatpump_Schnellwahlen_Zeitphase.png" width="32%">
<img alt="Schnell Wahlen Ferien" src="/heatpump/Images/Heatpump_Schnellwahlen_Ferien.png" width="32%"></img>  

Betriebsart uses directly the Items of the Heatpump.  
Zeitphase can handle up to 4 heating circuits at the moment.  
Ferien and Ferien-Zuhause (Holiday and HolidayAtHome) is ready but not functional due to an problem with the ViessmannBinding or the ViessmannAPI itself.  

## The Widget Tabs
### Tab1 : Heatpump schematic and Heating Curve
<img alt="Heatpump Tab1" src="/heatpump/Images/Heatpump_Tab1.png" width="32%"><img alt="Heatpump Tab1 Heizkurve" src="/heatpump/Images/Heatpump_Tab1_Heizkurve.png" width="32%"></img>  

Tab1 shows an schematic representation of the different parts of the heatpump, almost the same as in the technician service settings of the heat pump with same small extensions.  
Through the ViessmannAPI available datapoints are next to the corresponding parts of the heatpump rendered, also the pumps, compressors or fans are animated when in use.  
The threeFourWayValves both indicate which function is active at the moment, the heatingRod is colored when in use.  

The button *Heizkurve* changes the view to a visualization of the heating curve, the formula to calculate the flow temperature is the same as Viessmann uses.
The available parameters are:  
- Solltemperatur : The minimum flow temperature for the heating circuit.
- Vorlauf-Begrenzung: The maximum allowed flow temperature for the heating circuit.
- Neigung : The slope for calculating the flow temperature.
- Niveau  : The parallel shift for calculating the flow temperature.

### Tab2 : Heating Schedule
<img alt="Heatpump Tab2" src="/heatpump/Images/Heatpump_Tab2.png" width="32%"> <img alt="Heatpump Tab2 Schedule" src="/heatpump/Images/Heatpump_Tab2_Schedule.png" width="302px"> <img alt="Heatpump Tab2 Schedule Setter" src="/heatpump/Images/Heatpump_Tab2_Schedule_Setter.png" width="30%"></img>

Tab2 shows the schedule for the heating mode of the heatpump, and 4 buttons to change :
- Running state of the heatpump (Heating/Standby).
- 3 Buttons to change the temperature of the three for scheduling available heating niveaus.
- Clicking on one of the weekday schedule visualizations opens a sheet for editing the schedule for this day and for adding an additional time-pair.
The opening sheet shows the day, the schedule for this day, as the niveaus in use.
- The times as the used niveau (reduced, normal, comfort) can be changed by clicking on the corresponding time-pair.
- Adding an extra time-phase is possible through the button **Neues Zeitpaar**.
The popup that open when clicking on a time-pair allows :
- Changeing the start and end times.
- Changing the wished niveau.
- Deleting the time-pair, leading to niveau _reduced_.

### Tab3 : DomesticHotWater and Zirculation Schedule, Hysterese and Hygiene Settings
<img alt="Heatpump Tab3 WW" src="/heatpump/Images/Heatpump_Tab3_WW.png" width="32%"> <img alt="Heatpump Tab3 Zirk" src="/heatpump/Images/Heatpump_Tab3_Zirkulation.png" width="32%"></img>

Tab2 shows the schedules for the circulation pumps of the heating circuit and the DomesticHotWater circuit, and 5 buttons to change :  
- The first button allows to change the mode for DHW (off, Eco, Comfort).
- The second button allows to set the target temperatur for DHW.
- The third button switches the visualized schedules beneath the buttons between _DHW schedule_ and _circulation pump schedule_. Button text indicates which schedule gets activated.
- The fourth button opens an popup to allow to change the hysterese. The hysterese controls when DHW generation switches on/off.
- The last button allows to setup wether DHW hygiene runs, when (daily/weekly) and at which time it runs. Also the target temperature can be changed.

<img alt="Heatpump HystereseWarn" src="/heatpump/Images/Heatpump_HystereseWarn.png" width="32%"> <img alt="Heatpump Tab3 Hysterese" src="/heatpump/Images/Heatpump_Tab3_Hysterese.png" width="32%"> <img alt="Heatpump Tab3 Hygiene" src="/heatpump/Images/Heatpump_Tab3_Hygiene.png" width="32%"></img>

Not much to explain:
- First image shows the warning shown before the settings popup for the hysterese settings opens.  
- Second image shows the settings popup for the hysterese settings.
- Third image shows the settings popup for the hygiene settings.

### Tab4 : Energy Data
<img alt="Heatpump Tab4" src="/heatpump/Images/Heatpump_Tab4.png" width="inherit"></img>

Tab4 currently visualizes some of the available consumption data :  
- Eletricity consumption for DHW, Heating and Total for the last twelve months.
- SCOP for DHW, Heating and Total for the last year.
- Eletricity consumption for DHW, Heating and Total since beginning of the year.
- Eventually i will extend with data of the produced heat for DHW, Heating and Total as those datapoints are available recently.

Unfortunatly the datapoints for the last two months aren't always exact as Viessmann doesn't delivers this data on the same time basis as other datapoints. Roughly only every 14 days those get updated.  

## Installation and Setup
At the moment only copying and pasting the different parts of the heatpump-widget is available.
The yaml's for the widget parts as the rules aren't the newest version as of 13.02.26.
I will need some days to get everything updated to be useable.
Some problems also exist :
- There seem to be a problem in openhab with props in nested widgets.  For example i am not able to reach the prop colorScheme through from semanticHomeMenu -> semanticHomeMenu_Heatpump -> Heatpump_Tab3 -> Heatpump_Hygiene. It seems as nesting is somewhat depth limited. In this case i can hardcode the colorScheme with minor side effects.
- The same problem exits for some other props where i need the data to get the awaited functionality. This is an open problem i have to discuss with the community and maintainers to find the (my?) mistake or at least a solution.

## Needed prerequisites :
Besides the Items the ViessmannAPI delivers there are some proxy items needed :

