---
title: Cargar inquilino y datos de compilación en el panel de calidad de llamadas (CQD)
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
description: Aprenda a cargar inquilino y a crear datos en el panel de calidad de llamadas (CQD).
ms.openlocfilehash: 37499cf2715a3cabb05ab5039a19190190253b07
ms.sourcegitcommit: c1aaf1f81c07c0956095b5bd4cb241b1de67b189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "46897840"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Cargar inquilino y datos de compilación en el panel de calidad de llamadas (CQD)


Para sacar el máximo provecho del panel de calidad de llamadas (CQD), le recomendamos que cargue su espacio empresarial y los datos de compilación. Hay dos tipos de archivos de datos de inquilinos, [creación](#upload-building-data-file) y [finalización](#endpoint-data-file).

[Aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)puede descargar una plantilla de datos de un inquilino de ejemplo. Para obtener ayuda con la creación de asignaciones, lea [crear un mapa de creación para el CQD](CQD-building-mapping.md).

En el panel informes de resumen del CQD, seleccione **carga de datos de inquilino** en el menú de **configuración** del CQD (un icono de engranaje en la parte superior del CQD). Desde aquí, los administradores pueden cargar la información de compilación y de extremo de su organización, como la asignación de direcciones IP e información geográfica, la asignación de cada punto de acceso inalámbrico y su dirección MAC, etc.

1. Abra el CQD (desde el centro de administración de Teams, o en [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ), seleccione el icono de engranaje en la esquina superior derecha y elija **carga de datos de inquilino** en la página informes de **Resumen** .

   ![Captura de pantalla del cuadro de diálogo que aparece mientras se cargan los datos](media/qerguide-image-tenantdataupload.png)
    
2. Como alternativa, si esta es la primera vez que visita el CQD, se le pedirá que cargue los datos de compilación. Puede seleccionar **cargar ahora** para desplazarse rápidamente a la página de **carga de datos de inquilino** .

   ![Captura de pantalla de banner que notifica a un usuario que debe cargar datos de compilación](media/qerguide-image-buildingdatauploadbanner.png)

3. En la página **carga de datos de inquilino** , seleccione **examinar** para elegir un archivo de datos.

4. Después de seleccionar un archivo de datos, especifique **fecha de inicio** y, opcionalmente, especifique una fecha de finalización.

5. Después de seleccionar **fecha de inicio**, seleccione **cargar** para cargar el archivo en el CQD. <br><br>Antes de que se cargue el archivo, se valida. Si se produce un error en la validación, se muestra un mensaje de error en el que se le pide que corrija el archivo. En la siguiente ilustración se muestra un error que se produce cuando el número de columnas del archivo de datos es incorrecto.

   ![Ejemplo de cuadro de diálogo que muestra un error de carga de datos de compilación](media/qerguide-image-buildingdatauploaderror.png)
 
6. Si no se producen errores durante la validación, la carga del archivo se realizará correctamente. Puede ver el archivo de datos cargado en la tabla **mis cargas** , que muestra la lista completa de todos los archivos cargados para el inquilino actual en la parte inferior de la página.

> [!NOTE]
> Puede demorar hasta cuatro horas en finalizar el procesamiento del archivo de creación. <br><br> Si ya ha cargado un archivo de compilación y necesita agregar subredes que puedan haberse perdido o excluido, modifique el archivo original agregando las nuevas subredes, quite el archivo actual y vuelva a cargar el archivo recién editado. Solo puede haber un archivo de datos de construcción activo en el CQD. 


## <a name="upload-building-data-file"></a>Cargar archivo de datos de compilación

El primer tipo de archivo de datos de inquilino en el CQD es el archivo de datos de **compilación** . La columna subred se deriva expandiendo la columna red + rango, luego se une la columna subred a la primera subred de la llamada o la segunda subred para mostrar la información de la región o el edificio, la ciudad, el país o la región. El formato del archivo de datos que cargue debe cumplir los siguientes criterios para pasar la comprobación de validación antes de la carga:
  
- El archivo debe ser un archivo. TSV (las columnas están separadas por una TABULAción) o un archivo. csv (las columnas se separan con una coma).

- El archivo de datos no incluye una fila de encabezado de tabla. Se espera que la primera línea del archivo de datos sea datos reales, no etiquetas de encabezado como "Network".

- Los tipos de datos en el archivo solo pueden ser de cadena, entero o booleano. Para el tipo de datos Integer, el valor debe ser un valor numérico. Los valores booleanos deben ser 0 o 1.

- Si una columna usa el tipo de datos String, un campo de datos puede estar vacío, pero aún debe estar separado por una tabulación o una coma. Un campo de datos vacío simplemente asigna un valor de cadena vacía.

- Debe haber 14 columnas por cada fila, cada columna debe tener el tipo de datos adecuado, y las columnas deben estar en el orden indicado en la siguiente tabla (coma o delimitado por tabulaciones):

  **Crear formato de archivo de datos**
  
  | Nombre de columna        | Tipo de datos | Ejemplo                   | Instrucciones              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | Obligatorio              |
  | Red        | String    | Estados Unidos/Seattle/SEATTLE-mar-1 | Requerido<sup>1</sup>  |
  | NetworkRange       | Número    | 26                        | Obligatorio              |
  | BuildingName       | String    | SEATTLE-MAR-1             | Requerido<sup>1</sup>  |
  | Propiedad      | String    | Dpto                   | Opcional              |
  | Edificio       | String    | Finalización de ti            | Opcional              |
  | BuildingOfficeType | String    | Integración               | Opcional              |
  | Ciudad               | String    | Seattle                   | Recomendado           |
  | ZipCode            | String    | 98001                     | Recomendado           |
  | Tercer            | String    | DÉJEN                        | Recomendado           |
  | Estado              | String    | WA                        | Recomendado           |
  | Region             | String    | MSUS                      | Recomendado           |
  | InsideCorp<sup>2</sup>         | Booleano      | 1             | Obligatorio              |
  | ExpressRoute<sup>3</sup>       | Booleano      | ,0             | Obligatorio              |
  | VPN                | Booleano      | ,0                         | Opcional              |

  <sup>1</sup> aunque el CQD no lo requiera, las plantillas se configuran para mostrar la creación y el nombre de red.

  <sup>2</sup> esta configuración se puede usar para reflejar si la subred está dentro de la red corporativa. Puede personalizar el uso de otros propósitos.

  <sup>3</sup> esta configuración se puede usar para reflejar si la red usa Azure ExpressRoute. Puede personalizar el uso de otros propósitos.  

  **Fila de ejemplo:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> El intervalo de red se puede usar para representar una superred (combinación de varias subredes con un único prefijo de enrutamiento). Todas las nuevas cargas de creación se marcarán para todos los intervalos superpuestos. Si ha cargado previamente un archivo de compilación, debe descargar el archivo actual y volver a cargarlo para identificar cualquier solapamiento y corregir el problema antes de volver a cargar. Cualquier solapamiento de los archivos cargados previamente puede dar lugar a asignaciones erróneas de subredes a edificios de los informes. Ciertas implementaciones de VPN no informan con precisión de la información de subred. 
>
> La columna VPN es opcional y se establecerá de forma predeterminada en 0. Si el valor de la columna VPN se establece en 1, la subred representada por esa fila se expandirá completamente para coincidir con todas las direcciones IP de la subred.  Use esto con moderación y solo para las subredes VPN, ya que la expansión de estas subredes tendrá un impacto negativo en los tiempos de las consultas para las consultas que impliquen datos de compilación.


### <a name="supernetting"></a>Superredes

Puede usar superredes, denominadas comúnmente enrutamiento entre dominios con clases (CIDR), en lugar de definir cada subred. Una *superred* es una combinación de varias subredes que comparten un único prefijo de enrutamiento. En lugar de agregar una entrada para cada subred, puede usar la dirección de superredes. Es compatible con la superredes, pero no recomendamos que lo uses.

Por ejemplo, la creación de marketing de Contoso está formada por las subredes siguientes:

-   10.1.0.0/24 — primer piso
-   10.1.1.0/24, segundo piso
-   10.1.2.0/24, tercer piso
-   10.1.3.0/24, cuarto piso

En lugar de agregar una entrada para cada subred, puede usar la dirección de superredes, en este ejemplo, 10.1.0.0/22.

-   Network = 10.1.0.0
-   Intervalo de red = 22

Estas son algunas cosas que debe tener en cuenta antes de implementar la superredes:

-   La superredes solo se puede usar en una asignación de subred con una máscara de 8 bits a 28 bits.

-   La superredes tarda menos tiempo en cargarse, pero es el costo de reducir la riqueza de los datos. Supongamos que hay un problema de calidad que afecta a la subred 10.1.2.0. Si ha implementado la superredes, no sabrá en qué lugar de la creación se encuentra la subred ni qué tipo de red (por ejemplo, un laboratorio). Si definiste todas las subredes para un edificio y cargó información de ubicación del piso, podrás ver esa distinción.

-   Es importante asegurarse de que la dirección de superredes sea correcta y de que no se detecte ninguna subred no deseada.

-   Es muy común buscar 192.168.0.0 en los datos. Para muchas organizaciones, esto indica que el usuario está en casa. Para otros, este es el esquema de dirección IP de una oficina satélite. Si su organización tiene oficinas que usan esta configuración, no la incluya en el archivo de creación porque es difícil distinguir entre las redes domésticas y domésticas mediante [subredes comunes](quality-of-experience-review-guide.md#common-subnets). 

> [!IMPORTANT]
> El intervalo de red se puede usar para representar un superred. Todas las nuevas cargas de archivos de datos de creación se verificarán para los intervalos superpuestos. Si ha cargado previamente un archivo de compilación, debe descargar el archivo actual y cargarlo de nuevo para identificar cualquier solapamiento y corregir el problema. Cualquier solapamiento de los archivos cargados previamente puede dar lugar a asignaciones erróneas de subredes a edificios de los informes.

### <a name="vpn"></a>VPN

Los datos de la calidad de la experiencia (QoE) que los clientes envían a Microsoft 365 u Office 365, que es donde se origenn los datos del CQD: incluye una marca de VPN. El CQD verá esto como la primera dimensión VPN y del segundo. Sin embargo, esta marca depende de los informes de proveedores de VPN para Windows que el adaptador de red VPN registrado es un adaptador de acceso remoto. No todos los proveedores de VPN registran correctamente adaptadores de acceso remoto. Por este motivo, es posible que no pueda usar los filtros de consulta de VPN integrados. Use la columna VPN descrita anteriormente para marcar y identificar con precisión subredes VPN. También es buena práctica etiquetar las redes VPN para facilitar la identificación en los informes. A continuación se muestran dos ejemplos de cómo etiquetar las subredes VPN:

- Defina un **nombre de red** escribiendo "VPN" en este campo para subredes VPN.

  ![Captura de pantalla de informe QCD que muestra VPN con nombre de red](media/qerguide-image-vpnnetworkname.png)

- Defina un **nombre de edificio** escribiendo "VPN" en este campo para subredes VPN.

  ![Captura de pantalla de informe QCD que muestra VPN con el nombre de creación](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> Se sabe que las conexiones VPN no identifican correctamente el tipo de conexión de red como cableada cuando la conexión subyacente es inalámbrica. Al mirar la calidad de las conexiones VPN, no puede dar por sentado que el tipo de conexión se ha identificado correctamente.

## <a name="endpoint-data-file"></a>Archivo de datos de extremo

El otro tipo de archivo de datos de inquilino del CQD es el archivo de datos del **extremo** . Los valores de columna se usan en el primer nombre de punto de conexión de cliente del registro de llamada o el segundo nombre de punto de conexión de cliente para mostrar la información de tipo, modelo o fabricante de puntos de conexión. El formato del archivo de datos que cargue debe cumplir los siguientes criterios para pasar la comprobación de validación antes de la carga:

- El archivo debe ser un archivo. TSV (las columnas están separadas por una TABULAción) o un archivo. csv (las columnas se separan con una coma).

- El contenido del archivo de datos no incluye encabezados de tabla. Se espera que la primera línea del archivo de datos sea datos reales, no una etiqueta de encabezado como "EndpointName".

- Las seis columnas solo usan el tipo de datos String. La longitud máxima permitida es de 64 caracteres.

- Un campo de datos puede estar vacío, pero aún debe estar separado por una tabulación o una coma. Un campo de datos vacío simplemente asigna un valor de cadena vacía.

- EndpointName debe ser único; de lo contrario, se producirá un error en la carga. Si hay una fila duplicada o dos filas que usan la misma EndpointName, el conflicto provocará una combinación incorrecta.

- EndpointLabel1, EndpointLabel2 y EndpointLabel3 son etiquetas personalizables. Pueden ser cadenas vacías o valores como "equipo de ti designado 2018 portátil" o "etiqueta de activo 5678".

- Debe haber seis columnas por cada fila y las columnas deben estar en el siguiente orden:

  **Orden de los campos:**

  EndpointName, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Fila de ejemplo:**

  `1409W3534, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018,`  


## <a name="update-a-building-file"></a>Actualizar un archivo de compilación

Al recopilar la información de creación y de subred, los administradores cargarán el archivo de compilación en varias iteraciones a lo largo del tiempo, agregando nuevas subredes y la información de compilación cuando esté disponible. Cuando esto sucede, tendrá que volver a cargar el archivo de compilación. Este proceso es como la carga inicial según se describe en la sección anterior, con algunas excepciones, tal y como se indica en la siguiente sección.

> [!Important]
> Solo puede haber un archivo de compilación activo cada vez. No se acumulan varios archivos de compilación.

## <a name="add-net-new-subnets"></a>Agregar subredes nuevas

En ocasiones, tendrá que agregar subredes nuevas a el CQD que no eran parte de su topología de red. Para agregar subredes nuevas, haga lo siguiente desde la página de **carga de datos de inquilino** en el CQD:

1.  Descargue el archivo original, si aún no tiene una copia actualizada.

1.  Quitar el archivo actual del CQD.

1.  Edite el archivo de creación original y proporcione una fecha de finalización que se produzca al menos un día antes de que se hayan adquirido las nuevas subredes.

1.  Anexe las subredes nuevas al archivo de creación original.

1.  Cargue el archivo de generación que acaba de modificar y establezca la fecha de inicio de un día después de que finalice el archivo de compilación anterior.

## <a name="add-missing-subnets"></a>Agregar subredes que faltan

Después de cargar la información de creación para redes administradas, cada red administrada debe tener una asociación de compilación. Sin embargo, esto no siempre será así; Normalmente, se pierden algunas subredes. Para encontrar estas redes perdidas, revise el **Informe de subred perdida** en la página de **informes de calidad de la experiencia** en el CQD. Esto presenta todas las subredes con 10 o más flujos de audio que no se definen en el archivo de datos de compilación y se marcan como externos. Asegúrese de que no hay redes administradas en esta lista. Si faltan subredes, use el procedimiento siguiente para actualizar el archivo de datos de creación original y volver a cargarlo en el CQD.

1. Vaya a la página de **carga de datos de inquilino** en el CQD.

1. Descargue el archivo original, si aún no tiene una copia actualizada.

1. Quitar el archivo actual del CQD.

1. Anexe las nuevas subredes al archivo original.

1. Cargue el archivo de creación. Asegúrese de establecer la fecha de inicio al menos ocho meses antes para que el CQD procese los datos históricos.


> [!IMPORTANT]
> Tendrá que agregar su identificador de inquilino como filtro de consulta para el **segundo identificador de inquilino** a este informe para filtrar el informe para ver solo los datos de inquilinos de su organización. En caso contrario, el informe mostrará subredes federadas.

> [!NOTE] 
> Asegúrese de ajustar el filtro de informe de año mensual al mes en curso. Seleccione **Editar**y ajuste el filtro de informe **mes de año** para guardar el nuevo mes predeterminado.


## <a name="related-topics"></a>Temas relacionados

[Crear un mapa de creación para el CQD](CQD-building-mapping.md)

[Mejorar y supervisar la calidad de las llamadas de los equipos](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de flujo en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar los datos del CQD](CQD-Power-BI-query-templates.md)
