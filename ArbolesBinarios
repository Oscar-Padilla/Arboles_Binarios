public class ArbolesBinarios 
{
    public static void main(String[] args) 
    {
        //Creamos el objeto para poder acceder a los metodos de la clase.
        ArbolesBinarios arbol=new ArbolesBinarios();
        //En esta seccion se irán agregando todos los elementos del arbol.
        arbol.insertar(15);
        arbol.insertar(9);
        arbol.insertar(20);
        arbol.insertar(6);
        arbol.insertar(14);
        arbol.insertar(17);
        arbol.insertar(64);
        arbol.insertar(13);
        arbol.insertar(26);
        arbol.insertar(72);
        //Siguiente a la ingesta de datos. Seguiremos con los recorridos.
        //Daremos formato para identificar cada uno de los recorridos y
        //siguiente a eso llamaremos con el objeto a su respectivo metodo.
        System.out.println("Impresion preorden:");
        arbol.imprimirPre();
        System.out.println("Impresion inorden:");
        arbol.imprimirIn();
        System.out.println("Impresion postorden:");
        arbol.imprimirPost();
        //Como ultimo paso, vamos a imprimir la altura del arbol, ya que
        //el metodo para determinar la altura es de tipo int y requiere una 
        //instruccion return, tenemos que mandar a llamar dentro del print
        //al metodo de este.
        System.out.println("Altura del arbol: "+arbol.Altura());
    }
    //Instanciamos el nodo que será la raíz, tenerlo fuera del
    //metodo es para poder llamarlo desde otros metodos.
    Nodo raiz;
    //Instanciamos la variable de altura que nos ayudará para más
    //adelante para determinar la altura del arbol.
    int altura;
    //La clase nodo es la principal para ingresarle la informacion
    //al arbol. Así como los diferentes hijos de los subarboles.
    class Nodo
    {
        //Esta es la variable que almacenará la informacion que será
        //agregada al arbol.
        int info;
        //Estás variables de tipo Nodo serán las que ayudarán a poder
        //identificar los hijos.
        Nodo izq,der;
    }
    //En este metodo se construye el arbol.
    public ArbolesBinarios()
    {
        raiz=null;
    }
    //Iniciamos con el metodo para ingresar los datos al arbol. Este
    //recibe como parametro un dato.
    public void insertar(int info)
    {
        //Creamos la variable nuevo de tipo nuevo el cual será un objeto.
        //Nos permitirá poder acceder a la informacion que se ingresa. 
        Nodo nuevo=new Nodo();
        //Decimos que la informacion que se ingresa será de caracter nuevo.
        nuevo.info=info;
        //Estos siguientes apuntadores es más que nada para definir el
        //final del arbol.
        nuevo.izq=null;
        nuevo.der=null;
        //Este ciclo de if funciona para que cuando es la primera vez
        //que se ingresa un dato, este será dirigido a raíz.
        if(raiz==null)
        {
            raiz=nuevo;
        }else{
            //Sino se cumple la sentencia anterior es porque ya existe
            //un nodo raíz.
            Nodo anterior=null, reco;
            //reco será la variable que se necesitará para poder 
            //identificar a la raíz.
            reco=raiz;
            //Decimos que mientras reco sea diferente de null.
            while (reco!=null) 
            {
                //El nodo anterior será definido como la raiz, para 
                //crear subarboles.
                anterior=reco;
                //Si la informacion que se ingresa por primera vez, es
                //menor que la informacion del padre del subarbol.
                if (info<reco.info) 
                {
                    //diremos que reco será hijo izquierdo del padre para
                    //el subarbol.
                    reco=reco.izq;
                }else{
                    //De caso contrario será dirigido a ser el hijo derecho.
                    reco=reco.der;
                }
            }
            //En este ciclo volveremos a instanciar anterior para que sea
            //la informacion guardada para un nuevo dato.
            if (info<anterior.info) 
            {
                anterior.izq=nuevo;
            }else{
                anterior.der=nuevo;
            }
        }
    }
    //Estos siguientes metodos son para poder imprimir de tres maneras.
    //Para poder imprimir un arbol se dice que se puede hacerse el recorrido,
    //preorden, inorden y postorden.
    //Este primer metodo utilizaremos para imprimir en preorden.
    private void imprimirPre(Nodo reco)
    {
        //Si reco que es la variable que reconoce todo el arbol (dicese de
        //otra manera es el apuntador), es diferente de null, realizará el 
        //acomodo como lo marca el preorden (raíz, hijo izquierdo e hijo derecho).
        if (reco!=null)
        {
            //Imprimimos la informacion gracias a la recursividad, con el
            //siguiente formato. 
            System.out.print(reco.info+" ");
            imprimirPre(reco.izq);
            imprimirPre(reco.der);
        }
    }
    //En este metodo podemos acceder al metodo anterior en el cual le
    //ingestaremos la raiz del arbol.
    public void imprimirPre()
    {
        //Llamamos al metodo que recibe el parametro.
        imprimirPre(raiz);
        System.out.println();
    }
    //Continuamos con la siguiente manera de recorrido del arbol, ahora con
    //el inorden.
    //Todos los metodos utilizan la misma estructura, lo unico que cambia es
    //dentro del primer metodo de cada recorrido, y esto es por el orden en
    //se coloca la raiz del arbol.
    private void imprimirIn(Nodo reco) 
    {
        if (reco!=null) 
        {
            //Este recorrido lo hacemos de la siguiente manera:
            //Hijo izquierdo, raíz y el hijo derecho.
            imprimirIn(reco.izq);
            System.out.print(reco.info+" ");
            imprimirIn(reco.der);    
        }   
    }
    public void imprimirIn()
    {
        imprimirIn(raiz);
        System.out.println();
    }
    private void imprimirPost(Nodo reco)
    {
        if (reco!=null) 
        {
            //Como ultimo recorrido el postorden. Este se realiza yendo
            //del hijo izquierdo, hijo derecho y por ultimo la raíz.
            imprimirPost(reco.izq);
            imprimirPost(reco.der);
            System.out.print(reco.info+" ");
        }
    }
    public void imprimirPost()
    {
        imprimirPost(raiz);
        System.out.println();
    }
    //Recursivo
    //Se crea un metodo para obtener la altura en el que
    //recibe de parametros el apuntador de los nodos y una
    //nueva variable para almacenar el nivel.
    private void Altura(Nodo reco, int nivel)
    {
        //Recorremos cada nodo cuando sea diferente de null
        //esto es para que cuando sea igual a null detecte
        //que ya es una hoja.
        if (reco!=null) 
        {
            //Se usa la recursividad para que aumente el
            //valor de la vareable nivel esto es para pasar
            //por cada uno de los hijos.
            Altura(reco.izq, nivel+1);
            //Si el nivel es mayor a la altura quiere decir 
            //que ya debe de pasar de nivel.
            if (nivel>altura) 
            {
                //Se actualiza el valor.
                altura=nivel;    
            }
            //Se repite la recursividad para el siguiente hijo.
            Altura(reco.der, nivel+1);
        }
    }
    //Este metodo inicializará la recursion.
    public int Altura()
    {
        //Inicializa la variable de altura en 0.
        altura=0;
        //Ingresamos el nodo raiz de parametro para que 
        //inicie desde el mismo. y el nivel se inicia desde 1
        //esto es porque la raiz representa el primer nivel. 
        Altura(raiz, 1);
        //El valor que regresará el parametro será ya el 
        //numero de niveles que tiene. Cabe mencionar que
        //la altura se maneja por niveles, es decir, que si
        //un arbol tiene n niveles, n será su altura.
        return altura;
    }
}
