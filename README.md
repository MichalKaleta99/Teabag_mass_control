# Teabag_mass_control - R Twining and Company Sp. z o.o.
Teabag weight and packaging tare control system made for R Twining and Company Sp. z o.o.

# Copyrights

Due to copyrights of the company in which I worked I assume that I can not paste whole project at public repository.
Moreover in a project that was written in Tia Portal v16 there were sensitive data such as ip addresses of the drivers and scales. That's why I made up my mind not to insert the project here.

# Short project description

The goal of the project was to enable machine operators to weigh the content of one teabag and to carry out the packaging tare. Then PLC had to check if the measurement was good (was within tolerance from imposed mass setpoint) or bad (was out of tolerance).

In order to weigh the components, I used a Radwag scales. Every machine producing teabags had it's own scale. The total number of machines (and also scales) was 85 - algorithm (and also called function with it) was the same for all of them.

# Communication (SCADA, Scale, another PLCs)

I used a TCP/IP communication to collect data from the Radwag scales where PLC used in project (S7-1500) was slave and the scale was a master. Every scale had its own unique IP adress what of course was necessary to read data properly.

Using built-in Siemens functions i performed a data exchange with existing yet PLCs - both of them were S7-300. I read from them physical buttons (Weigh button and reset button) and I wrote to them enable bit concering the approval for the operation of the conveyor depending on whether the mass measurement was within the tolerance or not.

The whole system could be turned on and off from SCADA level.

# SQL - read and write data

Every machine always had its unique order so to get information about Order and assign it in PLC i had to read data from Twinings' SQL database (MS SQL). The data needed for my system was located in different tables so I had to combine them wisely. Reading was cyclical and took place every minute.

Customers need was that each measurement was saved to the database - after collecting data, besides HMI i had to save them to database.


# Visualization - HMI and lamp

To inform machine operators I used an HMI app written in C# (which was created before my system so i only had to exchange data with it) and also a signal lamp. Depending on the needs that operator had to do (taring, measuring, time expired etc.) the lamp flashed at different frequencies and application looked a little different - relevant information about an existing need was displayed at the screen.


# Training and instruction of use (manual)

At the end of the project I made a instruction of use which you can find in my repo. Factory for which I prepared the project locates itself in Poland so obviously instruction and algorithm is made in polish language.

Beyond the manual itself, to make that project as easy as possible for machine operators I performed a training about the control sytem - I listened and answered all possible questions and once everyone was familiar with system the project was done.

# Summary

The project itself has been fully completed and runned on the production line.



