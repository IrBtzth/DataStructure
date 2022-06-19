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
```

## Insentar elementos en una lista

- **Lista vacia:** en esta caso es sencillo porque lista.primero = NULL, asi que es solo se crea un nuevo nodo y se hace que se apunte a ese.

``` C
 
  VARIABLE nuevoNodo : Nodo
  nuevoNodo.elemento = l
  nuevoNodo.siguiente = NULL
  lista.primero = nuevoNodo
 
```

- **Insertar al principio:**
``` C
 PROC InsertarPrincipio(l: Lista, b:libro)
  VARIABLE nuevoNodo: NODO
  nuevoNodo.elemento = b
  nuevoNodo.siguiente = l.primero
  l.primero = nuevoNodo

 FIN PROC
```

- **Insertar al final:** se recorre la lista hasta llegar al que no tenga puntero NULL. Luego se instancia el nuevo nodo y se hace que este ultimo elemento apunte a este nodo recien creado.

- **Insertar elementos en la enisima posicion:** si se quiere insertar un elemento despues de "n-element", se apunta a este "n-element" se instancia el nuevo nodo apuntando al siguiente "n+1-element", luego se apunta "n-element" al nuevo nodo.

## Eliminar un elemento de la lista

- **Eliminar al comienzo**

``` C
 PROC EliminarPrimero(l: Lista)
  VARIABLE temporal: Nodo
  
  temporal = l.primero
  l.primero = l.primero.siguiente
  
  ELIMINAR temporal

 FIN PROC
```
- **Eliminar al final**

``` C
 PROC EliminarUltimo(l: Lista)
  VARIABLE temporal: Nodo
  VARIABLE nodo: Nodo
  
  nodo = l.primero
  MIENTRAS (nodo.siguiente.siguiente != NULL)
      nodo = nodo.siguiente
  FIN MIENTRAS
  
  temporal = nodo.siguiente
  nodo.siguiente = NULL
  
  ELIMINAR temporal

 FIN PROC
```






