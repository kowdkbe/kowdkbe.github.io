import numpy as np

import matplotlib.pyplot as pl

import matplotlib

import math

import random

 

row = 4

col = 4

 

N = 500

fs = 5

n = [2*math.pi*fs*t/N for t in range(N)]    # 生成了500个介于0.0-31.35之间的点

# print n

axis_x = np.linspace(0,3,num=N)

 

#频率为5Hz的正弦信号

x = [math.sin(i) for i in n]

pl.subplot(121)

pl.plot(axis_x,x)

pl.title(u'5Hz')

pl.axis('tight')

 


#频谱绘制

xf = np.fft.fft(x)

xf_abs = np.fft.fftshift(abs(xf))

axis_xf = np.linspace(-N/2,N/2-1,num=N)

pl.subplot(122)

pl.title(u'5Hz')

pl.plot(axis_xf,xf_abs)

pl.axis('tight')

 



 

pl.show()