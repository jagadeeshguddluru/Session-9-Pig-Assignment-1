# Session-9-Pig-Assignment-1
grunt> petrol = load 'petrolproducts.txt' using PigStorage(',') as (dis:bytearray,dname:bytearray,brate:bytearray,srate:bytearray,vin:int,vout:int,year:int);
grunt> volsold = group petrol by dname;                                                                                                                      
grunt> out = foreach volsold generate group,SUM(petrol.vout);                                                                                                
grunt> dump out;                                                                                                                                             
(shell,69266)
(Bharat,83662)
(reliance,76558)
(hindustan,71767)


grunt> petrol = load 'petrolproducts.txt' using PigStorage(',') as (dis:bytearray,dname:bytearray,brate:bytearray,srate:bytearray,vin:int,vout:int,year:int);
grunt> ord = order petrol by vout desc;                                                                                                                      
grunt> grp = group l by dis;;                                                                                                                                
grunt> out = foreach grp generate group,l.vout;                                                                                                              
grunt> dump out;                                                                                                                                             
(+E6O 9P1,{(895)})
(+F6W 6H3,{(896)})
(+J4M 4G3,{(895)})
(+M6S 1P4,{(895)})
(+N5Q 8E5,{(895)})
(+O8A 6Z5,{(897)})
(+O9P 9S3,{(897)})
(+S8W 0P4,{(899)})
(+T1A 9W4,{(899)})
(+V8U 2T6,{(898)})




grunt> petrol = load 'petrolproducts.txt' using PigStorage(',') as (dis:bytearray,dname:bytearray,brate:bytearray,srate:bytearray,vin:int,vout:int,year:int);
grunt> grp = group petrol by dname;                                                                                                              
gunt> for = foreach grp generate group,SUM(petrol.vout) as v;
grunt> orderr = order for by v asec;
grunt> l = limit orderr 1;   
grunt> dump l;
(shell,69266)




