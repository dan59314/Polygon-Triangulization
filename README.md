# Polygon-Triangulization
Convert non-convex polygon into triangles.

  ---------------------------------------------------------------------------------

  Copyright: (C) Daniel Lu, RasVector Technology.

  Email : dan59314@gmail.com
  
  linkedin : https://www.linkedin.com/in/daniel-lu-238910a4/
  
  Web :     http://www.rasvector.url.tw/
  
  YouTube : http://www.youtube.com/dan59314/playlist
  
  Instructables : https://goo.gl/EwRGYA
  
  
  GooglePlay : https://play.google.com/store/apps/developer?id=%EF%BC%A4aniel+Lu+%E5%91%82%E8%8A%B3%E5%85%83
  
  

  This software may be freely copied, modified, and redistributed
  provided that this copyright notice is preserved on all copies.
  The intellectual property rights of the algorithms used reside
  with the Daniel Lu, RasVector Technology.

  You may not distribute this software, in whole or in part, as
  part of any commercial product without the express consent of
  the author.

  There is no warranty or other guarantee of fitness of this
  software for any purpose. It is provided solely "as is".

  ---------------------------------------------------------------------------------
  版權宣告  (C) Daniel Lu, RasVector Technology.

  Email : dan59314@gmail.com
  
  linkedin : https://www.linkedin.com/in/daniel-lu-238910a4/
  
  Web :     http://www.rasvector.url.tw/
  
  YouTube : http://www.youtube.com/dan59314/playlist
  
  Instructables : https://goo.gl/EwRGYA
  
  
  GooglePlay : https://play.google.com/store/apps/developer?id=%EF%BC%A4aniel+Lu+%E5%91%82%E8%8A%B3%E5%85%83



  使用或修改軟體，請註明引用出處資訊如上。未經過作者明示同意，禁止使用在商業用途。
  
  
---------------------------------------------------------------------------------

[Concave to convex polygons Video](https://www.youtube.com/watch?v=CaX3jKzSdfU&index=14&list=PLZG_AEGYW1gKbWlpKQV2EYN9Uh5K9MXQg)
[![Concave to Convex polygons](https://github.com/dan59314/Polygon-Triangulization/blob/master/Plg06.PNG)](https://www.youtube.com/watch?v=CaX3jKzSdfU&index=14&list=PLZG_AEGYW1gKbWlpKQV2EYN9Uh5K9MXQg?t=0s "Concave to convex polygons") 


To convert a non-convex polygon into triangles. There are so many algorithms available in internet.  None of them is easy to me to implement it.


I then try to think how to do the polygon triangulation in my own concept. Here is how I did it.

Step 1: Find all concave points in a polygon.

<img src="https://github.com/dan59314/Polygon-Triangulization/blob/master/plg02.PNG" width="480">


Step 2 : Connect all unused concave points to the near points to split one polygon into several ones.

<img src="https://github.com/dan59314/Polygon-Triangulization/blob/master/Plg03.PNG" width="480">


Step 3: Repeat step1 and step2 for all the split polygons until there is no more concave points.

<img src="https://github.com/dan59314/Polygon-Triangulization/blob/master/plg04.PNG" width="480">


Step 4 : Start do triangulation for each convex polygon. Let's say there is a n-points convex polygon. Start from 1st point, then point-n, point-2nd......,  (1,n,2),(n,2,n-1),(2,n-1,3)......

ForeId = 1;

BackId = n;

while (BackId-ForeId>1) {

  GetTriangle( ForeId, BackId, ForeId+1);
  
  GetTriangle( BackId, ForeId+1, BackId-1);

  ForeId++;

  BackId--;

}

<img src="https://github.com/dan59314/Polygon-Triangulization/blob/master/plg05.PNG" width="480">


I then finally convert the non-convex polygon into many triangles.

<img src="https://github.com/dan59314/Polygon-Triangulization/blob/master/Plg06.PNG" width="480">


Quite easy, isn't it?
