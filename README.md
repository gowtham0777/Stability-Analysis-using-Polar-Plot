# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
<img width="516" height="861" alt="image" src="https://github.com/user-attachments/assets/d4101516-78d6-450b-bdf4-3e0d321fa377" />
<img width="539" height="857" alt="image" src="https://github.com/user-attachments/assets/fc351335-2fd0-468e-92cd-a6c1889c3422" />






## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
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
```

## Output:
<img width="702" height="629" alt="image" src="https://github.com/user-attachments/assets/84c7aa5d-d91d-4eb1-b4ae-7f410c8447f6" />



## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7<br>
Phase Margin = -8.88 <br>
Gain crossover frequency = 3.75 <br>
Phase crossover frequency = 3.16 <br>
The system is unstable
