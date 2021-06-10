---
title: Upload inquilino y generar datos en el Panel de calidad de llamadas (CQD)
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
description: Obtenga información sobre cómo cargar inquilinos y crear datos en el Panel de calidad de llamadas (CQD).
ms.openlocfilehash: 7a1f6de78e01a8988317aa99aae917aa0018e19a
ms.sourcegitcommit: 7e673b88346e07f7c777710437b19d257ccecb1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "50067145"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Upload inquilino y generar datos en el Panel de calidad de llamadas (CQD)


Para sacar el máximo partido del Panel de calidad de llamadas (CQD), le recomendamos que cargue los datos de inquilino y de creación. Hay 2 tipos de archivos de datos de inquilino, [Edificio](#upload-building-data-file) y [Punto de conexión.](#endpoint-data-file)

Puede descargar una plantilla de datos de inquilino de ejemplo [aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true) Para obtener ayuda con la asignación de edificios, lea [Crear un mapa de creación para CQD](CQD-building-mapping.md).

En el panel Informes de resumen de CQD, seleccione Datos de **inquilino Upload** en el menú Configuración CQD (un icono de engranaje en la parte superior de CQD).  Desde aquí, los administradores pueden cargar la información de creación y punto de conexión de su organización, como asignación de direcciones IP e información geográfica, asignación de cada punto de acceso inalámbrico y su dirección MAC, etc.

1. Abra CQD (desde el centro de administración de Teams o en) y, a continuación, seleccione el icono de engranaje en la esquina superior derecha y elija Datos de inquilino Upload en la página Informes de [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) resumen.  

   ![Captura de pantalla del cuadro de diálogo que aparece mientras se cargan los datos](media/qerguide-image-tenantdataupload.png)
    
2. Como alternativa, si es la primera vez que visita CQD, se le pedirá que cargue datos de creación. Puede seleccionar Upload **Ahora para** ir rápidamente a la página Datos del espacio **empresarial Upload** usuario.

   ![Captura de pantalla de banner que notifica a un usuario que cargue datos de creación](media/qerguide-image-buildingdatauploadbanner.png)

3. En la **página Datos Upload** inquilino, seleccione **Examinar** para elegir un archivo de datos.

4. Después de seleccionar un archivo de datos, especifique **la fecha de inicio** y, opcionalmente, especifique una fecha de finalización.

5. Después de seleccionar **Fecha de inicio,** **Upload** para cargar el archivo en CQD. <br><br>Antes de cargar el archivo, se valida. Si se produce un error en la validación, se muestra un mensaje de error en el que se le solicita que corrija el archivo. En la siguiente ilustración se muestra un error que se produce cuando el número de columnas del archivo de datos es incorrecto.

   ![Ejemplo de cuadro de diálogo que muestra un error de carga de datos de creación](media/qerguide-image-buildingdatauploaderror.png)
 
6. Si no se producen errores durante la validación, la carga del archivo se realizará correctamente. A continuación, puede ver el archivo de datos cargado en la tabla Mis cargas, que muestra la lista completa de todos los archivos **cargados** para el inquilino actual en la parte inferior de esa página.

> [!NOTE]
> Puede tardar hasta cuatro horas en finalizar el procesamiento del archivo de creación. <br><br> Si ya ha cargado un archivo de creación y necesita agregar subredes que podrían haber perdido o excluido, modifique el archivo original agregando las nuevas subredes, quite el archivo actual y vuelva a cargar el archivo recién editado. Solo puede haber un archivo de datos de creación activo en CQD. 


## <a name="upload-building-data-file"></a>Upload crear un archivo de datos

El primer tipo de archivo de datos de inquilino en CQD es **el archivo de** datos De creación. La columna Subred se deriva expandiendo la columna Network+NetworkRange y, a continuación, uniendo la columna Subred a la columna Primera subred o Segunda subred del registro de llamada para mostrar información de creación, ciudad, país o región. El formato del archivo de datos que cargue debe cumplir los siguientes criterios para superar la comprobación de validación antes de cargarlo:
  
- El archivo debe ser un archivo .tsv (las columnas están separadas por una PESTAÑA) o un archivo .csv (las columnas están separadas por una coma).

- El archivo de datos no incluye una fila de encabezado de tabla. Se espera que la primera línea del archivo de datos sean datos reales, no etiquetas de encabezado como "Red".

- Los tipos de datos del archivo solo pueden ser Cadena, Entero o Booleano. Para el tipo de datos Entero, el valor debe ser un valor numérico. Los valores booleanos deben ser 0 o 1.

- Si una columna usa el tipo de datos String, un campo de datos puede estar vacío, pero debe estar separado por una pestaña o coma. Un campo de datos vacío solo asigna un valor String vacío.

- Hay un límite de filas expandido de 1000 000 por archivo de datos de inquilino.

- Debe haber 15 columnas para cada fila, cada columna debe tener el tipo de datos adecuado y las columnas deben estar en el orden indicado en la tabla siguiente (delimitada por comas o tabulaciones):

  **Crear formato de archivo de datos**
  
  | Nombre de columna        | Tipo de datos | Ejemplo                   | Instrucciones              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | Obligatorio              |
  | NetworkName        | String    | EE.UU./Seattle/SEATTLE-SEA-1 | Obligatorio<sup>1</sup>  |
  | NetworkRange       | Número    | 26                        | Obligatorio              |
  | BuildingName       | String    | SEATTLE-SEA-1             | Obligatorio<sup>1</sup>  |
  | OwnershipType      | String    | Contoso                   | Opcional              |
  | BuildingType       | String    | Finalización de IT            | Opcional              |
  | BuildingOfficeType | String    | Ingeniería               | Opcional              |
  | Ciudad               | String    | Seattle                   | Recomendado           |
  | ZipCode            | String    | 98001                     | Recomendado           |
  | País            | String    | EE. UU.                        | Recomendado           |
  | Estado              | String    | WA                        | Recomendado           |
  | Region             | String    | MSUS                      | Recomendado           |
  | InsideCorp<sup>2</sup>         | Booleano      | 1             | Obligatorio              |
  | ExpressRoute<sup>3</sup>       | Booleano      | 0             | Obligatorio              |
  | VPN                | Booleano      | 0                         | Opcional              |

  <sup>1 Aunque</sup> CQD no lo requiere, las plantillas están configuradas para mostrar el nombre de la creación y la red.

  <sup>2</sup> Esta configuración se puede usar para reflejar si la subred está o no dentro de la red corporativa. Puede personalizar el uso para otros fines.

  <sup>3 Esta</sup> configuración se puede usar para reflejar si la red usa o no Azure ExpressRoute. Puede personalizar el uso para otros fines.  

  **Fila de ejemplo:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> El rango de red se puede usar para representar una supernet (combinación de varias subredes con un único prefijo de enrutamiento). Todas las cargas de edificio nuevas se comprobarán si hay rangos superpuestos. Si previamente ha cargado un archivo de creación, debe descargar el archivo actual y volver a cargarlo para identificar cualquier superposición y solucionar el problema antes de cargarlo de nuevo. Cualquier superposición de archivos cargados previamente puede dar lugar a asignaciones incorrectas de subredes a edificios en los informes. Algunas implementaciones de VPN no informan con precisión de la información de subred. 
>
> La columna VPN es opcional y tendrá el valor predeterminado 0. Si el valor de la columna VPN se establece en 1, la subred representada por esa fila se expandirá por completo para que coincida con todas las direcciones IP de la subred. Use esto con moderación y solo para subredes VPN, ya que la expansión total de estas subredes tendrá un impacto negativo en los tiempos de consulta para las consultas que implican la creación de datos. Si la expansión de la subred da como resultado el límite de fila de expansión de 1.000.000 superado, no se aceptará el archivo de creación.


### <a name="supernetting"></a>Supernetting

Puede usar la supernetting, comúnmente denominada Enrutamiento sin Inter-Domain (CIDR), en lugar de definir cada subred. Una *supernet* es una combinación de varias subredes que comparten un único prefijo de enrutamiento. En lugar de agregar una entrada para cada subred, puede usar la dirección superconsonada. La supernetting es compatible, pero no se recomienda usarlo.

Por ejemplo, el edificio de marketing de Contoso está hecho de las subredes siguientes:

-   10.1.0.0/24: primer piso
-   10.1.1.0/24: segundo piso
-   10.1.2.0/24: tercer piso
-   10.1.3.0/24: cuarto piso

En lugar de agregar una entrada para cada subred, puede usar la dirección superconsonada(en este ejemplo, 10.1.0.0/22).

-   Red = 10.1.0.0
-   Rango de red = 22

Estas son algunas cosas que debe tener en cuenta antes de implementar la supernetting:

-   La supernetting solo se puede usar en una asignación de subred con una máscara de 8 bits a 28 bits.

-   La supernetting tarda menos tiempo por adelantado, pero se produce a costa de reducir la riqueza de los datos. Supongamos que hay un problema de calidad relacionado con la subred 10.1.2.0. Si implementó la supernetting, no sabrá dónde se encuentra la subred en el edificio ni qué tipo de red es (por ejemplo, un laboratorio). Si hubiera definido todas las subredes de un edificio y la información de ubicación de la planta cargada, podría ver esa distinción.

-   Es importante asegurarse de que la dirección superada es correcta y no captura subredes no deseadas.

-   Es bastante común encontrar 192.168.0.0 en los datos. Para muchas organizaciones, esto indica que el usuario está en casa. Para otros usuarios, este es el esquema de direcciones IP para una oficina satélite. Si su organización tiene oficinas que usan esta configuración, no la incluya en el archivo de creación porque es difícil distinguir entre redes internas e internas mediante subredes [comunes.](quality-of-experience-review-guide.md#common-subnets) 

> [!IMPORTANT]
> El rango de red se puede usar para representar una supernet. Todas las cargas de archivos de datos de creación nuevas se comprobarán si hay rangos superpuestos. Si previamente ha cargado un archivo de creación, debe descargar el archivo actual y cargarlo de nuevo para identificar cualquier superposición y solucionar el problema. Cualquier superposición en archivos cargados previamente puede dar como resultado asignaciones incorrectas de subredes a edificios en los informes.

### <a name="vpn"></a>VPN

La calidad de los datos de experiencia (QoE) que los clientes envían a Microsoft 365 o Office 365,que es de donde se origenn los datos CQD, incluye una marca VPN. CQD verá esto como las dimensiones Primera VPN y Segunda VPN. Sin embargo, esta marca se basa en los informes de los proveedores de VPN para Windows que el adaptador de red VPN registrado es un adaptador de acceso remoto. No todos los proveedores de VPN registran correctamente adaptadores de acceso remoto. Debido a esto, es posible que no pueda usar los filtros de consulta de VPN integrados. Use la columna VPN descrita anteriormente para marcar e identificar con precisión las subredes VPN. También es una buena práctica etiquetar las redes VPN para facilitar la identificación en los informes. A continuación se muestran dos ejemplos de cómo etiquetar las subredes VPN:

- Para definir **un nombre de red,** escriba "VPN" en este campo para las subredes VPN.

  ![Captura de pantalla del informe de QCD que muestra la VPN con el nombre de red](media/qerguide-image-vpnnetworkname.png)

- Para definir **un nombre de edificio,** escriba "VPN" en este campo para subredes VPN.

  ![Captura de pantalla del informe de QCD en la que se muestra la VPN con el nombre del edificio](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> Se ha sabido que las conexiones VPN identificaron erróneamente el tipo de conexión de red como cableada cuando la conexión subyacente es inalámbrica. Al ver la calidad a través de las conexiones VPN, no puede suponer que el tipo de conexión se ha identificado con precisión.

## <a name="endpoint-data-file"></a>Archivo de datos de punto de conexión

El otro tipo de archivo de datos de inquilino CQD es el **archivo de** datos de punto de conexión. Los valores de columna se usan en la columna Nombre del primer punto de conexión de cliente o Segundo nombre del punto de conexión de cliente del registro de llamada para mostrar información de marca, modelo o tipo del punto de conexión del punto de conexión. El formato del archivo de datos que cargue debe cumplir los siguientes criterios para superar la comprobación de validación antes de cargarlo:

- El archivo debe ser un archivo .tsv (las columnas están separadas por una PESTAÑA) o un archivo .csv (las columnas están separadas por una coma).

- El contenido del archivo de datos no incluye encabezados de tabla. Se espera que la primera línea del archivo de datos sean datos reales, no una etiqueta de encabezado como "EndpointName".

- Las siete columnas solo usan el tipo de datos String. La longitud máxima permitida es de 64 caracteres.

- Un campo de datos puede estar vacío, pero debe estar separado por una pestaña o coma. Un campo de datos vacío solo asigna un valor String vacío.

- EndpointName debe ser único, de lo contrario, se produce un error en la carga. Si hay una fila duplicada o dos filas que usan el mismo EndpointName, el conflicto provocará una unión incorrecta.

- EndpointLabel1, EndpointLabel2 y EndpointLabel3 son etiquetas personalizables. Pueden estar vacías Cadenas o valores como "Departamento de TI designado portátil 2018" o "Etiqueta de activo 5678".

- Debe haber siete columnas para cada fila y las columnas deben estar en el orden siguiente:

  **Orden de campo:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Fila de ejemplo:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Actualizar un archivo de creación

Al recopilar información de creación y subred, los administradores suelen cargar el archivo de creación en varias iteraciones a lo largo del tiempo, agregando nuevas subredes y su información de creación a medida que esté disponible. Cuando esto ocurra, tendrá que volver a cargar el archivo de creación. Este proceso es como la carga inicial como se describe en la sección anterior, con algunas excepciones como se indica en la sección siguiente.

> [!Important]
> Solo un archivo de creación puede estar activo a la vez. Varios archivos de creación no son acumulativos.

## <a name="add-net-new-subnets"></a>Agregar nuevas subredes netas

Hay ocasiones en las que tendrá que agregar nuevas subredes netas a CQD que no formaban parte originalmente de la topología de red. Para agregar nuevas subredes netas, haga lo siguiente desde la página Datos **del espacio empresarial Upload** en CQD:

1.  Descargue el archivo original, si aún no tiene una copia actualizada.

1.  Quite el archivo actual en CQD.

1.  Edite el archivo de creación original y proporcione una fecha de finalización que se produzca al menos un día antes de la adquisición de las nuevas subredes netas.

1.  Anexe las nuevas subredes de red al archivo de creación original.

1.  Upload el archivo de creación modificado recientemente y establezca la fecha de inicio para un día después de que finalice el archivo de creación anterior.

## <a name="add-missing-subnets"></a>Agregar subredes que faltan

Después de cargar información de creación para redes administradas, todas las redes administradas deben tener una asociación de creación. Sin embargo, esto no siempre será el caso; por lo general, se pierden algunas subredes. Para buscar estas redes que faltan, revise el Informe de **subred que** falta en la **página Informes** de calidad de la experiencia en CQD. Esto presenta todas las subredes con 10 o más transmisiones de audio que no están definidas en el archivo de datos de creación y que se marcan como externas. Asegúrese de que no hay redes administradas en esta lista. Si faltan subredes, use el procedimiento siguiente para actualizar el archivo de datos de creación original y volver a cargarlo en CQD.

1. Vaya a la **página Datos Upload** inquilino en CQD.

1. Descargue el archivo original, si aún no tiene una copia actualizada.

1. Quite el archivo actual en CQD.

1. Anexar las nuevas subredes al archivo original.

1. Upload el archivo de creación. Asegúrese de establecer la fecha de inicio en al menos ocho meses antes para que CQD procese datos históricos.


> [!IMPORTANT]
> Tendrá que agregar su identificador de inquilino  como filtro de consulta para segundo identificador de inquilino a este informe para filtrar el informe para ver solo los datos de inquilino de su organización. En caso contrario, el informe mostrará subredes federadas.

> [!NOTE] 
> Asegúrese de ajustar el filtro de informe Año del mes al mes actual. Seleccione **Editar** y ajuste el filtro de informe **Año** del mes para guardar el nuevo mes predeterminado.


## <a name="related-topics"></a>Temas relacionados

[Crear un mapa de creación para CQD](CQD-building-mapping.md)

[Mejorar y supervisar la calidad de las llamadas Teams](monitor-call-quality-qos.md)

[¿Qué es CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Datos e informes de CQD](CQD-data-and-reports.md)

[Usar CQD para administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de secuencias en CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos CQD](CQD-Power-BI-query-templates.md)
