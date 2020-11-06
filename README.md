# STM32开发套件项目规范

## 一、文件命名规范

根据项目的次数，命名该项目文件为“xxx_First”、“xxx_Second”

## 二、文件目录规范

<p align='center'>
<img src='pic\Snipaste_2020-11-06_17-02-52.png' title='images' style='max-width:600px'></img>
</p>



使用STM32CubeMX生成工程的配置文件，

在src中放代码文件中放代码，根据模块名，新建一个文件夹

<p align='center'>
<img src='pic\Snipaste_2020-11-06_17-35-22.png' title='images' style='max-width:600px'></img>
</p>



除此之外



<p align='center'>
<img src='pic\Snipaste_2020-11-06_19-44-47.png' title='images' style='max-width:600px'></img>
</p>





## 三、代码规范



```
/* Define to prevent recursive inclusion -------------------------------------*/
#ifndef __key_H
#define __key_H
#ifdef __cplusplus
 extern "C" {
#endif
	 
/* Doc ------------------------------------------------------------------*/
/*
文件名   : TIM.h
功能描述 : This file provides code for the configuration
           of the TIM instances.

# 参数设置介绍

## 1s

我们把时钟预分频器设置为 7200 - 1
则驱动计数器的时钟：CK_CNT = CK_INT / (71+1)= 0.01MHz
即计数器计数一次的时间等于： 1 / CK_CNT = 0.1ms
定时器设置自动重装载寄存器 ARR 的值设置为 10000 - 1
当计数器计数到 ARR 的值 10000 - 1 时，产生一次中断，
则中断一次的时间 为：1 / CK_CNT * (ARR+1) = 1s 

## 1ms

我们把时钟预分频器设置为 72 - 1
则驱动计数器的时钟：CK_CNT = CK_INT / (71+1)= 1MHz
即计数器计数一次的时间等于： 1 / CK_CNT = 1us
定时器设置自动重装载寄存器 ARR 的值设置为 1000 - 1
当计数器计数到 ARR 的值 1000 - 1 时，产生一次中断，
则中断一次的时间 为：1 / CK_CNT * (ARR+1) = 1ms 

## 1us

我们把时钟预分频器设置为 36 - 1
则驱动计数器的时钟：CK_CNT = CK_INT / (35+1)= 2MHz
即计数器计数一次的时间等于： 1 / CK_CNT = 0.5us
定时器设置自动重装载寄存器 ARR 的值设置为 2 - 1
当计数器计数到 ARR 的值 2 - 1 时，产生一次中断，
则中断一次的时间 为：1 / CK_CNT * (ARR+1) = 1us 
*/

/* Includes ------------------------------------------------------------------*/
#include "main.h"
#include "gpio.h"

/* Defines -------------------------------------------------------------------*/


/* Functions -----------------------------------------------------------------*/
uint8_t Key_Scan(GPIO_TypeDef* GPIOx,uint16_t GPIO_Pin);

#ifdef __cplusplus
}
#endif
#endif /*__ key_H */
```

