<img src="https://bit.ly/2VnXWr2" alt="Ironhack Logo" width="100" align="right"/>

<img src="https://www.fullestop.com/blog/wp-content/uploads/2019/03/The-Future-of-E-Commerce-Unpredictable-But-Revolutionar.jpg" alt="Google Analytics Project" width="300"/>


#  Final Project Ironhack Data Bootcamp
*Jorge Álvarez*

*Data Part Time Barcelona May 2019*


## Content
- [Project Description](#project)
- [Dataset](#dataset)
- [Workflow](#workflow)
    * [EDA + Preprocessing](#preprocessing)


<a name="project"></a>
## Project Description

En este proyecto vamos a predecir el valor del ciclo de vida del cliente.

## Dataset

Online Retail Data Set 
[Online Retail Data Set]https://www.kaggle.com/vijayuv/onlineretail

<a name="workflow"></a>


## Workflow

<a name="preprocessing"></a>


### Preprocessing

El Dataset contiene productos comprados, agrupados por factura y por cliente.
<br><br>Contiene 8 variables:

- **Numericas**
    - Continuas: UnitPrice 
    - Discretas: Quantity

- **Categoricas**
    - Ordinales:
    - Nominales: CustomerID, InvoiceNo, Description, StockCode, Country
- **Otras**
    - Fecha: InvoiceDate
    
    
<a name="eda"></a>


### EDA

Las variables Description y CustomerID contienen valores nulos.

Description: 1.454 null
CustomerID: 135.080 null

#### EDA de InvoiceNo

**Conclusión**: todas las facturas que comienzan con "C" son facturas negativas, y las facturas que contienen 7 caracteres comienzan con "C"

**Acción**: eliminaremos los registros negativos porque solo analizamos las facturas que se compraron.

#### EDA de Quantity
**Conclusión**: El conjunto de datos contiene valores de "Cantidad" entre -80.995 y 80.995. Los valores negativos representan compras devueltas o fallidas.

**Acción**: eliminaremos los valores negativos porque solo analizamos las facturas que se compraron.

#### EDA de InvoiceDate
**Conclusión**: El conjunto de datos contiene el último mes de 2010 y todos los meses de 2011.

**Comentarios**: No tenemos ventas los sábados (puede ser un error o no)

#### EDA de CustomerID
**Conclusión**: el conjunto de datos contiene 134.697 cutómeros con valores de Nan

**Acción**: eliminaremos a los clientes, porque vamos a trabajar en los CustomerID's

#### EDA Conclusion
**Datos Negativos**: Representan devoluciones de productos y/o facturas y se mantendrán.
**CustomerID nullos**: Se eliminarán, ya que se trabajará en base a clientes.
