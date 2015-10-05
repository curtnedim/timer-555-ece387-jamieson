# Introduction #
The 555 timer has 3 modes of operation: astable, monostable, and bistable. Each mode comes with a set of unique applications.


# Details #
In astable mode, the chip provides as an highly regular and stable oscillator with an duty cycle and period configurable by the adjustment of only 2 circuit elements; a resistor and capacitor. The capacitor will charge to 2/3 the applied Vcc according to the familiar RC equation V(t)=V (1-e<sup>(-t/RC)</sup>) and discharge to 1/3 Vcc according to V(t)=V e<sup>(-t/RC)</sup>. Knowing this information, users of any skill level can manipulate the equations and develop their applications with little difficulty. As a clock the oscillator can achieve speeds as high as the kHz range.

Various Arduino models can also provide highly stable oscillation using the analogWrite(#) function. The devices are typically capable of providing oscillations at frequencies anywhere from 500 to 1000Hz. While the duty cycle is variable from 0-100% in divisions of 1/255 of a % (example analogWrite(128) yields a 50% duty cycle), its important to note the frequency is not adjustable. Depending on the model and output pin selected it will be 490Hz or 980Hz.

**Eliminate this code, increase efficiency and free pins with a simple 555 timer:**

analogWrite(pin label, duty-cycle number);

The monostable mode allows a trigger event to effect a pulse or high output for an adjustable length of time (on the order of milliseconds to many minutes). Again the delay can be accomplished with a simple RC combination that is calculable with the trivial RC charge/discharge time equations. After the capacitor has returned to the 2/3 threshold, the output will return to its single "stable" state.

Arduino models can easily perform event-triggered, time-delayed output changes and can do so on multiple pins. However, the practicality of designating pins for the task and initiating delays in the software is questionable for complicated projects.

**Eliminate this code, increase efficiency, and free pins with a simple 555 timer:**

if (event){

digitalWrite(pin label, HIGH);

delay(1000);

digitalWrite(pin label, LOW);

}

Finally, the bistable mode allows the chip to maintain a stable output (HIGH or LOW) until a trigger event causes the output to switch from HIGH to LOW or from LOW to HIGH. This mode of operation can be achieved with **no external circuit elements**. It can be used to indicate the status of externals that might exist in any one of two states or to provide control signals.

The Arduino can sense trigger events and update the state of outputs easy enough. The cost is a pair of pins and a few clock cycles. But depending on the application, meeting certain specifications may lead to a complexity in the software that might be relieved by simplicity in hardware. The following link is an example of code attempting to simulate a debounced switch; notice the long, complicated code accomplishing the simple task.

**Eliminate this code, increase efficiency, and free pins with a simple 555 timer**

**http://arduino.cc/en/Tutorial/Switch#.Uw5_9ct3sqQ**
