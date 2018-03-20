Table nivel_1, posicion, grafo;
final int r=10;
int x, x1, y1, i, j, p;
void setup() {
  size(700, 700);
  background(255);

  //TABLAS USADAS
  nivel_1=new Table();
  posicion=new Table();
  grafo=new Table();

  //CREACION DE NIVEL 1

  for ( i=0; i<width; i++) { 
    for ( j=0; j<height; j++) {
      nivel_1.setString(i, j, "0");
    }
  }
  nivel_1.setString(50, 50, "1");
  nivel_1.setString(350, 50, "1");
  nivel_1.setString(650, 50, "1"); 
  nivel_1.setString(50, 650, "1");
  nivel_1.setString(350, 650, "1");
  nivel_1.setString(650, 650, "1");
  nivel_1.setString(350, 200, "1");
  nivel_1.setString(200, 350, "1");
  nivel_1.setString(500, 350, "1");
  nivel_1.setString(350, 500, "1");
  
  //POSICION DEL NODO EN EJE X
  
  /* posicion.setString(0, 0, "50"); 
   posicion.setString(0, 1, "250");
   posicion.setString(0, 2, "450");
   posicion.setString(0, 3, "50");
   posicion.setString(0, 4, "250");
   posicion.setString(0, 5, "450");
   posicion.setString(0, 6, "50");
   posicion.setString(0, 7, "450");
   posicion.setString(0, 8, "250");
   posicion.setString(0, 9, "250");
   posicion.setString(0, 10, "200");
   posicion.setString(0, 11, "300");
   
   //POSICION DEL NODO EN EJE Y
   
   posicion.setString(1, 0, "50"); 
   posicion.setString(1, 1, "50");
   posicion.setString(1, 2, "50");
   posicion.setString(1, 3, "450");
   posicion.setString(1, 4, "450");
   posicion.setString(1, 5, "450");
   posicion.setString(1, 6, "250");
   posicion.setString(1, 7, "250");
   posicion.setString(1, 8, "200");
   posicion.setString(1, 9, "300");
   posicion.setString(1, 10, "250");
   posicion.setString(1, 11, "250");*/

  //LLENADO DE GRAFO

  for (i=0; i<width; i++) { 
    for ( j=0; j<height; j++) {
      grafo.setString(i, j, "0");
    }
  }

  for (i=50; i<651; i++) {
    grafo.setString(i, 50, "1");
    grafo.setString(i, 650, "1");
    grafo.setString(50, i, "1");
    grafo.setString(350, i, "1");
    grafo.setString(650, i, "1");
  }
  
  for ( i=0; i<151; i++) { 
    grafo.setString(200+i, 350+i, "1");
    grafo.setString(350+i, 200+i, "1");
  }
  
  for ( i=0; i<151; i++) {
    grafo.setString(200+i, 350-i, "1");
    grafo.setString(350+i, 500-i, "1");
  }
  
  saveTable(grafo, "data/grafo.csv");
  saveTable(nivel_1, "data/nivel_1.csv");
  saveTable(posicion, "data/posicion.csv");
}
void mouseClicked() {
  p= nivel_1.getInt(mouseX, mouseY);

  if (p==1) {
    x1=mouseX;
    y1=mouseY;
  }
}

void draw() {

//DIBUJA LOS NODOS

  for (i=0; i<width; i++) { 
    for ( j=0; j<height; j++) {
      x = nivel_1.getInt(i, j);
      if (x==1) {
        fill(17, 122, 101);
        stroke(17, 122, 101);
        ellipse(i, j, r, r);
      }
    }
  }
  
//TRAZADO DE LINEAS

  p= nivel_1.getInt(mouseX, mouseY);
  if (p==1) {
    stroke(0, 255, 0);
    fill(0, 255, 0);
    
    ellipse(mouseX, mouseY, r, r);
    if (x1==0&&y1==0) { 
      line(mouseX, mouseY, mouseX, mouseY);
    } else {
      line(x1, y1, mouseX, mouseY);
    }
  }
}
