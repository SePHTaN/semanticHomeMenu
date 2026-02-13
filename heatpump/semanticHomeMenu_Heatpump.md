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
- Adding an extra time-phase is possible through the button **Neues Zeitpaar**

### Tab3 : DomesticHotWater and Zirculation Schedule, Hysterese and Hygiene Settings
<img alt="Heatpump Tab3 WW" src="/heatpump/Images/Heatpump_Tab3_WW.png" width="32%"><img alt="Heatpump Tab3 Zirk" src="/heatpump/Images/Heatpump_Tab3_Zirkulation.png" width="32%">

<img alt="Heatpump Tab3 Hysterese" src="/heatpump/Images/Heatpump_Tab3_Hysterese.png" width="32%"><img alt="Heatpump Tab3 Hygiene" src="/heatpump/Images/Heatpump_Tab3_Hygiene.png" width="32%">

### Tab4 : Energy Data
<img alt="Heatpump Tab4" src="/heatpump/Images/Heatpump_Tab4.png" width="inherit">

Tab4 currently visualizes some of the available consumption data :  
- Eletricity consumption for DHW, Heating and Total for the last twelve months.
- SCOP for DHW, Heating and Total for the last year.
- Eletricity consumption for DHW, Heating and Total since beginning of the year.
- Eventually i will extend with data of the produced heat for DHW, Heating and Total as those datapoints are available recently.

Unfortunatly the datapoints for the last two months aren't always exact as Viessmann doesn't delivers this data on the same time basis as other datapoints. Roughly only every 14 days those get updated.  

