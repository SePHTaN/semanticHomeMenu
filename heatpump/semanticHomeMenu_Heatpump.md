# The different Parts of the Widget
This Widget is intended for use with a Viessmann Vitocal 250A heatpump.
It is trying to bring the same functionality to Openhab that the original ViCareAPP from Viessmann has.

## The Widget itself

<img alt="Heatpump" src="/heatpump/Images/Heatpump.png" width="inherit"></img>  
The Widget shows some Item-States for a quick overview, also the Button **Schnell Wahlen** (Fast Choices) for some heatpump settings that might be needed more often.  
![Grafik](https://api.iconify.design/mdi/outside-temperature.svg?color=`#000000`) Shows the outside temperature beneath.  
<img src="/heatpump/Icons/fan-circled-on.svg" width="16px"></img>  Indicates that the heatpump is running when animated.  
![Grafik](https://api.iconify.design/mdi/defrost.svg?color=`#000000`)  When colored $${\color{green}green}$$ the outdoor unit is defrosting.  
![Grafik](https://api.iconify.design/mdi/radiator-coil.svg?color=`#000000`)  When colored $${\color{green}green}$$ the heatpump is in heating mode.  
![Grafik](https://api.iconify.design/material-symbols-light/water-pump-rounded.svg?color=`#000000`)  When colored $${\color{green}green}$$ indicates that the heating circulation pump is running.  
![Grafik](https://api.iconify.design/lucide-lab/faucet.svg)  When colored $${\color{green}green}$$ the heatpump is in DomesticHotWater mode.  
![Grafik](https://api.iconify.design/material-symbols-light/water-pump-rounded.svg?color=`#000000`)  When colored $${\color{green}green}$$ indicates that the DHW circulation pump is running.  
![Grafik](https://api.iconify.design/bx/shower.svg?color=`#000000`)  When colored $${\color{green}green}$$ DomesticHotWater one time charge function is activ.  
![Grafik](https://api.iconify.design/mdi/heart.svg?color=`#000000`)  When colored $${\color{green}green}$$ Forced last from schedule function (Partymode) is activ .  
![Grafik](https://api.iconify.design/ri/suitcase-fill.svg?color=`#000000`)  When colored $${\color{orange}orange}$$ holiday program is pending, when $${\color{green}green}$$ it is activ.  
![Grafik](https://api.iconify.design/mdi/sofa-single.svg?color=`#000000`)  When colored $${\color{orange}orange}$$ holidayAtHome is pending, when $${\color{green}green}$$ it is activ.  

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

Tab4 currently visualizes some of the available consumption and production data :  
1. Chart
 - Produced amount of heat for DHW and Heating for the actual and last year.
 - Electricity consumption for this for the actual and last year.
2. Chart
 - Eletricity consumption for DHW, Heating and Total for the last twelve months.
 - SCOP for DHW, Heating and Total for the last year.
 - Eletricity consumption for DHW, Heating and Total since beginning of the year.

Unfortunatly the datapoints for the last two months aren't always exact as Viessmann doesn't delivers this data on the same time basis as other datapoints. Roughly only every 14 days those get updated.  

# Installation and Setup
At the moment only copying and pasting the different parts of the heatpump-widget is available.  
The yaml's for the widget parts, as the rules, aren't the newest version as of 13.02.26 but will get updated in the next days.  
I will need some days to get everything updated to be useable.  

## Needed prerequisites :

### Textural definition of Proxy-Items
Besides the Items the Viessmann-Binding delivers there are some proxy items needed :  
```
// This is as an example from my own Openhab the Group of the heatpump
Group     ViessmannWaermepumpe     "Viessmann Vitocal 250A"     <pump>     (gKeller_Hausgeraete_Keller)     [HeatPump]
Type      Name                                     Label                             Icon     Parent-Group             Semantic Point/Property  Command / State Description
// Proxy items needed for schedule management :
String    ViessmannWaermepumpe_art                 "Schedule Art in Bearbeitung"              (ViessmannWaermepumpe)   [Control, Info]
String    ViessmannWaermepumpe_m1                  "Schedule Mode Zeitpaar 1"                 (ViessmannWaermepumpe)   [Control, Mode]          { commandDescription=" " [options="comfort=Komfort,normal=Normal,reduced=Reduziert"] }
String    ViessmannWaermepumpe_m2                  "Schedule Mode Zeitpaar 2"                 (ViessmannWaermepumpe)   [Control, Mode]          { commandDescription=" " [options="comfort=Komfort,normal=Normal,reduced=Reduziert"] }
String    ViessmannWaermepumpe_m3                  "Schedule Mode Zeitpaar 3"                 (ViessmannWaermepumpe)   [Control, Mode]          { commandDescription=" " [options="comfort=Komfort,normal=Normal,reduced=Reduziert"] }
String    ViessmannWaermepumpe_m4                  "Schedule Mode Zeitpaar 4"                 (ViessmannWaermepumpe)   [Control, Mode]          { commandDescription=" " [options="comfort=Komfort,normal=Normal,reduced=Reduziert"] }
Number    ViessmannWaermepumpe_p1                  "Schedule Pos Zeitpaar 1"                  (ViessmannWaermepumpe)   [Control, Position]
Number    ViessmannWaermepumpe_p2                  "Schedule Pos Zeitpaar 2"                  (ViessmannWaermepumpe)   [Control, Position]
Number    ViessmannWaermepumpe_p3                  "Schedule Pos Zeitpaar 3"                  (ViessmannWaermepumpe)   [Control, Position]
Number    ViessmannWaermepumpe_p4                  "Schedule Pos Zeitpaar 4"                  (ViessmannWaermepumpe)   [Control, Position]
DateTime  ViessmannWaermepumpe_te1                 "Schedule Endzeit 1"              <time>   (ViessmannWaermepumpe)   [Control, Timestamp]
DateTime  ViessmannWaermepumpe_te2                 "Schedule Endzeit 2"              <time>   (ViessmannWaermepumpe)   [Control, Timestamp]
DateTime  ViessmannWaermepumpe_te3                 "Schedule Endzeit 3"              <time>   (ViessmannWaermepumpe)   [Control, Timestamp]
DateTime  ViessmannWaermepumpe_te4                 "Schedule Endzeit 4"              <time>   (ViessmannWaermepumpe)   [Control, Timestamp]
DateTime  ViessmannWaermepumpe_ts1                 "Schedule Startzeit 1"            <time>   (ViessmannWaermepumpe)   [Control, Timestamp]
DateTime  ViessmannWaermepumpe_ts2                 "Schedule Startzeit 2"            <time>   (ViessmannWaermepumpe)   [Control, Timestamp]
DateTime  ViessmannWaermepumpe_ts3                 "Schedule Startzeit 3"            <time>   (ViessmannWaermepumpe)   [Control, Timestamp]
DateTime  ViessmannWaermepumpe_ts4                 "Schedule Startzeit 4"            <time>   (ViessmannWaermepumpe)   [Control, Timestamp]

// Proxy items needed for the hygiene functionality :
Number    ViessmannWaermepumpe_hygieneStartHour    "Proxy-Item für die Start-Stunde"          (ViessmannWaermepumpe)   [Point]
Number    ViessmannWaermepumpe_hygieneStartMinute  "Proxy-Item für die Start-Minute"          (ViessmannWaermepumpe)   [Point]
String    ViessmannWaermepumpe_hygieneRhythm       "Proxy-Item für den Rhytmus"      <text>   (ViessmannWaermepumpe)   [Setpoint]
String    ViessmannWaermepumpe_hygieneWeekday      "Proxy-Item für den Wochentag"    <text>   (ViessmannWaermepumpe)   [Point]                  { stateDescription=" " [options="Mon=Montag,Tue=Dienstag,Wed=Mittwoch,Thu=Donnerstag,Fri=Freitag,Sat=Samstag,Sun=Sonntag"] }
```
Those are an option that i might introduce again because using the items for Start/End Date of the holiday/holidayAtHome Programs do introduce latency due to API-Calls when trying to change the date. Proxy-Items don't have this problem.
```
// Proxy items needed for holiday / holidayAtHome functionality :
String    ViessmannWaermepumpe_holidayStart        "Holiday Start-Datum Proxy"                (ViessmannWaermepumpe)   [Setpoint, Timestamp]
String    ViessmannWaermepumpe_holidayEnde         "Holiday Ende-Datum Proxy"                 (ViessmannWaermepumpe)   [Point, Timestamp]
```
One thing to mention : I started this widget some time ago and since then some things changed with the Viessmann-Binding from @rogrun !  
If you are **naming your Group** for your heating device **differently** then me (ViessmannWaermepumpe) then the **name for the proxy-items have to be named accordingly** !  
**ViessmannWaermepumpe_m1** would change to **MyHeatpump_m1** if you name your Group **MyHeatpump**.  

### Needed Rules
Also these Rules are needed :  

| Rule ID | Label | Description |
|---------|-------|-------------|
| [Heatpump_Generate_Power_JSONs](/heatpump/Rules/Heatpump_Generate_Power_JSONs) | Heatpump Generate JSON String Items for Power-Month Items | Erzeugt JSON-Strings der Power Consumption Month Items von DHW,Heating,Total |
| [Heatpump_Hygiene](/heatpump/Rules/Heatpump_Hygiene) | Heatpump Hygiene | Belegt die Proxy.Items und speichert zurück in die Items |
| [Heatpump_Populate_ProxyItems](/heatpump/Rules/Heatpump_Populate_ProxyItems) | Heatpump Populate Proxy Items for schedule setter | Belegt die Items für Start-/End- Zeit, Mode und Pos |
| [Heatpump_fastChoice](/heatpump/Rules/Heatpump_fastChoice) | Heatpump Schnell-Wahlen | Setzt die diversen Datenpunkte aus den Schnell-Wahlen |
| [Heatpump_Update_Schedule](/heatpump/Rules/Heatpump_Update_Schedule) | Heatpump Update Schedule | Entfernt, ändert oder ergänzt Zeitpaare baut den JSON String und schickt ihn ans Item |


To install these rules, go to Rules in the MainUI press the plus in the bottom right corner to add a rule.  
Name the Rule ID according to the table above this is important !  
Otherwise the rule won't be found if called, for label and description you can change to what ever you want or is more comprehensive for you.  
Now click on the Code Tab and overwrite everything with the code of the rule that you get if you follow the link in the table.  

### Icons and Images
This widget uses some icons not available from openhab, frameworkF7, material or iconify.  
  
| Icons / Images | Where to put |
|-------|--------------|
| pump-on, pump-off, fan-circled, fan-circled-on, heizstab, heizstab-on, heizstab-off, 3wv, 3wv-dhw, 3wv-heat, compressor, compressor-on, compressor-off, 4wv-heat, 4wv-cool, betrieb-evulock, betrieb-heat, betrieb-cool, ww-zirkulation-w, limit-upper, limit-lower, ww-drop, ww-heat | openhab-conf icons/classic |
| Waermepumpe.svg, heat1.svg, heat2.svg, heat3.svg, ww-heat1.svg, ww-zirkulation-w.svg, zirkulation-rounded.svg | openhab-conf html/waermepumpe |

All icons are .svg files. In the table above i only listed the name ! So pump-on effectively is the file pump-on.svg.

### The Widget parts
To add them follow the normal procedure to add a widget in _developer tools/widgets_.  
Press the plus button in the bottom right corner and overwrite everything with the contents of the according *.yaml file.

If everything gone right, you don't made mistakes with the naming, the Widget should be ready for use.
