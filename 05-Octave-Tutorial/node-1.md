### Plotting Data

```
>> t = [0:0.01:0.98];
>> y1 = sin(2*pi*4*t);
>> plot(t, y1);
```

<img src="./img/01.png" width="450px"/>

- `hold on;` 保留住本图，下次画图在本图基础上画。

```
>> plot(t, y1);
>> hold on;
>> y2 = cos(2*pi*4*t);
>> plot(t, y2, 'r');
>> xlabel('time')
>> ylabel('value')
>> legend('sin', 'cos')
>> title('my plot')
>> cd 'E:';
>> print -dpng 'test.png'
```

<img src="./img/02.png" width="450px"/>

- `close` 关闭plot窗口

还可以用数字来标识图，下面的命令会打开两个plot窗口。

```
>> figure(1); plot(t, y1);
>> figure(2); plot(t, y2);
```

- `subplot` 将一个plot窗口分为两个子图，具体用法如下。

```
>> subplot(1, 2, 1); % 将plot窗口分为一个1x2的grid，并选择第一个子图
>> plot(t, y1);
>> subplot(1, 2, 2); % 选择第二个子图
>> plot(t, y2);
```

<img src="./img/03.png" width="450px"/>

- `axis([0.5 1 -1 1])` 设置精度。矩阵前两个元素为X轴的范围，后两个为Y的范围。

下面的例子接上面的，还是选择的第二个子图，设置了第二个子图的X、Y轴的范围。

<img src="./img/04.png" width="450px"/>

- `clf` 清空plot窗口

- `imagesc()` 根据矩阵A中每个元素的值的大小生成一个直观的颜色Grid，例子如下

```
>> A = magic(5);
>> imagesc(A); % 生成的图为彩色的
>> imagesc(A), colorbar, colormap gray; % 生成的图为灰色的，并带有colorbar。注意此处为用逗号分隔的命令链，相当于一次执行了三个命令
>> imagesc(magic(15)), colorbar, colormap gray;
```

<img src="./img/05.png" width="450px"/>
<img src="./img/06.png" width="450px"/>
<img src="./img/07.png" width="450px"/>
