# Teabag_mass_control - R Twining and Company Sp. z o.o.
Teabag weight and packaging tare control system

# Short project description

The goal of the project was to enable machine operators to weigh the content of one teabag and to carry out the packaging tare.

In order to weigh the components, I used a Radwag scales. Every machine producing teabags had it's own scale. The total number of machines (and also scales) was 85 - algorithm (and also called function with it) was the same for all of them.

I used a TCP/IP communication to collect data from the Radwag scales where PLC used in project (S7-1500) was slave and the scale was a master.
