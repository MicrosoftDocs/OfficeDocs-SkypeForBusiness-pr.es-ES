---
title: Cargar datos de inquilino y de edificio en el panel de calidad de llamadas (CQD)
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Obtenga información sobre cómo cargar datos de inquilino y de edificio en el panel de calidad de llamadas.
ms.openlocfilehash: 7a1f6de78e01a8988317aa99aae917aa0018e19a
ms.sourcegitcommit: 7e673b88346e07f7c777710437b19d257ccecb1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "50067145"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Cargar datos de inquilino y de edificio en el panel de calidad de llamadas (CQD)


Para sacar el máximo partido del panel de calidad de llamadas, le recomendamos que cargue los datos de inquilino y de edificio. Hay dos tipos de archivos de datos de inquilino: [Edificio y](#upload-building-data-file) punto de [conexión.](#endpoint-data-file)

Puede descargar una plantilla de datos de inquilino de [ejemplo aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true) Para obtener ayuda con la asignación de edificios, [lea Crear un mapa de edificio para el CQD.](CQD-building-mapping.md)

En el panel Informes de resumen  del CQD, seleccione Carga de datos del inquilino desde el menú Configuración del CQD  (un icono de engranaje en la parte superior del CQD). Desde aquí, los administradores pueden cargar la información del edificio y del punto de conexión de su organización, como la asignación de direcciones IP e información geográfica, la asignación de cada punto de acceso inalámbrico y su dirección MAC, etc.

1. Abra el CQD (en el Centro de administración de Teams o en), seleccione el icono de engranaje de la esquina superior derecha y elija Carga de datos del inquilino en la página Informes [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) **de** resumen. 

   ![Captura de pantalla del cuadro de diálogo que aparece mientras se cargan datos](media/qerguide-image-tenantdataupload.png)
    
2. Como alternativa, si es la primera vez que visita el CQD, se le pedirá que cargue los datos de creación. Puede seleccionar Cargar **ahora para ir** rápidamente a la página Carga de datos del **espacio** empresarial.

   ![Captura de pantalla de la pancarta que notifica a un usuario que debe cargar datos de creación](media/qerguide-image-buildingdatauploadbanner.png)

3. En la **página Carga de datos del** inquilino, seleccione **Examinar** para elegir un archivo de datos.

4. Después de seleccionar un archivo de datos, especifique **la fecha de** inicio y, opcionalmente, especifique una fecha de finalización.

5. Después de seleccionar **la fecha de** inicio, seleccione Cargar para cargar el archivo en el CQD.  <br><br>Antes de cargar el archivo, se valida. Si se produce un error en la validación, se muestra un mensaje de error en el que se solicita que se corrija el archivo. La figura siguiente muestra un error que se produce cuando el número de columnas del archivo de datos es incorrecto.

   ![Ejemplo de cuadro de diálogo que muestra un error de carga de datos de creación](media/qerguide-image-buildingdatauploaderror.png)
 
6. Si no se produce ningún error durante la validación, el archivo se cargará correctamente. A continuación, puede ver el archivo de datos cargado en la tabla Mis cargas, que muestra la lista completa de todos los archivos **cargados** para el inquilino actual en la parte inferior de la página.

> [!NOTE]
> Puede tardar hasta cuatro horas en finalizar el procesamiento del archivo de creación. <br><br> Si ya ha cargado un archivo de creación y necesita agregar subredes que podrían haber sido perdidas o excluidas, modifique el archivo original agregando las nuevas subredes, quite el archivo actual y vuelva a cargar el archivo editado. Solo puede haber un archivo de datos de creación activo en el CQD. 


## <a name="upload-building-data-file"></a>Cargar archivo de datos de creación

El primer tipo de archivo de datos de inquilino en el CQD es el **archivo de datos** De creación. La columna Subnet se deriva expandiendo la columna Network+NetworkRange y, después, uniendo la columna Subnet a la columna First Subnet o Second Subnet del registro de llamada para mostrar información de Building, City, Country o Region. El formato del archivo de datos que cargue debe cumplir los siguientes criterios para pasar la comprobación de validación antes de cargarlo:
  
- El archivo debe ser un archivo .tsv (las columnas están separadas por una tecla TAB) o un archivo .csv (las columnas se separan con una coma).

- El archivo de datos no incluye una fila de encabezado de tabla. Se espera que la primera línea del archivo de datos sean datos reales, no etiquetas de encabezado como "Red".

- Los tipos de datos del archivo solo pueden ser String, Integer o Boolean. Para el tipo de datos Integer, el valor debe ser un valor numérico. Los valores booleanos deben ser 0 o 1.

- Si una columna usa el tipo de datos String, un campo de datos puede estar vacío pero debe estar separado por una tabulación o una coma. Un campo de datos vacío simplemente asigna un valor de cadena vacío.

- Hay un límite de filas expandida de 1 000 000 por archivo de datos de espacio empresarial.

- Debe haber 15 columnas por cada fila, cada columna debe tener el tipo de datos adecuado y las columnas deben estar en el orden indicado en la tabla siguiente (delimitado por comas o tabulaciones):

  **Crear formato de archivo de datos**
  
  | Nombre de columna        | Tipo de datos | Ejemplo                   | Instrucciones              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | Obligatorio              |
  | NetworkName        | String    | USA/Seattle/SEATTLE-SEA-1 | Obligatorio<sup>1</sup>  |
  | NetworkRange       | Número    | 26                        | Obligatorio              |
  | BuildingName       | String    | SEATTLE-SEA-1             | Obligatorio<sup>1</sup>  |
  | OwnershipType      | String    | Contoso                   | Opcional              |
  | Tipo de edificio       | String    | Finalización de IT            | Opcional              |
  | BuildingOfficeType | String    | Ingeniería               | Opcional              |
  | Ciudad               | String    | Seattle                   | Recomendado           |
  | ZipCode            | String    | 98001                     | Recomendado           |
  | País            | String    | EE. UU.                        | Recomendado           |
  | Estado              | String    | WA                        | Recomendado           |
  | Region             | String    | MSUS                      | Recomendado           |
  | InsideCorp<sup>2</sup>         | Booleano      | 1             | Obligatorio              |
  | ExpressRoute<sup>3</sup>       | Booleano      | 0             | Obligatorio              |
  | VPN                | Booleano      | 0                         | Opcional              |

  <sup>1 Aunque</sup> el CQD no los necesita, las plantillas están configuradas para mostrar el nombre de edificio y red.

  <sup>2</sup> Esta configuración se puede usar para reflejar si la subred está dentro de la red corporativa o no. Puede personalizar el uso para otros fines.

  <sup>3 Esta</sup> configuración se puede usar para reflejar si la red usa Azure ExpressRoute o no. Puede personalizar el uso para otros fines.  

  **Fila de ejemplo:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> El rango de red se puede usar para representar una supernet (combinación de varias subredes con un solo prefijo de enrutamiento). Todas las nuevas cargas de creación se comprobarán por si hay rangos superpuestos. Si previamente ha cargado un archivo de creación, debe descargar el archivo actual y volver a cargarlo para identificar cualquier solapamiento y corregir el problema antes de volver a cargarlo. Cualquier superposición en archivos cargados anteriormente puede producir errores en la asignación de subredes a edificios en los informes. Algunas implementaciones VPN no informan de forma precisa sobre la información de subred. 
>
> La columna VPN es opcional y tendrá el valor predeterminado 0. Si el valor de la columna VPN se establece en 1, la subred representada por esa fila se ampliará por completo para coincidir con todas las direcciones IP de la subred. Use este programa con moderación y solo para las subredes VPN, ya que la ampliación completamente de estas subredes afectará negativamente a los tiempos de consulta en las consultas que impliquen generar datos. Si la expansión de la subred da como resultado que se supere el límite de 1000 000 filas de expansión, no se aceptará el archivo de creación.


### <a name="supernetting"></a>Supernetting

Puede usar supernetting, normalmente denominado enrutamiento de Inter-Domain clase (CIDR), en lugar de definir cada subred. Una *supernet* es una combinación de varias subredes que comparten un solo prefijo de enrutamiento. En lugar de agregar una entrada para cada subred, puede usar la dirección superespera. El supernetting es compatible, pero no se recomienda usarlo.

Por ejemplo, el edificio de marketing de Contoso está configurado con las subredes siguientes:

-   10.1.0.0/24: primera planta
-   10.1.1.0/24: segundo piso
-   10.1.2.0/24: tercera planta
-   10.1.3.0/24: cuarta planta

En lugar de agregar una entrada para cada subred, puede usar la dirección superespera (en este ejemplo, 10.1.0.0/22).

-   Red = 10.1.0.0
-   Intervalo de red = 22

Estos son algunos aspectos que debe tener en cuenta antes de implementar supernetos:

-   La supernetting solo se puede usar en una asignación de subred con máscaras de 8 bits a 28 bits.

-   El supernetismo requiere menos tiempo por adelantado, pero tiene el coste de reducir la riqueza de los datos. Supongamos que hay un problema de calidad relacionado con la subred 10.1.2.0. Si implementó supernetos, no sabrá dónde se encuentra la subred en la creación ni qué tipo de red es (por ejemplo, un laboratorio). Si ha definido todas las subredes de una edificio y la información de ubicación de la planta cargada, podrá ver esa distinción.

-   Es importante asegurarse de que la dirección superespera es correcta y no encuentra subredes no deseadas.

-   Es bastante común encontrar 192.168.0.0 en los datos. En muchas organizaciones, esto indica que el usuario se encuentra en casa. Para otros, este es el esquema de direcciones IP para una oficina satélite. Si su organización tiene oficinas que usan esta configuración, no la incluya en el archivo de creación porque es difícil distinguir entre las redes internas y locales mediante subredes [comunes.](quality-of-experience-review-guide.md#common-subnets) 

> [!IMPORTANT]
> El rango de red se puede usar para representar una supernet. Todas las nuevas cargas de archivos de datos de creación se comprobarán por si hay rangos superpuestos. Si previamente ha cargado un archivo de creación, debe descargar el archivo actual y cargarlo de nuevo para identificar cualquier solapamiento y corregir el problema. Los solapamientos en archivos cargados anteriormente pueden producir errores en la asignación de subredes a edificios en los informes.

### <a name="vpn"></a>VPN

Los datos de calidad de la experiencia (QoE) que los clientes envían a Microsoft 365 u Office 365, que es desde donde se recopilan los datos del CQD, incluyen una marca VPN. El CQD lo verá como las dimensiones Primera VPN y Segunda VPN. Sin embargo, esta marca depende de que los proveedores de VPN informen a Windows de que el adaptador de red VPN registrado es un adaptador de acceso remoto. No todos los proveedores de VPN registran correctamente adaptadores de acceso remoto. Por este problema, es posible que no pueda usar los filtros integrados de consulta de VPN. Use la columna VPN descrita anteriormente para marcar e identificar con precisión las subredes VPN. También es una buena práctica etiquetar las redes VPN para facilitar la identificación en los informes. A continuación se muestran dos ejemplos de cómo etiquetar las subredes VPN:

- Para definir **un nombre de** red, escriba "VPN" en este campo para las subredes VPN.

  ![Captura de pantalla del informe DESD que muestra una VPN con el nombre de la red](media/qerguide-image-vpnnetworkname.png)

- Para definir **un nombre de** edificio, escriba "VPN" en este campo para las subredes VPN.

  ![Captura de pantalla del informe DESLD que muestra una VPN con el nombre de edificio](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> Se sabe que las conexiones VPN han identificado de manera errónea el tipo de conexión de red como cableadas cuando la conexión subyacente es inalámbrica. Al mirar la calidad a través de conexiones VPN, no puede suponer que el tipo de conexión se ha identificado con precisión.

## <a name="endpoint-data-file"></a>Archivo de datos de punto de conexión

El otro tipo de archivo de datos del inquilino del CQD es el archivo de datos **de** extremo. Los valores de columna se utilizan en la columna First Client Endpoint Name o Second Client Endpoint Name del registro de llamada para mostrar la información sobre la marca, el modelo o el tipo del extremo del extremo. El formato del archivo de datos que cargue debe cumplir los siguientes criterios para pasar la comprobación de validación antes de cargarlo:

- El archivo debe ser un archivo .tsv (las columnas están separadas por una tecla TAB) o un archivo .csv (las columnas se separan con una coma).

- El contenido del archivo de datos no incluye encabezados de tabla. Se espera que la primera línea del archivo de datos sean datos reales, no una etiqueta de encabezado como "EndpointName".

- Las siete columnas usan solo el tipo de datos String. La longitud máxima permitida es de 64 caracteres.

- Un campo de datos puede estar vacío, pero debe separarse con una tabulación o una coma. Un campo de datos vacío simplemente asigna un valor de cadena vacío.

- EndpointName debe ser único, de lo contrario, se produce un error en la carga. Si hay una fila duplicada o dos filas que usan el mismo EndpointName, el conflicto provocará una unión incorrecta.

- EndpointLabel1, EndpointLabel2 y EndpointLabel3 son etiquetas personalizables. Pueden estar cadenas vacías o valores como "Departamento de TI designado portátil 2018" o "Etiqueta de activos 5678".

- Debe haber siete columnas para cada fila y las columnas deben estar en el siguiente orden:

  **Orden de campo:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Fila de ejemplo:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Actualizar un archivo de creación

Al recopilar información de generación y subred, los administradores suelen cargar el archivo de creación en varias iteraciones a lo largo del tiempo, agregando nuevas subredes y la información de creación cuando esté disponible. Cuando esto ocurra, deberá volver a cargar el archivo de creación. Este proceso es como la carga inicial tal y como se describe en la sección anterior, con algunas excepciones, como se indica en la sección siguiente.

> [!Important]
> Solo puede estar activo un archivo de creación a la vez. Los archivos de creación múltiples no son acumulativos.

## <a name="add-net-new-subnets"></a>Agregar nuevas subredes netas

En ocasiones necesitará agregar nuevas subredes de red al CQD que no formaban parte originalmente de la topología de red. Para agregar nuevas subredes netas, haga lo siguiente desde la página Carga de datos **del** inquilino en el CQD:

1.  Descargue el archivo original, si todavía no tiene una copia actualizada.

1.  Quite el archivo actual en el CQD.

1.  Edite el archivo de creación original y proporcione una fecha de finalización que se produzca al menos un día antes de que se adquieran las nuevas subredes netas.

1.  Anexe las nuevas subredes de red al archivo de creación original.

1.  Cargue el archivo de creación modificado y establezca la fecha de inicio de un día después de que finalice el archivo de creación anterior.

## <a name="add-missing-subnets"></a>Agregar subredes que faltan

Después de cargar la información de creación de las redes administradas, todas las redes administradas deben tener una asociación de edificios. Sin embargo, este no siempre será el caso; normalmente, se pierden algunas subredes. Para ver estas redes que faltan, revise el Informe de subred que falta **en** la **página** Informes de calidad de la experiencia del CQD. Esto presenta todas las subredes con 10 o más transmisiones de audio que no están definidas en el archivo de datos de creación y que se marcan como externas. Asegúrese de que no haya ninguna red administrada en esta lista. Si faltan subredes, use el procedimiento siguiente para actualizar el archivo de datos de creación original y volver a cargarlo en el CQD.

1. Vaya a la **página Carga de datos del** inquilino en el CQD.

1. Descargue el archivo original, si todavía no tiene una copia actualizada.

1. Quite el archivo actual en el CQD.

1. Anexe las nuevas subredes al archivo original.

1. Cargue el archivo de creación. Asegúrese de establecer la fecha de inicio como mínimo ocho meses antes para que el CQD procese datos históricos.


> [!IMPORTANT]
> Necesitará agregar el id. de inquilino como  filtro de consulta para el segundo id. de espacio empresarial a este informe para filtrar el informe y ver solo los datos del inquilino de su organización. En caso contrario, el informe mostrará las subredes federadas.

> [!NOTE] 
> Asegúrese de ajustar el filtro del informe Month Year al mes actual. Seleccione **Editar** y ajuste el filtro **del informe Month Year** para guardar el nuevo mes predeterminado.


## <a name="related-topics"></a>Temas relacionados

[Crear un mapa de edificio para el CQD](CQD-building-mapping.md)

[Mejorar y supervisar la calidad de las llamadas en Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Informes y datos del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)
