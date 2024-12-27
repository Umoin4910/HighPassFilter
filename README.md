# High Pass Filter Circuit
**Author**: Moinuddin Ansari  

## Objective  
To design and simulate a High Pass Filter circuit for a given cutoff frequency of **1.5 kHz**.  

## Design  
A High Pass Filter is an RC circuit where a resistor and capacitor are connected in series. The input is applied across the series combination of the capacitor and resistor, while the output is taken across the resistor.  

The cutoff frequency (`f_c`) of the circuit is given by:

f_c = 1 / (2 * π * R * C)  

Assuming the value of the capacitor to be **8 nF**, we calculate the resistor (`R`) using the formula above by substituting the given cutoff frequency:  
R = **13.262 kΩ**

Hence, the time constant (`τ`) is calculated as:  

τ = R * C = **0.106 ms**

## Schematic in LTSpice  
The pulse waveform is used as the input. The **T(on)** of the pulse is determined by the time constant of the circuit. To achieve better results, **T(on)** is typically chosen as 10 times the time constant. The time period of the waveform is twice the value of **T(on)**. 

  <img width="611" alt="sche" src="https://github.com/user-attachments/assets/274541a3-10ac-489a-8dce-716d0ecaaa65" />



## Simulation Results
### Transient Response
Transient Analysis is performed using the command (`.tran 60m`) where the stop time **60m** is decided by the time period of input Pulse such that at least 3 to 4 pulse can be obsered on the input plot clearly.
            <img width="960" alt="trans" src="https://github.com/user-attachments/assets/4c4a44c7-99e8-4909-8684-7d93c748d1a9" />

Following Observation have been made by analyzing the Transient Response: 
   - At the rising edge of the input pulse, the output voltage exhibits a sharp positive peak due to the sudden change in the input signal.  
   - Similarly, at the falling edge of the input pulse, the output voltage shows a sharp negative peak.  
   - Between the rising and falling edges, the output voltage settles close to 0 V, indicating that the DC component of the input is blocked.

### AC Analysis
AC Analysis is performed using the command (`.ac dec 10 10 1gig`).
<img width="960" alt="ac" src="https://github.com/user-attachments/assets/6fea170a-99ef-4707-abc9-5574dc2cf5dd" />

From the transfer function graph above (Note: Vout/Vin is not plotted as Vin is already set to 1 as AC1), the cutoff frequency (f_c) is obtained as 1.5 kHz.
#
If you have any questions or need further clarification, don't hesitate to contact the me. 
Keep Learning Keep Hustling! 




