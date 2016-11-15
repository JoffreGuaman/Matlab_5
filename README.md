# Matlab_5

clear
%cambiamos los valore de 10 y -10 por 30 y -30 correspondientemente
nneg=-30:-1;
npos=1:30;
n=nneg;
Fnneg=(1./(j*n*pi)).*(-3*exp(-j*n*6*pi/7)+2*exp(j*n*2*pi/7)+exp(-j*n*12*pi/7));
n=npos;
Fnpos=(1./(j*n*pi)).*(-3*exp(-j*n*6*pi/7)+2*exp(j*n*2*pi/7)+exp(-j*n*12*pi/7));
F0=10/7;%funcion final
n=[nneg,0,npos];
Fn=[Fnneg,F0,Fnpos];
k=0;
%inicializa un ciclo repetitivo
for t=-1:.01:6
k=k+1;
fapprox(k)=sum(Fn.*(exp(j*n*2*pi*t/7)));
end
% fin del ciclo
t=-1:.01:6;
fexact=4*(t<=3)-2*(t>=3);
plot(t,fapprox,t,fexact)
