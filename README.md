# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
<img width="1181" height="1430" alt="image" src="https://github.com/user-attachments/assets/3652f231-d7d1-4c72-89ac-94ac408e1558" />
<img width="982" height="1600" alt="image" src="https://github.com/user-attachments/assets/e8f6e89e-c432-44ca-a63f-318c35fa3bc2" />

<img width="954" height="1280" alt="image" src="https://github.com/user-attachments/assets/dd46ef4d-1066-421e-beba-4a5cc7684186" />


## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
num=[10]

den=[0.1 0.7 1 0]

sys=tf(num,den)

[mag,phase,W]=bode(sys)

mag=squeeze(mag)

phase=squeeze(phase)

phase1=deg2rad(phase)

polarplot(phase1,mag,'linewidth',1.5)

grid on

[Gm Pm Wpc Wgc]=margin(sys)

if(Wpc>Wgc)
 disp('stable')
	
elseif(Wpc == Wgc)
disp('marginally stable')
	
else
    disp('unstable')
	
end
## Output:
<img width="1102" height="1028" alt="image" src="https://github.com/user-attachments/assets/3787b7ef-06a4-498d-bb1f-7ca2219037a3" />


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB.


Gain margin = 0.70


Phase Margin = -8.88


Gain crossover frequency = 3.75


Phase crossover frequency = 3.16


The system is unstable
