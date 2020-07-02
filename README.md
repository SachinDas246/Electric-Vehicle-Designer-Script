Electric-Vehicle-Designer-Script

Inshort : This is a python script which can be used for calculating the parameters for an ev
The story of this started as we joined in an ev design Competition which we were unable to submit on time due to lack of resources for an ev design.so we publish this script which not only allows you to do the design faster but also how it works.


For beginners in ev field ,the design part is not so friendly. So here we have created a python script that can do whole design in matter of seconds.

Note this only basic calculation for ev .

# Getting Started

Note : For faster tuning of the parameters and better understanding we have build ipython file which can be directly opended in google colab using link: [https://colab.research.google.com/drive/1UTv94fMMKu0cdnbi8fbHHlNgJ3YXLsNN?usp=sharing](https://colab.research.google.com/drive/1UTv94fMMKu0cdnbi8fbHHlNgJ3YXLsNN?usp=sharing)

## Converter Functions :

These are some converter functions for better understanding.And is not considered that you need complete under standing of this.

1. Rpm\_to\_mpers(rpm,radius): call this function with rpm and radius to convert RPM to m/s

2.mpstokmh(mps):Call this function with m/s value to convert to Km/Hr

3.kmhtomps(kmh):Call this function with Km/Hr value to convert it to m/s

## Vehicle Data

1. Acceleration : This value represent the acceleration required for the ev , Normally EV have an acceleration of 0-100 in 8 seconds so default value is 3.4722225 m/s^2

2. Design Speed : This is the speed at which our vehicle is designed to run , NOTE that this value is not the maximum speed or the minimum speed insted it is the speed at which the vehicle is tested [in the conditions area]

By default the value is 150 #km/h

3.Total\_Mass\_of\_Vehicle : This is the total mass ( Not Weight ) of vehicle in Kg

defaults value : 1000 Kg

4. Radius\_Of\_Wheel : Radius of wheel of the Ev (Not Diameter ) in meter

Default value : 0.203 m

5. Coefficient\_of\_rolling\_resistance Cr : It is the Rolling resistance factor for the Ev due to friction . This can be found from the [Mechanical Engineer&#39;s Data Handbook](https://amzn.to/3inUNzp) or from Search engines here are some values . Default Value : 0.1

| Driving Surface | Cr |
| --- | --- |
| New Asphalt/Concrete | 0.01 |
| Worn Asphalt/Concrete | 0.02 |
| New Small Cobbles | 0.01 |
| Worn Large Cobbles | 0.03 |
| Rolled New Gravel | 0.02 |
| Loose Worn Gravel | 0.04 |
| Medium Hard Soil | 0.08 |
| Sand | 0.1 - 0.2 |

6. Drag\_Coefficient Cd : Aerodynamic drag coefficient of the vehicle\

Default value : 1.5 , This can be found from the [Mechanical Engineer&#39;s Data Handbook](https://amzn.to/3inUNzp) or from Search engines here are some values .

| Vehicle | Cd |
| --- | --- |
| Sports Car with Sloping Rear | 0.2 - 0.3 |
| Saloon with Stepped Rear | 0.4 - 0.5 |
| Open Top Convertible | 0.6 - 0.7 |
| Bus | 0.6 - 0.8 |
| Truck | 0.8 - 1.0 |
| Motorbike &amp; Rider | 1.8 |
| Flat Plate (face on to flow) | 1.2 |
| Long Streamlined Body | 0.1 |
| Sphere | 0.47 |

7. Front\_Area\_of\_Vehicle : Front Area of your vehicle ie heigh\*width \* 0.9

default value : 3 m^2

8. Air\_Density : Density of the air in the region

Default value : 1.2 kg/m^3

9. Maximum\_Climbing\_Angle : Maximum angle at which the vehicle can climb

default value : 0 Degree

Running this block will get you the Force and Torque for the vehicle in Newton and Newton Meter.

## Motor Parameters :

These are the values of the motor you should select. For comparison of selecting motor you can compare the torque of the motor with the require torque in above result , You can choose motor with lower or higher torque but according to that value a gear ratio will be calculate which affects the rpm of the motor .

1.Motor\_Torque : this is the toque of the motor

default value : 234.5565 Newton Meter

2. Motor\_Rpm : RPM of the chosen motor

default value : 8000 RPM

3. Motor\_KW(Power) : KW of the chosen motor

default value : 35 KW

4. Motor\_Voltage : Voltage of the chosen motor

default value : 125 V

Running this block will get you the Gear Ratio and Speed for the vehicle in m/s . Note this is the maximum speed and you have to choose the motor such that your maximum speed is greater than designed speed.

## Conditions :

These are the condition your vehicle should pass.

1. Distance : this is the distance your vehicle should run with a single full charge.

Default value : 300000 Meter

2. Additional\_time : this is the additional time which should be added to time it requires to complete the condition distance. [During calculation of power requirement the time for completing the distance is calculated using the designed\_speed , But it will not be possible for a car to run at constant speed , so inorder to reduce the error we consider an additional time]

default value : 0 seconds

Running this block will get you

• the Time required to complete the distance

• and power to do it.

## Battery Calculation :

This area deals with calculation of the battery for the vehicle . These values depend on the parameters of the battery you have chosen .

1. Ah\_of\_Each\_cell : This is the Ah rating of cell you have chosen [Higher the rating lower the number of strings]

default value:=3.5 Ah

2. Voltage\_of\_Each\_Cell : This is the Voltage of the cell you havechosen . [higher the value lower the value of battery in each string]

Default Value : 3.7 V

3. Useable\_Percentage : Percentage of battery that can be used before considered as empty.

[Normally in ev we wont draw the whole power of the battery because it can significantly decrease the lifetime of the battery instead we use only a part of the batter like 20%]

Default value : 0.2 percent(here the vehicle show Batter empty when the battery is at 80%)

## Running this block will get you the

• no of cells in each string ,

• no of Strings

• Total no of cells.

Make sure that the weight of cell can be included in the total mass of the vehicle .

This desing considers some parameter to the limit so that your ev will be more and efficient if you consider factors like regrenerative breaking.

## And the final result

I know most of you have got an undesireable result at first , you can tune the parameters to find able find the most efficient and powerful design , this is what currently Engineering and Researcher are trying to solve , And some of the companies like TESLA has already solved to some extend .But these technologies are not avaialbe to us . So our design won&#39;t be that much efficient.

But using this program with full control in your hand I give you the ability to come up with a powerful design .

Thanks for trying out my project:
I Am not an expert in this area so if there is any error in the code please do report.
Sachin Das 246 : )
