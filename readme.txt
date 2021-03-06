This document is a manual for a Singular implementation for computing the localization of an ideal at a prime ideal.

The computer algebra system Singular can be downloaded from the following URL. 

https://www.singular.uni-kl.de

Please load the file "locprime.lib" on Singular: 

> LIB "locprime.lib";

The main command is the following. 

locPrime(I,P); a minimal primary decomposition of IK[X]_P\cap K[X] 
               where I is an ideal and P is a prime ideal.

Examples

Ex.1:
> ring r = 0,(x,y),dp;
> ideal i = x3,x2y;
> ideal p = x;
> locPrime(i,p);
_[1]=x2

Please load the file "aminor.lib" on Singukar for using adjacent-minor ideals:

> LIB "aminor.lib"

Ex.2:
> ring r = aminor_ring(2,3,4); 
> ideal i = aminor(2,3,4); 
> ideal p = x(24),x(23),x(22),x(21); // p is an isolated prime divisor of i
> i = std(i); 
> p = std(p);
> locPrime(i,p); // p is the p-primary component of i
_[1]=x(24)
_[2]=x(23)
_[3]=x(22)
_[4]=x(21)


Ex.3:
> ring r = aminor_ring(2,3,4); 
> ideal i = aminor(2,3,4); 
> ideal p = x(33),x(24),x(23),x(22),x(21),x(13),x(12)*x(31)-x(11)*x(32);  // p is an embedded prime divisor of i
> i = std(i); 
> p = std(p);
> locPrime(i,p);
[1]:
   _[1]=x(24)
   _[2]=x(23)
   _[3]=x(22)
   _[4]=x(21)
[2]:
   _[1]=x(33)
   _[2]=x(23)
   _[3]=x(13)
   _[4]=x(22)*x(31)-x(21)*x(32)
   _[5]=x(12)*x(31)-x(11)*x(32)
   _[6]=x(12)*x(21)-x(11)*x(22)
[3]:
   _[1]=x(33)
   _[2]=x(23)
   _[3]=x(22)
   _[4]=x(21)
   _[5]=x(13)
[4]:
   _[1]=x(33)^2
   _[2]=x(24)*x(33)-x(23)*x(34)
   _[3]=x(23)*x(33)
   _[4]=x(23)*x(32)-x(22)*x(33)
   _[5]=x(23)*x(31)-x(21)*x(33)
   _[6]=x(22)*x(31)-x(21)*x(32)
   _[7]=x(24)^2
   _[8]=x(23)*x(24)
   _[9]=x(23)^2
   _[10]=x(22)*x(23)
   _[11]=x(21)*x(23)
   _[12]=x(14)*x(23)-x(13)*x(24)
   _[13]=x(13)*x(23)
   _[14]=x(22)^2
   _[15]=x(21)*x(22)
   _[16]=x(13)*x(22)-x(12)*x(23)
   _[17]=x(21)^2
   _[18]=x(13)*x(21)-x(11)*x(23)
   _[19]=x(12)*x(21)-x(11)*x(22)
   _[20]=x(13)^2
   _[21]=x(13)*x(24)*x(32)-x(14)*x(22)*x(33)
   _[22]=x(13)*x(24)*x(31)-x(14)*x(21)*x(33)
   _[23]=x(12)^2*x(31)^2-2*x(11)*x(12)*x(31)*x(32)+x(11)^2*x(32)^2

Ex.4:
> ring r = aminor_ring(2,3,4); 
> ideal i = aminor(2,3,4); 
> ideal p = maxideal(1);  // p is a maximal ideal but not a prime divisor of i
> i = std(i); 
> p = std(p);
> locPrime(i,p); // this is a minimal primary decomposition of i
[1]:
   _[1]=x(24)*x(33)-x(23)*x(34)
   _[2]=x(14)*x(33)-x(13)*x(34)
   _[3]=x(24)*x(32)-x(22)*x(34)
   _[4]=x(23)*x(32)-x(22)*x(33)
   _[5]=x(14)*x(32)-x(12)*x(34)
   _[6]=x(13)*x(32)-x(12)*x(33)
   _[7]=x(24)*x(31)-x(21)*x(34)
   _[8]=x(23)*x(31)-x(21)*x(33)
   _[9]=x(22)*x(31)-x(21)*x(32)
   _[10]=x(14)*x(31)-x(11)*x(34)
   _[11]=x(13)*x(31)-x(11)*x(33)
   _[12]=x(12)*x(31)-x(11)*x(32)
   _[13]=x(14)*x(23)-x(13)*x(24)
   _[14]=x(14)*x(22)-x(12)*x(24)
   _[15]=x(13)*x(22)-x(12)*x(23)
   _[16]=x(14)*x(21)-x(11)*x(24)
   _[17]=x(13)*x(21)-x(11)*x(23)
   _[18]=x(12)*x(21)-x(11)*x(22)
[2]:
   _[1]=x(24)
   _[2]=x(23)
   _[3]=x(22)
   _[4]=x(21)
[3]:
   _[1]=x(33)
   _[2]=x(23)
   _[3]=x(22)
   _[4]=x(21)
   _[5]=x(13)
[4]:
   _[1]=x(32)
   _[2]=x(24)
   _[3]=x(23)
   _[4]=x(22)
   _[5]=x(12)
[5]:
   _[1]=x(32)
   _[2]=x(22)
   _[3]=x(12)
   _[4]=x(24)*x(33)-x(23)*x(34)
   _[5]=x(14)*x(33)-x(13)*x(34)
   _[6]=x(14)*x(23)-x(13)*x(24)
[6]:
   _[1]=x(33)
   _[2]=x(23)
   _[3]=x(13)
   _[4]=x(22)*x(31)-x(21)*x(32)
   _[5]=x(12)*x(31)-x(11)*x(32)
   _[6]=x(12)*x(21)-x(11)*x(22)
[7]:
   _[1]=x(33)^2
   _[2]=x(24)*x(33)-x(23)*x(34)
   _[3]=x(23)*x(33)
   _[4]=x(23)*x(32)-x(22)*x(33)
   _[5]=x(23)*x(31)-x(21)*x(33)
   _[6]=x(22)*x(31)-x(21)*x(32)
   _[7]=x(24)^2
   _[8]=x(23)*x(24)
   _[9]=x(23)^2
   _[10]=x(22)*x(23)
   _[11]=x(21)*x(23)
   _[12]=x(14)*x(23)-x(13)*x(24)
   _[13]=x(13)*x(23)
   _[14]=x(22)^2
   _[15]=x(21)*x(22)
   _[16]=x(13)*x(22)-x(12)*x(23)
   _[17]=x(21)^2
   _[18]=x(13)*x(21)-x(11)*x(23)
   _[19]=x(12)*x(21)-x(11)*x(22)
   _[20]=x(13)^2
   _[21]=x(13)*x(24)*x(32)-x(14)*x(22)*x(33)
   _[22]=x(13)*x(24)*x(31)-x(14)*x(21)*x(33)
   _[23]=x(12)^2*x(31)^2-2*x(11)*x(12)*x(31)*x(32)+x(11)^2*x(32)^2
[8]:
   _[1]=x(24)*x(33)-x(23)*x(34)
   _[2]=x(32)^2
   _[3]=x(24)*x(32)-x(22)*x(34)
   _[4]=x(23)*x(32)-x(22)*x(33)
   _[5]=x(22)*x(32)
   _[6]=x(22)*x(31)-x(21)*x(32)
   _[7]=x(24)^2
   _[8]=x(23)*x(24)
   _[9]=x(22)*x(24)
   _[10]=x(23)^2
   _[11]=x(22)*x(23)
   _[12]=x(14)*x(23)-x(13)*x(24)
   _[13]=x(22)^2
   _[14]=x(21)*x(22)
   _[15]=x(14)*x(22)-x(12)*x(24)
   _[16]=x(13)*x(22)-x(12)*x(23)
   _[17]=x(12)*x(22)
   _[18]=x(21)^2
   _[19]=x(12)*x(21)-x(11)*x(22)
   _[20]=x(12)^2
   _[21]=x(12)*x(24)*x(31)-x(14)*x(21)*x(32)
   _[22]=x(12)*x(23)*x(31)-x(13)*x(21)*x(32)
   _[23]=x(14)^2*x(33)^2-2*x(13)*x(14)*x(33)*x(34)+x(13)^2*x(34)^2
   _[24]=x(14)*x(21)*x(32)*x(33)-x(13)*x(21)*x(32)*x(34)
[9]:
   _[1]=x(24)*x(33)-x(23)*x(34)
   _[2]=x(23)*x(32)-x(22)*x(33)
   _[3]=x(22)*x(31)-x(21)*x(32)
   _[4]=x(14)*x(23)-x(13)*x(24)
   _[5]=x(13)*x(22)-x(12)*x(23)
   _[6]=x(12)*x(21)-x(11)*x(22)
   _[7]=x(33)^3
   _[8]=x(23)*x(33)^2
   _[9]=x(23)^2*x(33)
   _[10]=x(22)*x(23)*x(33)
   _[11]=x(13)*x(23)*x(33)
   _[12]=x(22)^2*x(33)
   _[13]=x(32)^3
   _[14]=x(22)*x(32)^2
   _[15]=x(13)*x(24)*x(32)-x(14)*x(22)*x(33)
   _[16]=x(22)^2*x(32)
   _[17]=x(12)*x(22)*x(32)
   _[18]=x(12)*x(23)*x(31)-x(13)*x(21)*x(32)
   _[19]=x(24)^3
   _[20]=x(23)*x(24)^2
   _[21]=x(23)^2*x(24)
   _[22]=x(22)*x(23)*x(24)
   _[23]=x(23)^3
   _[24]=x(22)*x(23)^2
   _[25]=x(13)*x(23)^2
   _[26]=x(12)*x(23)^2
   _[27]=x(22)^2*x(23)
   _[28]=x(21)*x(22)*x(23)
   _[29]=x(12)*x(22)*x(23)
   _[30]=x(13)^2*x(23)
   _[31]=x(22)^3
   _[32]=x(21)*x(22)^2
   _[33]=x(12)*x(22)^2
   _[34]=x(21)^2*x(22)
   _[35]=x(12)^2*x(22)
   _[36]=x(21)^3
   _[37]=x(13)^3
   _[38]=x(12)^3
   _[39]=x(22)*x(32)*x(33)^2
   _[40]=x(21)*x(22)*x(33)^2
   _[41]=x(14)*x(22)*x(33)^2-x(12)*x(23)*x(33)*x(34)
   _[42]=x(12)*x(22)*x(33)^2
   _[43]=x(21)*x(22)*x(32)*x(33)
   _[44]=x(12)^2*x(23)*x(33)
   _[45]=x(13)*x(21)*x(32)^2-x(11)*x(22)*x(32)*x(33)
   _[46]=x(13)*x(21)^2*x(32)-x(11)*x(21)*x(22)*x(33)
   _[47]=x(12)*x(13)*x(24)*x(31)-x(13)*x(14)*x(21)*x(32)
   _[48]=x(12)*x(13)*x(23)*x(24)
   _[49]=x(12)^2*x(23)*x(24)
   _[50]=x(12)^2*x(13)*x(23)
   _[51]=x(21)*x(32)^2*x(33)^2
   _[52]=x(21)^2*x(32)*x(33)^2
   _[53]=x(14)*x(21)*x(32)*x(33)^2-x(13)*x(21)*x(32)*x(33)*x(34)
   _[54]=x(13)*x(21)*x(32)*x(33)^2
   _[55]=x(21)^2*x(32)^2*x(33)
   _[56]=x(13)*x(14)*x(21)*x(32)*x(33)-x(13)^2*x(21)*x(32)*x(34)
   _[57]=x(13)^2*x(21)*x(32)*x(33)
   _[58]=x(12)*x(13)^2*x(24)^2
   _[59]=x(12)^2*x(13)*x(24)^2
   _[60]=x(12)^2*x(13)^2*x(24)

Ex.5:
> ring r = aminor_ring(2,3,5); 
> ideal i = aminor(2,3,5); 
> ideal p = x(12),x(22),x(23),x(24),x(25),x(32); // p is an isolated prime divisor of i
> i = std(i); 
> p = std(p);
> locPrime(i,p); // p is the p-primary component of i
_[1]=x(32)
_[2]=x(25)
_[3]=x(24)
_[4]=x(23)
_[5]=x(22)
_[6]=x(12)

Ex.6:
> ring r = aminor_ring(2,3,5); 
> ideal i = aminor(2,3,5); 
> ideal p = x(12)*x(31)-x(32)*x(11),x(13),x(14),x(21),x(22),x(23),x(24),x(25),x(33),x(34);  // p is an embedded prime divisor of i
> i = std(i); 
> p = std(p);
> locPrime(i,p);
[1]:
   _[1]=x(33)
   _[2]=x(23)
   _[3]=x(13)
   _[4]=x(25)*x(34)-x(24)*x(35)
   _[5]=x(15)*x(34)-x(14)*x(35)
   _[6]=x(22)*x(31)-x(21)*x(32)
   _[7]=x(12)*x(31)-x(11)*x(32)
   _[8]=x(15)*x(24)-x(14)*x(25)
   _[9]=x(12)*x(21)-x(11)*x(22)
[2]:
   _[1]=x(34)
   _[2]=x(24)
   _[3]=x(14)
   _[4]=x(23)*x(32)-x(22)*x(33)
   _[5]=x(13)*x(32)-x(12)*x(33)
   _[6]=x(23)*x(31)-x(21)*x(33)
   _[7]=x(22)*x(31)-x(21)*x(32)
   _[8]=x(13)*x(31)-x(11)*x(33)
   _[9]=x(12)*x(31)-x(11)*x(32)
   _[10]=x(13)*x(22)-x(12)*x(23)
   _[11]=x(13)*x(21)-x(11)*x(23)
   _[12]=x(12)*x(21)-x(11)*x(22)
[3]:
   _[1]=x(34)
   _[2]=x(24)
   _[3]=x(23)
   _[4]=x(22)
   _[5]=x(21)
   _[6]=x(14)
[4]:
   _[1]=x(25)
   _[2]=x(24)
   _[3]=x(23)
   _[4]=x(22)
   _[5]=x(21)
[5]:
   _[1]=x(33)
   _[2]=x(23)
   _[3]=x(22)
   _[4]=x(21)
   _[5]=x(13)
   _[6]=x(25)*x(34)-x(24)*x(35)
   _[7]=x(15)*x(34)-x(14)*x(35)
   _[8]=x(15)*x(24)-x(14)*x(25)
[6]:
   _[1]=x(33)
   _[2]=x(25)
   _[3]=x(24)
   _[4]=x(23)
   _[5]=x(13)
   _[6]=x(22)*x(31)-x(21)*x(32)
   _[7]=x(12)*x(31)-x(11)*x(32)
   _[8]=x(12)*x(21)-x(11)*x(22)
[7]:
   _[1]=x(34)^2
   _[2]=x(25)*x(34)-x(24)*x(35)
   _[3]=x(24)*x(34)
   _[4]=x(24)*x(33)-x(23)*x(34)
   _[5]=x(24)*x(32)-x(22)*x(34)
   _[6]=x(23)*x(32)-x(22)*x(33)
   _[7]=x(24)*x(31)-x(21)*x(34)
   _[8]=x(23)*x(31)-x(21)*x(33)
   _[9]=x(22)*x(31)-x(21)*x(32)
   _[10]=x(25)^2
   _[11]=x(24)*x(25)
   _[12]=x(24)^2
   _[13]=x(23)*x(24)
   _[14]=x(22)*x(24)
   _[15]=x(21)*x(24)
   _[16]=x(15)*x(24)-x(14)*x(25)
   _[17]=x(14)*x(24)
   _[18]=x(23)^2
   _[19]=x(22)*x(23)
   _[20]=x(21)*x(23)
   _[21]=x(14)*x(23)-x(13)*x(24)
   _[22]=x(22)^2
   _[23]=x(21)*x(22)
   _[24]=x(14)*x(22)-x(12)*x(24)
   _[25]=x(13)*x(22)-x(12)*x(23)
   _[26]=x(21)^2
   _[27]=x(14)*x(21)-x(11)*x(24)
   _[28]=x(13)*x(21)-x(11)*x(23)
   _[29]=x(12)*x(21)-x(11)*x(22)
   _[30]=x(14)^2
   _[31]=x(14)*x(25)*x(33)-x(15)*x(23)*x(34)
   _[32]=x(14)*x(25)*x(32)-x(15)*x(22)*x(34)
   _[33]=x(14)*x(25)*x(31)-x(15)*x(21)*x(34)
   _[34]=x(13)^2*x(32)^2-2*x(12)*x(13)*x(32)*x(33)+x(12)^2*x(33)^2
   _[35]=x(13)^2*x(31)*x(32)-x(12)*x(13)*x(31)*x(33)-x(11)*x(13)*x(32)*x(33)+x(11)*x(12)*x(33)^2
   _[36]=x(12)*x(13)*x(31)*x(32)-x(11)*x(13)*x(32)^2-x(12)^2*x(31)*x(33)+x(11)*x(12)*x(32)*x(33)
   _[37]=x(13)^2*x(31)^2-2*x(11)*x(13)*x(31)*x(33)+x(11)^2*x(33)^2
   _[38]=x(12)*x(13)*x(31)^2-x(11)*x(13)*x(31)*x(32)-x(11)*x(12)*x(31)*x(33)+x(11)^2*x(32)*x(33)
   _[39]=x(12)^2*x(31)^2-2*x(11)*x(12)*x(31)*x(32)+x(11)^2*x(32)^2
[8]:
   _[1]=x(25)*x(34)-x(24)*x(35)
   _[2]=x(33)^2
   _[3]=x(25)*x(33)-x(23)*x(35)
   _[4]=x(24)*x(33)-x(23)*x(34)
   _[5]=x(23)*x(33)
   _[6]=x(23)*x(32)-x(22)*x(33)
   _[7]=x(23)*x(31)-x(21)*x(33)
   _[8]=x(22)*x(31)-x(21)*x(32)
   _[9]=x(25)^2
   _[10]=x(24)*x(25)
   _[11]=x(23)*x(25)
   _[12]=x(24)^2
   _[13]=x(23)*x(24)
   _[14]=x(15)*x(24)-x(14)*x(25)
   _[15]=x(23)^2
   _[16]=x(22)*x(23)
   _[17]=x(21)*x(23)
   _[18]=x(15)*x(23)-x(13)*x(25)
   _[19]=x(14)*x(23)-x(13)*x(24)
   _[20]=x(13)*x(23)
   _[21]=x(22)^2
   _[22]=x(21)*x(22)
   _[23]=x(13)*x(22)-x(12)*x(23)
   _[24]=x(21)^2
   _[25]=x(13)*x(21)-x(11)*x(23)
   _[26]=x(12)*x(21)-x(11)*x(22)
   _[27]=x(13)^2
   _[28]=x(13)*x(25)*x(32)-x(15)*x(22)*x(33)
   _[29]=x(13)*x(24)*x(32)-x(14)*x(22)*x(33)
   _[30]=x(13)*x(25)*x(31)-x(15)*x(21)*x(33)
   _[31]=x(13)*x(24)*x(31)-x(14)*x(21)*x(33)
   _[32]=x(15)^2*x(34)^2-2*x(14)*x(15)*x(34)*x(35)+x(14)^2*x(35)^2
   _[33]=x(15)*x(22)*x(33)*x(34)-x(14)*x(22)*x(33)*x(35)
   _[34]=x(15)*x(21)*x(33)*x(34)-x(14)*x(21)*x(33)*x(35)
   _[35]=x(12)^2*x(31)^2-2*x(11)*x(12)*x(31)*x(32)+x(11)^2*x(32)^2
[9]:
   _[1]=x(25)*x(34)-x(24)*x(35)
   _[2]=x(24)*x(33)-x(23)*x(34)
   _[3]=x(23)*x(32)-x(22)*x(33)
   _[4]=x(23)*x(31)-x(21)*x(33)
   _[5]=x(22)*x(31)-x(21)*x(32)
   _[6]=x(15)*x(24)-x(14)*x(25)
   _[7]=x(14)*x(23)-x(13)*x(24)
   _[8]=x(13)*x(22)-x(12)*x(23)
   _[9]=x(13)*x(21)-x(11)*x(23)
   _[10]=x(12)*x(21)-x(11)*x(22)
   _[11]=x(34)^3
   _[12]=x(24)*x(34)^2
   _[13]=x(24)^2*x(34)
   _[14]=x(23)*x(24)*x(34)
   _[15]=x(14)*x(24)*x(34)
   _[16]=x(23)^2*x(34)
   _[17]=x(33)^3
   _[18]=x(23)*x(33)^2
   _[19]=x(14)*x(25)*x(33)-x(15)*x(23)*x(34)
   _[20]=x(23)^2*x(33)
   _[21]=x(13)*x(23)*x(33)
   _[22]=x(13)*x(24)*x(32)-x(14)*x(22)*x(33)
   _[23]=x(13)*x(24)*x(31)-x(14)*x(21)*x(33)
   _[24]=x(25)^3
   _[25]=x(24)*x(25)^2
   _[26]=x(24)^2*x(25)
   _[27]=x(23)*x(24)*x(25)
   _[28]=x(24)^3
   _[29]=x(23)*x(24)^2
   _[30]=x(14)*x(24)^2
   _[31]=x(13)*x(24)^2
   _[32]=x(23)^2*x(24)
   _[33]=x(22)*x(23)*x(24)
   _[34]=x(21)*x(23)*x(24)
   _[35]=x(13)*x(23)*x(24)
   _[36]=x(14)^2*x(24)
   _[37]=x(23)^3
   _[38]=x(22)*x(23)^2
   _[39]=x(21)*x(23)^2
   _[40]=x(13)*x(23)^2
   _[41]=x(22)^2*x(23)
   _[42]=x(21)*x(22)*x(23)
   _[43]=x(21)^2*x(23)
   _[44]=x(13)^2*x(23)
   _[45]=x(22)^3
   _[46]=x(21)*x(22)^2
   _[47]=x(21)^2*x(22)
   _[48]=x(21)^3
   _[49]=x(14)^3
   _[50]=x(13)^3
   _[51]=x(23)*x(33)*x(34)^2
   _[52]=x(22)*x(23)*x(34)^2
   _[53]=x(21)*x(23)*x(34)^2
   _[54]=x(15)*x(23)*x(34)^2-x(13)*x(24)*x(34)*x(35)
   _[55]=x(13)*x(23)*x(34)^2
   _[56]=x(22)*x(23)*x(33)*x(34)
   _[57]=x(21)*x(23)*x(33)*x(34)
   _[58]=x(13)^2*x(24)*x(34)
   _[59]=x(14)*x(22)*x(33)^2-x(12)*x(23)*x(33)*x(34)
   _[60]=x(14)*x(21)*x(33)^2-x(11)*x(23)*x(33)*x(34)
   _[61]=x(14)*x(22)^2*x(33)-x(12)*x(22)*x(23)*x(34)
   _[62]=x(14)*x(21)*x(22)*x(33)-x(11)*x(22)*x(23)*x(34)
   _[63]=x(14)*x(21)^2*x(33)-x(11)*x(21)*x(23)*x(34)
   _[64]=x(13)*x(14)*x(25)*x(32)-x(14)*x(15)*x(22)*x(33)
   _[65]=x(13)*x(14)*x(25)*x(31)-x(14)*x(15)*x(21)*x(33)
   _[66]=x(13)*x(14)*x(24)*x(25)
   _[67]=x(13)^2*x(24)*x(25)
   _[68]=x(13)^2*x(14)*x(24)
   _[69]=x(22)*x(33)^2*x(34)^2
   _[70]=x(21)*x(33)^2*x(34)^2
   _[71]=x(22)^2*x(33)*x(34)^2
   _[72]=x(21)*x(22)*x(33)*x(34)^2
   _[73]=x(15)*x(22)*x(33)*x(34)^2-x(14)*x(22)*x(33)*x(34)*x(35)
   _[74]=x(14)*x(22)*x(33)*x(34)^2
   _[75]=x(21)^2*x(33)*x(34)^2
   _[76]=x(15)*x(21)*x(33)*x(34)^2-x(14)*x(21)*x(33)*x(34)*x(35)
   _[77]=x(14)*x(21)*x(33)*x(34)^2
   _[78]=x(22)^2*x(33)^2*x(34)
   _[79]=x(21)*x(22)*x(33)^2*x(34)
   _[80]=x(21)^2*x(33)^2*x(34)
   _[81]=x(14)*x(15)*x(22)*x(33)*x(34)-x(14)^2*x(22)*x(33)*x(35)
   _[82]=x(14)^2*x(22)*x(33)*x(34)
   _[83]=x(14)*x(15)*x(21)*x(33)*x(34)-x(14)^2*x(21)*x(33)*x(35)
   _[84]=x(14)^2*x(21)*x(33)*x(34)
   _[85]=x(13)*x(14)^2*x(25)^2
   _[86]=x(13)^2*x(14)*x(25)^2
   _[87]=x(13)^2*x(14)^2*x(25)
   _[88]=x(12)^3*x(31)^3-3*x(11)*x(12)^2*x(31)^2*x(32)+3*x(11)^2*x(12)*x(31)*x(32)^2-x(11)^3*x(32)^3

Ex.7:
> ring r = aminor_ring(2,3,5); 
> ideal i = aminor(2,3,5); 
> ideal p = x(11),x(12),x(14),x(15),x(21),x(22),x(23),x(24),x(25),x(31),x(32),x(33),x(35);  // p is not a prime divisor of i
> i = std(i); 
> p = std(p);
> locPrime(i,p); 
[1]:
   _[1]=x(25)
   _[2]=x(24)
   _[3]=x(23)
   _[4]=x(22)
   _[5]=x(21)
[2]:
   _[1]=x(32)
   _[2]=x(25)
   _[3]=x(24)
   _[4]=x(23)
   _[5]=x(22)
   _[6]=x(12)