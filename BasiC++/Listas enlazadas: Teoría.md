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
{- Esta es mi lista -}
bibloteca: lista

{- Accedo al primer nodo -}
bibloteca.primero

{- Accedo al primer libro -}
bibloteca.primero.elemento

{- Accedo al tercer nodo -}
bibloteca.primero.sguiente.siguiente

## Recorrer una lista

``` C
 FUNCION RecorrerLista (l: lista): Nodo
  VARIABLE puntero : Nodo
  puntero = l.cabeza
  MIENTRAS (puntero != NULO){
  ProcesarElemento(puntero.elemento)
  puntero = puntero.siguiente
  }
  
FIN FUNCION    
}

## Insentar elementos en una lista

- Lista vacia: en esta caso es sencillo porque lista.primero = NULL, asi que es solo se crea un nuevo nodo y se hace que se apunte a ese.

``` C
 
  VARIABLE nuevoNodo : Nodo
  nuevoNodo.elemento = l
  nuevoNodo.siguiente = NULL
  lista.primero = nuevoNod
    
}
```










