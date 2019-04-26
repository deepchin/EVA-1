# Assignment 1B

# Questions

1. What are Channels and Kernels (according to EVA)?

    Kernels are feature extractors and channels are groups of the same or similar features.  

2. Why should we only (well mostly) use 3x3 kernels?
    1. Its computationally more efficient to use 3x3 kernels in the current hardware on the market. 
    2. One can achieve a subset of higher kernel size convolutions ( 5x5, 7x7, ... ) with a series of 3x3 convolutions.
    3. Using higher size kernels implies the model has more variables and they need to computed from the data. More variables would mean one might need more data and/or time to train the model. Hence from a practical perspective simpler models with lesser variables are preferred. Given one could achieve a subset of 5x5 or 11x11 etc. kernels using a 3x3 kernel, it all the more makes sense to use a 3x3 kernel with just 9 parameters instead of a higher order kernel with quadratically more number of variables.
    <br><br>

3. How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)
    <br><br>With every 3x3 convolution the image size drops by 2 pixels in both width and height. To go from 199x199 to 1x1 we need to drop in size by 198 pixels in both width and height. This would happen in 198/2  = 99 steps. The sequence of image sizes after every 3x3 convolution would be as follows:

    step-0: (199,199)
    <br>step-1: (197,197)
    <br>step-2: (195,195)
    <br>step-3: (193,193)
    <br>step-4: (191,191)
    <br>step-5: (189,189)
    <br>step-6: (187,187)
    <br>step-7: (185,185)
    <br>step-8: (183,183)
    <br>step-9: (181,181)
    <br>step-10: (179,179)
    <br>step-11: (177,177)
    <br>step-12: (175,175)
    <br>step-13: (173,173)
    <br>step-14: (171,171)
    <br>step-15: (169,169)
    <br>step-16: (167,167)
    <br>step-17: (165,165)
    <br>step-18: (163,163)
    <br>step-19: (161,161)
    <br>step-20: (159,159)
    <br>step-21: (157,157)
    <br>step-22: (155,155)
    <br>step-23: (153,153)
    <br>step-24: (151,151)
    <br>step-25: (149,149)
    <br>step-26: (147,147)
    <br>step-27: (145,145)
    <br>step-28: (143,143)
    <br>step-29: (141,141)
    <br>step-30: (139,139)
    <br>step-31: (137,137)
    <br>step-32: (135,135)
    <br>step-33: (133,133)
    <br>step-34: (131,131)
    <br>step-35: (129,129)
    <br>step-36: (127,127)
    <br>step-37: (125,125)
    <br>step-38: (123,123)
    <br>step-39: (121,121)
    <br>step-40: (119,119)
    <br>step-41: (117,117)
    <br>step-42: (115,115)
    <br>step-43: (113,113)
    <br>step-44: (111,111)
    <br>step-45: (109,109)
    <br>step-46: (107,107)
    <br>step-47: (105,105)
    <br>step-48: (103,103)
    <br>step-49: (101,101)
    <br>step-50: (99,99)
    <br>step-51: (97,97)
    <br>step-52: (95,95)
    <br>step-53: (93,93)
    <br>step-54: (91,91)
    <br>step-55: (89,89)
    <br>step-56: (87,87)
    <br>step-57: (85,85)
    <br>step-58: (83,83)
    <br>step-59: (81,81)
    <br>step-60: (79,79)
    <br>step-61: (77,77)
    <br>step-62: (75,75)
    <br>step-63: (73,73)
    <br>step-64: (71,71)
    <br>step-65: (69,69)
    <br>step-66: (67,67)
    <br>step-67: (65,65)
    <br>step-68: (63,63)
    <br>step-69: (61,61)
    <br>step-70: (59,59)
    <br>step-71: (57,57)
    <br>step-72: (55,55)
    <br>step-73: (53,53)
    <br>step-74: (51,51)
    <br>step-75: (49,49)
    <br>step-76: (47,47)
    <br>step-77: (45,45)
    <br>step-78: (43,43)
    <br>step-79: (41,41)
    <br>step-80: (39,39)
    <br>step-81: (37,37)
    <br>step-82: (35,35)
    <br>step-83: (33,33)
    <br>step-84: (31,31)
    <br>step-85: (29,29)
    <br>step-86: (27,27)
    <br>step-87: (25,25)
    <br>step-88: (23,23)
    <br>step-89: (21,21)
    <br>step-90: (19,19)
    <br>step-91: (17,17)
    <br>step-92: (15,15)
    <br>step-93: (13,13)
    <br>step-94: (11,11)
    <br>step-95: (9,9)
    <br>step-96: (7,7)
    <br>step-97: (5,5)
    <br>step-98: (3,3)
    <br>step-99: (1,1)