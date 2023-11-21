-Algoritmo Bodegas
		// Variables
		Define i Como Entero; // Indice del arreglo
		Define n, m Como Entero; // Numero de bodegas y productos por bodega
		Define cont, mayor As Entero; // Variables para contar productos
		Define mayorBodega, tipoMayor As Entero; // Bodega y tipo del producto en mayor cantidad
		Dimension arreglo[1 a 5, 1 a 10] Como Entero; // Arreglo que contiene la cantidad de productos de cada tipo en cada bodega
		
		// Inicialización
		n := 5; // Numero de bodegas
		m := 10; // Numero de productos por bodega
		mayor := 0; // Cantidad total de productos en la bodega con mayor cantidad
		tipoMayor := 0; // Cantidad total de productos de cada tipo
		
		// Rellenar el arreglo con los datos de las bodegas
		Para i := 1 Hasta 5 Hacer
			cont := 0;
			Para j := 1 Hasta 10 Hacer
				// Asignar a cada posición del arreglo una cantidad de productos aleatoria entre 1 y 100
				arreglo[i, j] := azar(1, 100);
				cont := cont + arreglo[i, j]; // Actualizar la cantidad total de productos en la bodega
			FinPara
			Escritar "La bodega ", i, " tiene un total de ", cont, " productos";
			
			// Comprobar si la cantidad total de productos en la bodega actual es mayor que la mayor cantidad encontrada hasta ahora
			Si cont > mayor Entonces
				mayor := cont; // Actualizar la cantidad total de productos en la bodega con mayor cantidad
				mayorBodega := i; // Actualizar el indice de la bodega con mayor cantidad
			FinSi
			// Actualizar la cantidad total de productos de cada tipo
			Para j := 1 Hasta 10 Hacer
				tipoMayor := tipoMayor + arreglo[j, i];
			FinPara
		FinPara
		
		// Determinar el producto en mayor cantidad y a que bodega corresponde
		cont := 0;
		Para i := 1 Hasta 10 Hacer
			Si arreglo[i, mayorBodega] > cont Entonces
				cont := arreglo[i, mayorBodega]; // Actualizar la cantidad de productos en mayor cantidad
				tipoMayor := i; // Actualizar el tipo del producto en mayor cantidad
			FinSi
		FinPara
		
		Escritar "El producto en mayor cantidad y a que bodega corresponde es el producto tipo ", tipoMayor, " y corresponde a la bodega ", mayorBodega;
FinAlgoritmo
