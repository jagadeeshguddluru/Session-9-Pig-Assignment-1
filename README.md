# Session-9-Pig-Assignment-1
grunt> petrol = load 'petrolproducts.txt' using PigStorage(',') as (dis:bytearray,dname:bytearray,brate:bytearray,srate:bytearray,vin:int,vout:int,year:int);
grunt> volsold = group petrol by dname;                                                                                                                      
grunt> out = foreach volsold generate group,SUM(petrol.vout);                                                                                                
grunt> dump out;                                                                                                                                             
(shell,69266)
(Bharat,83662)
(reliance,76558)
(hindustan,71767)


