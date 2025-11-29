# EXP 1 : Linear and Circular Convolution

## AIM: 

 To perform Linear and Circular Convolution for two given sequence using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (Linear Convolution): 
```
clc;
clear;

x = [1 1 1 1];
h= [1 2 3 4];

m = length(x);
n = length(h);
a=0:1:m-1;
b=0:1:n-1;
subplot(3,1,1);
plot2d3(a,x);
xlabel('Time');
ylabel('Amplitude');
title ('Graphical Representation of Input Signal X');

subplot(3,1,2);
plot2d3(b,h);
xlabel('Time');
ylabel('Amplitude');
title ('Graphical Representation of Impulse Signal h');

for i=1: n+m-1
	conv_sum =0;
		for j=1:i
			if (((i-j+1) <= n)&(j <=m))
				conv_sum=conv_sum +x(j)*h(i-j+1);
			end;
			y(i) = conv_sum;
		end;
end;

disp (y,'Convolution Sum using Direct Formula Method = ')
subplot(3,1,3);
plot2d3(y)
title ('Graphical Representation of output Signal y');
```

## PROGRAM (Circular Convolution): 
```
clc;
clear;

 x=[1 1 1 1];
 n1=0:1:length(x)-1;
 subplot(3,1,1);
 plot2d3(n1,x);
 xlabel('time');
 ylabel('amplitude');
 title('input sequence');

 h=[1 2 3];
 n2=0:1:length(h)-1;
 subplot(3,1,2);
 plot2d3(n2,h);
 xlabel('time');
 ylabel('amplitude');
 title('impulse sequence');

 N1=length(x);
 N2=length(h);
 N=max(N1,N2);
 N3=N1-N2;
 if(N3>0)
     h=[h,zeros(1,N3)];
 else
     x=[x,zeros(1,abs(N3))];
 end

 disp(x)
 disp(h)

 for n=1:N
     y(n)=0;
     for i=1:N
         j=n-i+1;
         if(j<=0)
             j=N+j;
         end
        (n)=y(n)+x(i)*h(j);
    end
end

disp(y)

n=0:N-1;
subplot(3,1,3);
plot2d3(n,y);
xlabel('time');
ylabel('amplitude');
title('circular convolution');
```


## OUTPUT (Linear Convolution): 

<img width="1268" height="753" alt="image" src="https://github.com/user-attachments/assets/0fc66258-9afc-446c-8424-d5545b8d2eca" />

## OUTPUT (Circular Convolution):

<img width="744" height="593" alt="image" src="https://github.com/user-attachments/assets/cf20cbc0-c4ee-4bfb-a69d-cfdfc9bfaf8f" />


## RESULT: 
Thus, the linear convolution and circular convolution of the two given sequences were performed and its result was verified.
