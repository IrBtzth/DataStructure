 # Listas enlazadas: Teoría
 
 Las lista estan compuesta de cabeza y cola. En el ultimo elemento de una lista apunta a una lista vacia.
 
 ## Ventajas
 
 Las lista no tienen porque estar de forma secuencia en memoria. Pueden tener longitud variable. Se puede agregar y quitar elementos en tiempo de ejecucion.
 
 ## Desventajas
 
 No tienen indice por lo tanto no se puede acceder a algun elemento sin antes haber recorrido los elementos anteriores del mismo. Necesitan mas espacio ya que deben guardar un valor y el puntero.
``` C
 ESTRUCTURA libro:
  cabeza : libro
    cola : PUNTERO A lista
FIN ESTRUCTURA    
}
```

``` C
 ESTRUCTURA nodo:
  elemento : libro
    siguiente : PUNTERO A nodo
FIN ESTRUCTURA    
}
```

``` C
 ESTRUCTURA lista:
  cabeza : PUNTERO A nodo
FIN ESTRUCTURA    
}
```

## Crear nodo

``` C
 FUNCION CrearNodo (l: libro): Nodo
  VARIABLE nuevoNodo : nodo
  nuevoNodo.elemento = l
  nuevoNodo.siguiente = NULO
FIN FUNCION    
}
```







