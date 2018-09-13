# MobileNets-SSD-Object-Detection

MobileNets, as the name suggests, are neural networks constructed for the purpose of running very efficiently (high FPS, low memory footprint) on mobile devices. MobileNets has 3 steps:
1. Perform a separable depthwise convolution.
2. Use Width Multiplier to reduces the size of the input/output channels, set to a value between 0 and 1.
3. Use Resolution multiplier to reduces the size of the original input, set to a value between 0 and 1.

These 3 techiniques reduce the size of cummulative parameters and therefore the computation required. 

