---
title: Cargar datos de inquilino y compilación en el Panel de calidad de llamadas (CQD)
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Obtenga información sobre cómo cargar inquilinos y crear datos en el Panel de calidad de llamadas.
ms.openlocfilehash: d999098a2d920c8709ae1878ac94648451c00f0b
ms.sourcegitcommit: 548978550d58f8657d7035b57b736e9cf9b15984
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2022
ms.locfileid: "69163230"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Cargar datos de inquilino y compilación en el Panel de calidad de llamadas (CQD)


Para aprovechar al máximo el Panel de calidad de llamadas, le recomendamos que cargue su inquilino y cree datos. Hay 2 tipos de archivos de datos del inquilino, [compilación](#upload-building-data-file) y [punto de conexión](#endpoint-data-file).

Puede descargar una plantilla de datos de inquilino de ejemplo [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true). Para obtener ayuda con la asignación de compilaciones, lea [Crear un mapa de creación para el CQD](CQD-building-mapping.md).

En el panel Informes de resumen del CQD, seleccione **Carga de datos del inquilino** en el menú **Configuración** del CQD (un icono de engranaje en la parte superior del CQD). Desde aquí, los administradores pueden cargar la información de compilación y puntos de conexión de su organización, como la asignación de direcciones IP e información geográfica, la asignación de cada punto de acceso inalámbrico y su dirección MAC, etc.

1. Abra el CQD (desde el Centro de administración de Teams o en [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), seleccione el icono de engranaje en la esquina superior derecha y elija **Carga de datos del inquilino** en la página **Informes de resumen** .

   ![Captura de pantalla del cuadro de diálogo que aparece mientras se cargan los datos.](media/qerguide-image-tenantdataupload.png)
    
2. Como alternativa, si es la primera vez que visita el CQD, se le pedirá que cargue datos de compilación. Puede seleccionar **Cargar ahora** para ir rápidamente a la página **Carga de datos del inquilino** .

   ![Captura de pantalla del banner que notifica a un usuario que cargue datos de compilación.](media/qerguide-image-buildingdatauploadbanner.png)

3. En la página **Carga de datos del inquilino** , seleccione **Examinar** para elegir un archivo de datos.

4. Después de seleccionar un archivo de datos, especifique **Fecha de inicio** y, opcionalmente, especifique una fecha de finalización.

5. Después de seleccionar **Fecha de inicio**, seleccione **Cargar** para cargar el archivo en el CQD. <br><br>Antes de cargar el archivo, se valida. Si se produce un error en la validación, se muestra un mensaje de error solicitando que corrija el archivo. La figura siguiente muestra un error que se produce cuando el número de columnas del archivo de datos es incorrecto.

   ![Ejemplo de cuadro de diálogo que muestra un error de carga de datos de compilación.](media/qerguide-image-buildingdatauploaderror.png)
 
6. Si no se produce ningún error durante la validación, la carga del archivo se realizará correctamente. A continuación, puede ver el archivo de datos cargado en la tabla Mis cargas, que muestra la lista completa de todos los archivos **cargados** para el inquilino actual en la parte inferior de esa página.

> [!NOTE]
> El procesamiento del archivo de compilación puede tardar hasta cuatro horas. <br><br> Si ya ha cargado un archivo de compilación y necesita agregar subredes que podrían haberse perdido o excluido, modifique el archivo original agregando las nuevas subredes, quite el archivo actual y vuelva a cargar el archivo editado. Solo puede haber un archivo de datos de compilación activo en el CQD. 


## <a name="upload-building-data-file"></a>Cargar un archivo de datos de compilación

El primer tipo de archivo de datos del inquilino en el CQD es el archivo de datos **de compilación** . La columna Subred se deriva expandiendo la columna Network+NetworkRange y, después, uniendo la columna Subred a la columna First Subnet o Second Subnet del registro de llamada para mostrar información de edificio, ciudad, país o región. El formato del archivo de datos que cargue debe cumplir los siguientes criterios para pasar la comprobación de validación antes de cargarlo:
  
- El archivo debe ser un archivo .tsv (las columnas están separadas por una tecla TAB) o un archivo .csv (las columnas están separadas por comas).

- El archivo de datos no incluye una fila de encabezado de tabla. Se espera que la primera línea del archivo de datos sean datos reales, no etiquetas de encabezado como "Red".

- Los tipos de datos del archivo solo pueden ser String, Integer o Boolean. Para el tipo de datos Integer, el valor debe ser un valor numérico. Los valores booleanos deben ser 0 o 1.

- Si una columna usa el tipo de datos String, un campo de datos puede estar vacío, pero debe separarse con una tabulación o una coma. Un campo de datos vacío simplemente asigna un valor String vacío.

- Hay un límite de fila ampliado de 1 000 000 por archivo de datos de inquilino.

- Debe haber 15 columnas para cada fila, cada columna debe tener el tipo de datos adecuado y las columnas deben estar en el orden indicado en la tabla siguiente (delimitadas por comas o tabulaciones):

  **Crear formato de archivo de datos**
  
  | Nombre de columna        | Tipo de datos | Ejemplo                   | Instrucciones              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | Obligatorio              |
  | NetworkName        | String    | EE. UU./Seattle/SEATTLE-SEA-1 | Necesario<sup>1</sup>  |
  | NetworkRange       | Número    | 26                        | Obligatorio              |
  | BuildingName       | String    | SEATTLE-MAR-1             | Necesario<sup>1</sup>  |
  | Tipo de propiedad      | String    | Contoso                   | Opcional<sup>4</sup>  |
  | Tipo de edificio       | String    | Finalización de TI            | Opcional<sup>4</sup>  |
  | BuildingOfficeType | String    | Ingeniería               | Opcional<sup>4</sup>  |
  | Ciudad               | String    | Seattle                   | Recomendado           |
  | ZipCode            | String    | 98001                     | Recomendado           |
  | País            | String    | Nos                        | Recomendado           |
  | Estado              | String    | WA                        | Recomendado           |
  | Region             | String    | MSUS                      | Recomendado           |
  | InsideCorp<sup>2</sup>         | Booleano      | 1             | Obligatorio              |
  | ExpressRoute<sup>3</sup>       | Booleano      | 0             | Obligatorio              |
  | VPN                | Booleano      | 0                         | Opcional              |

  <sup>1</sup> Aunque no lo requiere el CQD, las plantillas están configuradas para mostrar La compilación y el nombre de la red.

  <sup>2</sup> Esta configuración se puede usar para reflejar si la subred está o no dentro de la red corporativa. Puedes personalizar el uso para otros fines.

  <sup>3</sup> Esta configuración se puede usar para reflejar si la red usa Azure ExpressRoute o no. Puedes personalizar el uso para otros fines.  
  
  <sup>4</sup> Aunque estas columnas opcionales reciben un nombre para sugerir con qué valores desea rellenarlas, puede personalizar el uso para otros fines. por ejemplo: Prioridad de red - `Tier 1, Tier 2, Tier 3` 

  **Fila de ejemplo:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> El rango de red se puede utilizar para representar una superred (combinación de varias subredes con un solo prefijo de enrutamiento). Todas las nuevas cargas de compilación se comprobarán en busca de intervalos superpuestos. Si ha cargado anteriormente un archivo de compilación, debe descargar el archivo actual y volver a cargarlo para identificar cualquier solapamiento y corregir el problema antes de volver a cargarlo. Cualquier superposición en los archivos cargados anteriormente puede producir asignaciones incorrectas de subredes a edificios en los informes. Algunas implementaciones VPN no notifican con precisión la información de subred. 
>
> La columna VPN es opcional y se convertirá de forma predeterminada en 0. Si el valor de la columna VPN se establece en 1, la subred representada por esa fila se ampliará por completo para que coincida con todas las direcciones IP dentro de la subred. Use esto con moderación y solo para las subredes VPN, ya que la ampliación total de estas subredes tendrá un impacto negativo en los tiempos de consulta de las consultas que implican la creación de datos. Si la expansión de la subred da como resultado que se supere el límite de fila de expansión de 1.000.000, no se aceptará el archivo de compilación.


### <a name="supernetting"></a>Supernetting

Puede usar la supernetting, que normalmente se denomina Enrutamiento de Inter-Domain sin clase (CIDR), en lugar de definir cada subred. Una *superred* es una combinación de varias subredes que comparten un solo prefijo de enrutamiento. En lugar de agregar una entrada para cada subred, puede usar la dirección super morena. La supernetting es compatible, pero no se recomienda su uso.

Por ejemplo, el edificio de marketing de Contoso se compone de las subredes siguientes:

-   10.1.0.0/24: primer piso
-   10.1.1.0/24: segundo piso
-   10.1.2.0/24: tercer piso
-   10.1.3.0/24: cuarto piso

En lugar de agregar una entrada para cada subred, puede usar la dirección super morena(en este ejemplo, 10.1.0.0/22).

-   Red = 10.1.0.0
-   Rango de red = 22

Estos son algunos aspectos que debe tener en cuenta antes de implementar la supernetting:

-   La supernetting solo se puede utilizar en una asignación de subred con máscara de 8 bits a 28 bits.

-   La superredting tarda menos tiempo por adelantado, pero tiene el costo de reducir la riqueza de los datos. Supongamos que hay un problema de calidad que implica la subred 10.1.2.0. Si implementó supernetting, no sabrá dónde se encuentra la subred en el edificio o qué tipo de red es (por ejemplo, un laboratorio). Si hubiera definido todas las subredes de un edificio y la información de ubicación de los pisos cargados, podrá ver esa distinción.

-   Es importante asegurarse de que la dirección super morenada sea correcta y no detecte subredes no deseadas.

-   Es bastante común encontrar 192.168.0.0 en los datos. En muchas organizaciones, esto indica que el usuario está en casa. Para otros, este es el esquema de direcciones IP para una oficina por satélite. Si su organización tiene oficinas que usan esta configuración, no la incluya en el archivo de compilación porque es difícil distinguir entre redes domésticas e internas mediante el uso de [subredes comunes](quality-of-experience-review-guide.md#common-subnets). 

> [!IMPORTANT]
> El rango de red se puede usar para representar una superred. Todas las nuevas cargas de archivos de datos de compilación se comprobarán en busca de rangos superpuestos. Si ha cargado anteriormente un archivo de compilación, debe descargar el archivo actual y cargarlo de nuevo para identificar los solapamientos y corregir el problema. Cualquier superposición en los archivos cargados anteriormente podría dar lugar a asignaciones incorrectas de subredes a edificios en los informes.

### <a name="vpn"></a>VPN

La calidad de los datos de la experiencia (QoE) que los clientes envían a Microsoft 365 o Office 365, que es de donde proceden los datos del CQD, incluye una marca VPN. El CQD verá esto como las dimensiones Primera VPN y Segunda VPN. Sin embargo, esta marca se basa en que los proveedores de VPN informan a Windows de que el adaptador de red VPN registrado es un adaptador de acceso remoto. No todos los proveedores de VPN registran correctamente adaptadores de acceso remoto. Por este motivo, es posible que no puedas usar los filtros de consulta de VPN integrados. Usa la columna VPN analizada anteriormente para marcar e identificar con precisión las subredes VPN. También es recomendable etiquetar las redes VPN para facilitar su identificación en sus informes. A continuación se muestran dos ejemplos de cómo etiquetar las subredes VPN:

- Defina un **Nombre de red** escribiendo "VPN" en este campo para las subredes VPN.

  ![Captura de pantalla del informe QCD que muestra una VPN usando el nombre de la red.](media/qerguide-image-vpnnetworkname.png)

- Defina un **Nombre de edificio** escribiendo "VPN" en este campo para las subredes VPN.

  ![Captura de pantalla del informe QCD que muestra VPN usando el nombre del edificio.](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> Se sabe que las conexiones VPN identifican incorrectamente el tipo de conexión de red como cableadas cuando la conexión subyacente es inalámbrica. Al analizar la calidad a través de conexiones VPN, no puedes suponer que el tipo de conexión se haya identificado con precisión.

## <a name="endpoint-data-file"></a>Archivo de datos de punto de conexión

El otro tipo de archivo de datos del inquilino del CQD es el archivo de datos **del punto de conexión** . Los valores de columna se usan en la columna Nombre del punto de conexión del primer cliente del registro de llamada o Segundo nombre del punto de conexión de cliente para mostrar la información de marca, modelo o tipo del punto de conexión. El formato del archivo de datos que cargue debe cumplir los siguientes criterios para pasar la comprobación de validación antes de cargarlo:

- El archivo debe ser un archivo .tsv (las columnas están separadas por una tecla TAB) o un archivo .csv (las columnas están separadas por comas).

- El contenido del archivo de datos no incluye encabezados de tabla. Se espera que la primera línea del archivo de datos sean datos reales, no una etiqueta de encabezado como "EndpointName".

- Las siete columnas usan solo el tipo de datos String. La longitud máxima permitida es de 64 caracteres.

- Las entradas distinguen mayúsculas de minúsculas; EndpointName **ABC123** se tratará como único de EndpointName **abc123**.

- Un campo de datos puede estar vacío, pero debe separarse con una tabulación o una coma. Un campo de datos vacío simplemente asigna un valor String vacío.

- EndpointName debe ser único; de lo contrario, se producirá un error en la carga. Si hay una o dos filas duplicadas que usan el mismo EndpointName, el conflicto provocará una unión incorrecta.

- EndpointLabel1, EndpointLabel2 y EndpointLabel3 son etiquetas personalizables. Pueden estar vacíos Cadenas o valores como "Portátil designado por el departamento de TI 2018" o "Etiqueta de activo 5678".

- Debe haber siete columnas para cada fila y las columnas deben estar en el siguiente orden:

  **Orden de campos:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Fila de ejemplo:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Actualizar un archivo de compilación

Al recopilar información de compilación y subred, los administradores suelen cargar el archivo de compilación en varias iteraciones a lo largo del tiempo, agregando nuevas subredes y su información de compilación a medida que esté disponible. Cuando esto ocurra, tendrá que volver a cargar el archivo de compilación. Este proceso es como la carga inicial, como se describe en la sección anterior, con algunas excepciones, como se indica en la siguiente sección.

> [!Important]
> Solo un archivo de compilación puede estar activo a la vez. Varios archivos de compilación no son acumulativos.

## <a name="add-net-new-subnets"></a>Agregar nuevas subredes netas

Hay ocasiones en las que necesitará agregar nuevas subredes netas al CQD que originalmente no formaban parte de la topología de red. Para agregar nuevas subredes netas, haga lo siguiente desde la página **Carga de datos del inquilino** en el CQD:

1.  Descargue el archivo original, si aún no tiene una copia actualizada.

1.  Quitar el archivo actual en el CQD.

1.  Edite el archivo de compilación original y proporcione una fecha de finalización que tenga lugar al menos un día antes de que se adquiriesen las nuevas subredes netas.

1.  Anexe las nuevas subredes de red al archivo de compilación original.

1.  Cargue el archivo de compilación modificado recientemente y establezca la fecha de inicio para un día después de que finalice el archivo de compilación anterior.

## <a name="add-missing-subnets"></a>Agregar subredes que faltan

Después de cargar la información de compilación para redes administradas, todas las redes administradas deben tener una asociación de creación. Sin embargo, esto no siempre será el caso; normalmente, se pierden algunas subredes. Para encontrar estas redes que faltan, revise el **Informe de subred que falta** en la página **Informes de calidad de la experiencia** en el CQD. Esto presenta todas las subredes con 10 o más transmisiones de audio que no están definidas en el archivo de datos de compilación y se marcan como externas. Asegúrese de que no haya redes administradas en esta lista. Si faltan subredes, use el procedimiento siguiente para actualizar el archivo de datos de compilación original y volver a cargarlo en el CQD.

1. Vaya a la página **Carga de datos del inquilino** en el CQD.

1. Descargue el archivo original, si aún no tiene una copia actualizada.

1. Quitar el archivo actual en el CQD.

1. Anexar las nuevas subredes al archivo original.

1. Cargue el archivo de compilación. Asegúrese de establecer la fecha de inicio como mínimo ocho meses antes para que el CQD procese datos históricos.


> [!IMPORTANT]
> Tendrá que agregar su id. de inquilino como filtro de consulta para **second Tenant ID** a este informe para filtrar el informe y ver solo los datos del inquilino de su organización. En caso contrario, el informe mostrará las subredes federadas.

> [!NOTE] 
> Asegúrese de ajustar el filtro del informe Mes del año al mes actual. Seleccione **Editar** y ajuste el filtro de informe **Mes año** para guardar el nuevo mes predeterminado.


## <a name="related-topics"></a>Temas relacionados

[Crear un mapa de creación para el CQD](CQD-building-mapping.md)

[Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)
