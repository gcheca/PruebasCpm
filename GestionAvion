// Programa gestión avión

#include <stdio.h>
#include <ctype.h>

const int Numfilas = 10;
const int Asientosfila = 6;
const int Pasillo = Asientosfila/2;

typedef enum TipoEstado {vacio, ocupado, reserva};
typedef TipoEstado TipoOcupado[Asientosfila];
typedef struct TipoFila
{
  TipoOcupado asientosOcupados;
  int juntas;
  int juntasP;
};
typedef TipoFila TipoPlazas[NumFilas];
//Muestra ocupación
void PrintaPlazas(const TipoPlazas P)
{
  const char DibujoAsiento[3]={' ', '*', 'R'};
  print("\n     A   B   C      D   E   F\n\n");
  for (int i=0;i<Numfilas;i++)
  {
    print("%3d",i+1);
    for(int j=0;j<Asientosfila;j++)
    {
      if (j==Pasillo)
      {
        printf("   ");
      }
      printf(" (%c)", DibujoAsiento[P[i].asientosOcupados[j]]);
    }
    printf("\n");
  }
  printf("\n");
}

void ImprimirTarjeta (int fila, int asiento)
{
  printf(".----------------------------.\n");
  printf("|     TARJETA DE EMBARQUE    |\n");
  printf("|  Fila :%3d,fila);
  printf("  Asiento :%3c   |\n", asiento);
  printf("'----------------------------'\n"
}

// Calcula número y posición de plazas contiguas
void CalcularPlazasJuntas (TipoFila & fila)
{
  int juntas=0;
  int juntasP=0;

  fila.juntas=0;
  fila.juntasP=0;
  for(int j=0;j<AdientosFila;j++)
  {
    if(j==Pasillo)
    {
      juntas=0
    }
    if (fila.asientosOcupados[j]==vacio)
    {
      juntas++;
      juntasP++;
      if (juntas>fila.juntas)
      {
        fila.juntas=juntas;
        fila.desde=j-juntas+1;
      }
      if (juntasP>fila.juntasP)
      {
        fila.juntasP=juntasP;
        fila.desdeP=j-juntasP+1;
      }
    }
    else
    {
      juntas=0;
      juntasP=0;
    }
  }
}
void CalcularPlazasJuntas (TipoFila & fila)
{
  int juntas=0;
  int juntasP=0;

  fila.juntas=0;
  fila.juntasP=0;
  for(int j=0;j<AdientosFila;j++)
  {
    if(j==Pasillo)
    {
      juntas=0
    }
    if (fila.asientosOcupados[j]==vacio)
    {
      juntas++;
      juntasP++;
      if (juntas>fila.juntas)
      {
        fila.juntas=juntas;
        fila.desde=j-juntas+1;
      }
      if (juntasP>fila.juntasP)
      {
        fila.juntasP=juntasP;
        fila.desdeP=j-juntasP+1;
      }
    }
    else
    {
      juntas=0;
      juntasP=0;
    }
  }
}

//Reservar Plazas contiguas al mismo lado
bool MarcarPlazasJuntas(int numero, TipoFila & fila)
{
  if (fila.juntas<numero)
  {
    return false;
  }
  else
  {
    for (int j=1;j<=numero;j++)
    {
      fila.asientosOcupados[fila.desde+j-1]=reservado;
    }
    return true;
  }
}

//Reservar plazas contiguas a un lado u otro del pasillo

bool MarcarPlazasJuntasPasillo (int numero, TipoFila & fila)
{
  if (fila.juntas<numero)
  {
    return false;
  }
  else
  {
    for (int j=1;j<=numero;j++)
    {
      fila.asientosOcupados[fila.desdeP+j-1]=reservado;
    }
    return true;
  }
}
//Reservar plazas indistintamente de juntas o separadas
void MarcarPlazas (int & numero, Tipofila & fila)
{
  int j=0;
  while(numero>0 && j<AsientosFila)
  {
    fila.asientosOcupados[j]=reservado;
    numero--;
  }
}

//Busca plazas cerca
bool BuscarPlazas (int nuevas, int libres, TipoPlazas plazas)
{
  int fila;
  if (nuevas<=libres)//Busca en la misma fila
  {
    fila=0;
    while(fila<Numfilas)
    {
      if(MarcarPlazasJuntas(nuevas, plazas[fila]) )
      {
        return true;
      }
      fila++;
    }
    //Plazas en la misma fila
    fila=0;
    while(fila<NumFilas)
    {
      if (MarcarPlazasJuntasPasillo(nuevas,plazas[fila]))
      {
    return true;
      }
    }
  fila++;
  }
  else
  {
    printf("No hay plazas suficientes\n");
  }
  return false;
}

//Confirmar o liberar reservas
void ConfirmarPlazas(bool ok, TipoPlazas plazas)
{
  bool cambio;
  for(int i=0;i<NumFilas;i++)
  {
    cambio=false;
    for(int j=0; j<Asientosfila;j++)
    {
      if(plazas[i].asientosOcupados[j]==reservado)
      {
        if(ok)
        {
          plazas[i].asientosOcupados[j]=ocupado;
          ImprimirTarjeta(i+1,char(int('A')+j));
          cambio=true;
        }
        else
        {
          plazas[i].asientosOcupados[j]=vacio;
        }
      }
    }
    if(cambio)
    {
      CalculasPlazasJuntas(plazas[i]);
    }
  }
}

/*    PROGRAMA PRINCIPAL     */

int main()
{
  TipoPlazas pasaje;
  int sitiosLibres;
  char car;
  int aux, fil, col;
  bool seguir;

//Iniciamos con todo vacío
sitiosLibres=NumFilas*AsientosFila;
for(int i=0;i<NumFilas;i++)
  {
    for(int j=0;j<AsientosFila;j++)
    {
      pasaje[i].asientosOcupados[j]=vacio;
    }
    CalculasPlazasJuntas(pasaje[i]);
  }
  //Bucle
  seguir=true;
  while(seguir)
  {
    printf("¿Opción (Plaza, Grupo, Estado, Fin)?");
    scanf("%c", &car);
    car=toupper(car);
    switch(car)
    //Asigna una plaza determinada
    {
      case 'P':
      do
      {
        printf("Elije fila (1 a 10)");
        scanf("%d",&aux);
      }
      while(aux<1||aux>10);
      do
      {
        printf("Elije asiento (A a F)");
        scanf("%c",&car);
        car=toupper(car);
      }
      while(car<'A'||car>'F');
      fil=aux-1;
      col=int(car-'A');
      if(pasaje[fil].asientosOcupados[col]==vacio)
      {
        pasaje[fil].asientosOcupados[col]==ocupado;
        sitiosLibres--;
        CalcularPlazasJuntas(pasaje[fil]);
        ImprimirTarjeta(fil+1,char(int'A')+col));
      }
      else
      {
        printf("** Plaza Ocupada ** \n");
      }
      break;
      //Asigna automático plazas contiguas
      case 'G':
      do
      {
        printf("¿Cuantas plazas? (2 a 6)");
        scanf("%d", &aux);
      }
      while(aux<2||aux>6);
      if(BuscarPlazas(aux, sitiosLibres,pasaje))
      {
        PintarPlaas(pasaje);
        printf("Confirmar (S/N)");
        scanf("%c",&car);
        if(toupper(car)=='S')
        {
          ConfirmarPlazas(true,pasaje);
          sitiosLibres=sitiosLibres-aux;
        }
        else
        {
          ConfirmarPlazas(false,pasaje);
        }
      }
      break;
      //Printa ocupación
      case'E':
      PintarPlazas(pasaje);
      break;
      //Finalizar
      case'F':
      seguir=false;
      break;
    }
  }
}
