# Proyecto 5

El proyecto 5 consiste en llevar a cabo un procedimiento teórico que permita tomar una decisión con respecto al número de "servidores" necesarios para cierto proceso de vacunación, de forma tal que el sistema no exceda 100 personas en fila durante el 95% del tiempo de servicio. Posteriormente es necesario corroborar el resultado de los servidores y mostrar gráficamente el tiempo del sistema y el número de clientes que lo utilizan realizando una simulación utilizando Python. 

Antes que nada, se llevó a cabo la determinación teórica del número de servidores necesarios para cumplir el requisito. Para cumplir dicho propósito se realizó la estimación de la probabilidad de que más de cien personas se encontraran en la fila de vacunación, posteriormente utilizamos el sistema de colas M/M/29, el cual tiene un proceso de llegada y de servicio tipo Markov (de ahí la M) y un número s de servidores, para obtener el número de servidores. En este caso el número de servidores corresponde a veintinueve.

Para concluir, se procedió a modificar el código provisto para obtener dos gráficas que relacionaran el tiempo del sistema con respecto al número de usuarios que se encontraban en la fila y confirmar el número de servidores.  Por un lado, se concluyó para la primera grafica que únicamente el 0.26% del tiempo se encontraban más de cien personas en la fila, por el otro, en el caso de la segunda grafica se afirma que el 0.00% del tiempo más de cien personas se encontraban en la fila. Es importante tomar en cuenta que en ambas graficas se muestra una línea amarilla que cruza el eje vertical (clientes en el sistema, n) donde se identifica que el número de clientes en la fila es de 100, de esta forma es posible dimensionar gráficamente los resultados del tiempo cuando hay más de 100 solicitudes en fila.

De igual forma en ambos casos el periodo de tiempo no supera el 5%, por lo cual dicha especificación si se cumple. La conducta oscilatoria de la gráfica se debe al comportamiento de los estados y la duración de cada uno de ellos.

# Simulaciones ejecutadas
Se corre dos simulaciones para 50000 personas cada uno, aunque se puede bajar la cantidad de personas para que corresponda a 8 horas - se hizo con más de lo necesario para evidenciar las pocas veces que se excede el valor de 100 personas en el sistema.

```
Parámetro lambda = 7.0
Parámetro nu = 7.25
Tiempo con más de 100 solicitudes en fila:
	 0.26%
	 Sí cumple con la especificación.
Simulación es equivalente a 126.07 horas.
```

<img src="https://user-images.githubusercontent.com/20981514/127970177-de505437-408f-418f-b3b9-0acc3cc9657e.png" width="500"/>


```
Parámetro lambda = 7.0
Parámetro nu = 7.25
Tiempo con más de 100 solicitudes en fila:
	 0.00%
	 Sí cumple con la especificación.
Simulación es equivalente a 126.09 horas.
```
<img src="https://user-images.githubusercontent.com/20981514/127970184-37fa40dd-8659-4769-8d3c-6b93be9275ea.png" width="500"/>

# Criterio de estabilidad
Para que el sistema sea estable, se debe de cumplir:

`7/(0.25\*29) < 1`

Lo cual es verdadero, con lo que el sistema por lo menos podrá sostener la tasa de clientes que llega.
