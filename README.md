# QuickSort

ggmen
class Class
    {
        //Aqui el usuario deduce el tamaño del vector
        static void Main()
        {
            int n;

            Console.Write("Cuantos longitud del vector: ");
            n = Int32.Parse(Console.ReadLine());
            Llenar b = new Llenar(n);
        }
    }
    //En esta clase aqui el usuario ingresa los valores de su vectores
    class Llenar
    {
        int h;
        int[] Vector;
        public Llenar(int n)
        {
            h = n;
            Vector = new int[h];
            for (int i = 0; i < h; i++)
            {
                Console.Write("ingrese valor {0}: ", i + 1);
                Vector[i] = Int32.Parse(Console.ReadLine());
            }
            QuickSort(Vector, 0, h - 1);
            Desplegar();
        }

        //En este metodo esta el ordenamiento QuickSort 
        public void QuickSort(int[] vector, int primero, int ultimo)
        {
            int i, j, central;
            double pivote;
            central = (primero + ultimo) / 2;
            pivote = vector[central];
            i = primero;
            j = ultimo;
            do
            {
                while (vector[i] < pivote) i++;
                while (vector[j] > pivote) j--;
                if (i <= j)
                {
                    int temp;
                    temp = vector[i];
                    vector[i] = vector[j];
                    vector[j] = temp;
                    i++;
                    j--;
                }
            } while (i <= j);

            if (primero < j)
            {
                QuickSort(vector, primero, j);
            }
            if (i < ultimo)
            {
                QuickSort(vector, i, ultimo);
            }
        }
        //Aqui solo de despliega el vector ordenado
        public void Desplegar()
        {
            Console.WriteLine("Vector ordenados en forma ascendente");
            for (int i = 0; i < h; i++)
            {
                Console.Write("{0} ", Vector[i]);
            }
            Console.ReadLine();
        }
    }
