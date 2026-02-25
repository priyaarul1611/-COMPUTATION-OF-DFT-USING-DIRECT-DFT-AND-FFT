
# EXP 2 : COMPUTATION OF DFT USING DIRECT DFT AND FFT

# AIM: 
To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
**DISCRETE FOURIER TRANSFORM **
```
clc;
clear;
xn=[1 1 1 1 1 1 0 0];
n1=0:1:length(xn)-1;
subplot(3,1,1);
plot2d3(n1,xn);
xlabel('Time n');
ylabel('Amplitude xn');
title('Input Sequence');
j=sqrt(-1);
N=length(xn);
xk=zeros(1,N);
   for k=0:N-1
       for n=0:N-1
           xk(k+1)=xk(k+1)+xn(n+1)*exp((-j*2*%pi*k*n)/N);
   end    
end
disp(xk)
k1=0:1:length(xk)-1;
magnitude=abs(xk)
subplot(3,1,2);
plot2d3(k1,magnitude);
xlabel('frequency(Hz)');
ylabel('magnitude(gain)');
title('magnitude spectrum');
angle=atan(imag(xk),real(xk))
subplot(3,1,3);
plot2d3(k1,angle);
xlabel('frequency(Hz)');
ylabel('phase');
title('phase spectrum');
```
**FAST FOURIER TRANSFORM**
```
clc;
clear;
close;
xn=[1 1 1 1 1 1 0 0];
n1=0:1:length(xn)-1;
subplot(2,2,1);
plot2d3(n1,xn);
xlabel('time n');
ylabel('amplitude');
title('input sequence');
xk=fft(xn);
k1=0:1:length(xk)-1;
magnitude=abs(xk)
subplot(2,2,2);
plot2d3(k1,magnitude);
xlabel('frequency(Hz)');
ylabel('magnitude(gain)');
title('magnitude spectrum');

angle=atan(imag(xk),real(xk));
subplot(2,2,3);
plot2d3(k1,angle);
xlabel('frequency(Hz)');
ylabel('Phase');
title('phase spectrum');
y=ifft(xk);
n2=0:1:length(y)-1;
subplot(2,2,4);
plot2d3(n2,y);
xlabel('time n');
ylabel('amplitude');
title('inverse FFT of x(k)');
```
# CALCULATIONS: 
<img width="800" height="1000" alt="image" src="https://github.com/user-attachments/assets/84827aea-292d-47c9-9eb9-75da45809aa8" />
<img width="800" height="1000" alt="image" src="https://github.com/user-attachments/assets/95016e24-09dc-4b71-8ea0-5c7c4b8c7d69" />
<img width="800" height="1000" alt="image" src="https://github.com/user-attachments/assets/b10d0767-7bd1-4001-8977-2e54ff79ccf8" />

# SAMPLE OUTPUT: 
<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/a95429b3-f869-4809-8802-9e99931ef2b9" />
<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/6c001b1f-9c37-49df-aaa0-f9dc5aa6543e" />



# RESULT: 
