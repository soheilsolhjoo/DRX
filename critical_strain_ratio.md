
```matlab
clear; close all;

x = linspace(0,1,101);
x(1) = [];

rc(:,1) = (sqrt(1-x)+x-1)./x;
rc(:,2) = 1-(2-x+sqrt((1-x).*(5-x))).^(-1/2);
rc(:,3) = 2/pi*atan(sqrt(1-x));

figure; hold on;
xlabel(' $0 < v \leq 1$ ','interpreter','latex') 
ylabel(' $R_\mathrm{c}$ ','interpreter','latex') 
plot(x,rc(:,1),'b-','DisplayName','ES-7', 'LineWidth', 1)
plot(x,rc(:,2),'r:','DisplayName','S-10', 'LineWidth', 1.5)
plot(x,rc(:,3),'k--','DisplayName','S-12', 'LineWidth', 1)
ylim([0,1]);
hl = legend('show');
set(hl, 'Interpreter','latex')
HD_g_figstyle
```

![figure_0.png](critical_strain_ratio_media/figure_0.png)

```matlab
v1 = 3; rc(:,4) = 1/v1*atanh(sqrt((1-x)./(1+x)));
v1 = 10; rc(:,5) = 1/v1*atanh(sqrt((1-x)./(1+x)));

v1 = -3; rc(:,6) = (-v1*x).^(-1./x);
v1 = -10; rc(:,7) = (-v1*x).^(-1./x);

figure; hold on;
xlabel(' !!!EQ_3!!! ','interpreter','latex') 
ylabel(' !!!EQ_2!!! ','interpreter','latex') 
plot(x,rc(:,4),'go--','DisplayName','S-14  !!!EQ_5!!! ', 'LineWidth', 1,'MarkerSize',3)
plot(x,rc(:,5),'g<--','DisplayName','S-14  !!!EQ_6!!! ', 'LineWidth', 1,'MarkerSize',3)
plot(x,rc(:,6),'r-','DisplayName','CFC-14  !!!EQ_7!!! ', 'LineWidth', 1,'MarkerSize',3,'Marker','square')
plot(x,rc(:,7),'r>-','DisplayName','CFC-14  !!!EQ_8!!! ', 'LineWidth', 1,'MarkerSize',3)
ylim([0,1]);
hl = legend('show');
set(hl, 'Interpreter','latex')
HD_g_figstyle
```

![figure_1.png](critical_strain_ratio_media/figure_1.png)
