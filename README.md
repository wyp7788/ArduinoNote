# ArduinoNote
Arduino for maker/geek.

Arduino is open source platform. It,s a super friendly platform where makers can do anything they want to do


# Arduino语法Note【01】

**Arduino**是一款便捷灵活的开源电子平台。Arduino能通过各种各样的传感器感知环境，拥有灵活、易用的软件和硬件。本系列（**Arduino**语法Note）更多的是记录每个函数的功能及参数，同时还有一些偏底层的解释。本Note更多的是对Arduino官网文档的翻译，当然也会加一些自己的理解。

**Arduino** 编程语法主要由三部分组成：

* 函数  **functions**
* 数值  **values**
* 结构  **structure** 

## 一、Functions 函数

For controlling the Arduino board and performing computations. 函数用于控制 **Arduino**板执行运算。

### Digital I/O 数字输入、输出

1. **pinMode** Configures the specified pin to behave eieher as an input or an output. pinMode（）函数设置指定引脚的输入输出、模式。

   As of Arduino 1.0.1, it is possible to enable the internal pullup resistors with the mode `INPUT_PULLUP`. Additionally, the `INPUT` mode explicitly disables the internal pullups.  Arduino1.0.1另外（集成开发环境）版本以上，都支持

1. **digitalWrite**  Write a `HIGH` or `LOW` value to a digital pin. 将高电平或者是低电平写入到数字引脚。

   If the pin has been configured as an `OUTPUT` with `pinMode()` , its voltage will be set to the corresponding value: 5V (or 3.3V on 3.3 V  boards) for `HIGH`, 0 V (ground) for `LOW`.  如果数字引脚已经被`pinMode()` 函数设置为输出模式，将引脚设置为高电平的时候对应的引脚输出电压为5 V，低电平时候对应的引脚输出电压为0 V。（电源电压是3.3 V的 Arduino 开发板则对应数字引脚输出为3.3 V）

   If the pin is configured as an `INPUT`, `digitalWrite()` will enable (`HIGH`) or disable (`LOW`) the internal pullup on the input pin. It is recommended to set the `pinMode()` to `INPUT_PULLUP` to enable the internal pull-up resistor. 

   If you do not set the `pinMode()` to `OUTPUT`, and connect an LED to a pin, when calling `digitalWrite(HIGH)`, the LED may appear dim. Without explicitly setting `pinMode()`, `digitalWrite()` will have enabled the internal pull-up resistor, which acts like a large current-limiting resistor.　当调用

   **Syntax**　用法

   `digitalWrite(pin, value);`

   **Parameters** 函数参数

   `pin`: the Arduino pin number. Arduino 数字引脚号
   `value`: `HIGH` or `LOW`. 数值，高电平或低电平 

   **Return**

   Nothing 无返回值

   **Example code**

   `setup()、loop()`函数都是Arduino内置函数，必不可少，**`void`**关键字表示函数无返回值。

   ```c++
   void setup() {
     pinMode(13, OUTPUT);    // sets the digital pin 13 as output设置13号引脚为输出模式
   }
   
   void loop() {
     digitalWrite(13, HIGH); // sets the digital pin 13 on 把13号引脚设置为高电平（5V）
     delay(1000);            // waits for a second         延时、等待 1000毫秒
     digitalWrite(13, LOW);  // sets the digital pin 13 off 把13号引脚设置为高电平（0V）
     delay(1000);            // waits for a second          延时、等待 1000毫秒
   }
   ```

    **Note and Warnings**  

The analog input pins can be used as digital pins, referred to as A0, A1, etc. The exception is the Arduino Nano, Pro Mini, and Mini’s A6 and A7 pins, which can only be used as analog inputs. 模拟输入引脚也可被用于数字引脚，引脚编号为14<-->A0 etc... Arduino Nano, pro mini 的Ａ6，Ａ7引脚仅能作为模拟输入引脚。

3. **digitalRead** 

## 二、Values 数值







## 三、Structure 结构
