#A Linear-Integrated-Circuits

As a part of the subject in Linear Integrated Circuits Laboratory 4th semester,I have started doing the first experiment in the simulation using LT Spice Software.

Aim : 


1) The Common Source Amplifier 
 
As per the above given circuit, M1 is a 180nm nMOS with Vdd=1.8V, Vg=0.9V, Vs=0V, P=100uW with an Rd resistor.
Using power and voltage we can find the value of current i.e., P = V.I , so by solving this equation we get the current, I=5.55 × 10^-5 A. 
Now we have to find the Rd value using Vout = Vdd - (Id×Rd) by keeping the length and width as 180nm and 1um respectively.We know the value of Id theoretically and we know Vdd but we need find Vout.To find the Vout first we need to setup the circuit in the software then attach the library file of 180nm MOSFET i.e., tsmc018.lib after that by adjusting the values of length and width of MOSFET we can find Vout by running the simulation, run the simulation with DC opt pnt then we will get Vout. Finally by using all required values we found out the value of Rd as 2.764k ohm.
Now by setting the value of Rd we need to obtain the theoretical current by changing the length and width of the MOSFET.I got the desired current of the MOSFET at length of 180nm and width of 0.209um.