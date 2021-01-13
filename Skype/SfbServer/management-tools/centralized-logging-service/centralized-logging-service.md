---
title: Servicio de registro centralizado en Skype Empresarial 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Resumen: obtenga información sobre los componentes de servicio y las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015.'
ms.openlocfilehash: f4cb47204aa4970e0a86d5f1d556099b52afd07c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835270"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Servicio de registro centralizado en Skype Empresarial 2015
 
**Resumen:** Obtenga información sobre los componentes de servicio y las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015.
  
El servicio de registro centralizado puede: 
  
- Inicie o detenga el registro en uno o varios equipos y grupos de servidores con un único comando desde una ubicación central.
    
- Registros de búsqueda en uno o más equipos y grupos de servidores. Puedes personalizar la búsqueda para devolver todos los registros de todas las máquinas o devolver resultados más concisos.
    
- Configurar las sesiones de registro de la siguiente manera:
    
  - Defina un **Escenario** o use un escenario predeterminado. Un escenario del servicio de registro centralizado se conste de ámbito (global o de sitio), un nombre de escenario para identificar el propósito del escenario y uno o más proveedores. Puede ejecutar el escenario predeterminado y uno definido en cualquier momento en un equipo.
    
  - Use un proveedor existente o cree un nuevo proveedor. Aprovider define lo que recopila la sesión de registro, qué nivel de detalle, qué componentes se deben seguir y qué marcas se aplican.
    
    > [!TIP]
    >  Si está familiarizado con OCSLogger, los termproviders se **refieren** **a** la colección de componentes **(por** ejemplo, S4, SIPStack), un tipo de registro (por ejemplo, WPP, EventLog o archivo de registro de IIS), un nivel de seguimiento (por ejemplo, All, verbose, debug) y marcas **(por** ejemplo, TF_COMPONENT, TF_DIAG). Estos elementos se definen en el proveedor (una variable Windows PowerShell) y se pasan al comando Servicio de registro centralizado.
  
  - Configurar registros para equipos y grupos específicos.
    
  - Defina el ámbito de la sesión de registro desde las opciones Sitio **(para** ejecutar capturas de registro solo en equipos de ese sitio) o **Global** (para ejecutar capturas de registro en todos los equipos de la implementación).
    
El servicio de registro centralizado es una herramienta de solución de problemas eficaz para problemas grandes o pequeños, desde el análisis de la causa raíz hasta los problemas de rendimiento. Todos los ejemplos se muestran con el Shell de administración de Skype Empresarial Server. Se proporciona ayuda para la herramienta de línea de comandos a través de la propia herramienta, pero hay un conjunto limitado de funciones que se pueden ejecutar desde la línea de comandos. Al usar el Shell de administración de Skype Empresarial Server, tiene acceso a un conjunto de características mucho más grande y mucho más configurable, por lo que siempre debe ser su primera opción. 
  
## <a name="logging-service-components"></a>Componentes del servicio de registro

 El servicio de registro centralizado se ejecuta en todos los servidores de la implementación y está configurado por los siguientes agentes y servicios:
  
- El agente clsAgent del servicio de registro centralizado se ejecuta en todos los equipos con Skype Empresarial Server implementado. Escucha ( en los puertos **TCP 50001-50003**) los comandos de ClsController a través de WCF y envía respuestas de vuelta al controlador. Administra las sesiones de registro (inicio,detén/actualización) y busca registros. También realiza operaciones de mantenimiento, como el archivado de registros y las purgas. 
    
- Cmdlets del controlador de servicio de registro centralizado El Shell de administración de Skype Empresarial Server envía comandos Start, Stop, Flush y Search a ClsAgent. Cuando se envían comandos de búsqueda, los registros resultantes se devuelven al ClsControllerLib.dll y se agregan. El controlador envía comandos al agente, recibe el estado de esos comandos y administra los datos del archivo de registro de búsqueda a medida que se devuelven de todos los agentes en cualquier equipo del ámbito de búsqueda y agrega los datos de registro en un conjunto de resultados significativo y ordenado. La información de los siguientes temas se centra en el uso del Shell de administración de Skype Empresarial Server.
    
**Comunicaciones clsController con ClsAgent**

![Relación entre CLSController y CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Los comandos se emiten mediante la interfaz de línea de comandos de Windows Server o mediante el Shell de administración de Skype Empresarial Server. Los comandos se ejecutan en el equipo en el que ha iniciado sesión y se envían al ClsAgent localmente o a los demás equipos y grupos de servidores de la implementación.
  
ClsAgent mantiene un archivo de índice de todos los archivos . Archivos CACHÉ que tiene en el equipo local. ClsAgent los asigna para que se distribuyen uniformemente entre los volúmenes definidos por la opción CacheFileLocalFolders, sin consumir nunca más del 80 % de cada volumen (es decir, la ubicación de caché local y el porcentaje se pueden configurar mediante el cmdlet **Set-CsClsConfiguration).** ClsAgent también es responsable de la aging de archivos antiguos de registro de seguimiento de eventos en caché (.etl) fuera del equipo local. Después de dos semanas (es decir, el período de tiempo se puede configurar con el cmdlet **Set-CsClsConfiguration),** estos archivos se copian en un recurso compartido de archivos y se eliminan del equipo local. Para obtener más información, [consulte Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Cuando se recibe una solicitud de búsqueda, los criterios de búsqueda se usan para seleccionar el conjunto de archivos .etl almacenados en caché para realizar la búsqueda en función de los valores del índice mantenido por el agente.
  
> [!NOTE]
> ClsAgent puede buscar los archivos que se mueven al recurso compartido de archivos desde el equipo local. Una vez que ClsAgent mueve los archivos al recurso compartido de archivos, ClsAgent no mantiene la eliminación y la eliminación de archivos. Debe definir una tarea administrativa para supervisar el tamaño de los archivos del recurso compartido de archivos y eliminarlos o archivarlos. 
  
Los archivos de registro resultantes se pueden leer y analizar con una variedad de herramientas, como **Snooper.exe** y cualquier herramienta que pueda leer un archivo de texto, como **Notepad.exe**. Snooper.exe forma parte de las herramientas de depuración de Skype Empresarial Server 2015 y está disponible como [descarga web.](https://go.microsoft.com/fwlink/p/?LinkId=285257)
  
Al igual que OCSLogger, el servicio de registro centralizado tiene varios componentes con los que hacer un seguimiento y proporciona opciones para seleccionar marcas, como TF_COMPONENT y TF_DIAG. El servicio de registro centralizado también conserva las opciones de nivel de registro de OCSLogger.
  
La ventaja más importante de usar el Shell de administración de Skype Empresarial Server en la línea de comandos ClsController es que puede configurar y definir nuevos escenarios con proveedores seleccionados destinados al espacio del problema, las marcas personalizadas y los niveles de registro. Los escenarios disponibles para ClsController se limitan a los que se definen para el archivo ejecutable.
  
En versiones anteriores, se OCSLogger.exe para permitir a los administradores y al personal de soporte técnico recopilar archivos de seguimiento de los equipos de la implementación. OCSLogger, para todos sus puntos fuertes, tenía una desventaja. Solo se podían recopilar registros en un equipo a la vez. Puede iniciar sesión en varios equipos mediante copias independientes de OCSLogger, pero terminó con varios registros y sin una forma sencilla de agregar los resultados.
  
Cuando un usuario solicita una búsqueda de registro, clsController determina a qué equipos enviar la solicitud (es decir, en función de los escenarios seleccionados). También determina si la búsqueda debe enviarse al recurso compartido de archivos donde se encuentran los archivos .etl guardados. Cuando los resultados de la búsqueda se devuelven al ClsController, el controlador combina los resultados en un único conjunto de resultados ordenado por tiempo que se presenta al usuario. Los usuarios pueden guardar los resultados de la búsqueda en su equipo local para realizar un análisis posterior.
  
Cuando se inicia una sesión de registro, se especifican escenarios relativos al problema que se intenta resolver. Puede tener dos escenarios en ejecución en cualquier momento. Uno de estos dos escenarios debe ser el escenario AlwaysOn. Como su nombre indica, siempre debe estar ejecutándose en la implementación, recopilando información en todos los equipos, grupos y componentes.
  
> [!IMPORTANT]
> De forma predeterminada, el escenario AlwaysOn no se está ejecutando en la implementación. Debe iniciar explícitamente el escenario. Una vez iniciado, seguirá ejecutándose hasta que se detenga explícitamente y el estado de ejecución persistirá durante los reinicios de los equipos. Para obtener más información sobre los escenarios de inicio y detención, consulte Iniciar o detener la captura de registros de CLS en [Skype Empresarial Server 2015.](start-or-stop-log-capture.md) 
  
Cuando se produzca un problema, inicie un segundo escenario relacionado con el problema notificado. Reproduzca el problema y detenga el registro del segundo escenario. Inicie las búsquedas de registro relativas al problema notificado. La colección agregada de registros genera un archivo de registro que contiene mensajes de seguimiento de todos los equipos del sitio o del ámbito global de la implementación. Si la búsqueda devuelve más datos de los que puede analizar (normalmente conocido como relación señal-ruido, donde el ruido es demasiado alto), ejecute otra búsqueda con parámetros más estrechos. En este punto, puede empezar a observar patrones que se muestran y pueden ayudarle a centrarse más claramente en el problema. En última instancia, después de realizar un par de búsquedas refinadas, puede encontrar datos relevantes para el problema y averiguar la causa raíz.
  
> [!TIP]
> Cuando se le presente un escenario de problema en Skype Empresarial Server, empiece por preguntarse "¿Qué sé ya sobre el problema?". Si cuantifica los límites del problema, puede eliminar una gran parte de las entidades operativas en Skype Empresarial Server. 
  
Considere un escenario de ejemplo en el que sepa que los usuarios no están obteniendo resultados actuales cuando buscan un contacto. No tiene sentido buscar problemas en los componentes multimedia, Telefonía IP empresarial, conferencias y otros componentes. Lo que puede que no sepa es dónde está realmente el problema: en el cliente o es un problema del lado servidor? El replicador de usuarios recopila los contactos de Active Directory y se entregan al cliente mediante el servidor de libreta de direcciones (ABServer). AbServer obtiene sus actualizaciones de la base de datos RTC (donde el replicador de usuarios las escribió) y las recopila en los archivos de la libreta de direcciones de forma predeterminada : 1:30 a.m. Los clientes de Skype Empresarial Server recuperan la nueva libreta de direcciones según una programación aleatoria. Dado que sabe cómo funciona el proceso, puede reducir la búsqueda de la posible causa de un problema relacionado con los datos recopilados de Active Directory por el replicador de usuarios, el ABServer no recupera y crea los archivos de la libreta de direcciones o los clientes no descargan el archivo de la libreta de direcciones.
  
## <a name="current-configuration"></a>Configuración actual

El servicio de registro centralizado está configurado para definir lo que el servicio de registro pretende recopilar, cómo se recopila, de dónde se recopilará y cuál es la configuración de registro. Estas configuraciones se definen globalmente (es decir, para toda la implementación) o para un sitio (es decir, un sitio con nombre en la implementación). Cualquier registro que defina utilizará las configuraciones apropiadas para la identidad que utiliza para iniciar, detener, vaciar y buscar registros.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Para mostrar la configuración actual del servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. Escriba lo siguiente en un símbolo del sistema:
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Puede restringir o expandir el ámbito de las opciones de configuración que se devuelven mediante la definición y un ámbito, como "Site:Redmond" para devolver sólo CsClsConfiguration para el sitio  `-Identity` Redmond. Si desea obtener información detallada sobre una parte determinada de la configuración, puede canalizar el resultado a otro cmdlet Windows PowerShell configuración. Por ejemplo, para obtener detalles sobre los escenarios definidos en la configuración del sitio "Redmond", escriba: `Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Salida de ejemplo de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    El resultado del cmdlet muestra la configuración actual del servicio de registro centralizado.
    
|**Configuración**|**Descripción**|
|:-----|:-----|
|**Identidad** <br/> |Identifica el ámbito y el nombre de esta configuración. Hay solamente una configuración global y una configuración por sitio.  <br/> |
|**Scenarios** <br/> |Listado de todos los escenarios que se definen para esta configuración.  <br/> |
|**SearchTerms** <br/> |Términos de búsqueda definidos para la configuración. Microsoft 365 u Office 365, no las implementaciones locales.  <br/> |
|**SecurityGroups** <br/> |Grupos de seguridad definidos que controlan quiénes (es decir, miembros de los grupos de seguridad) pueden ver equipos basados en el sitio en el que se encuentran. El sitio, en este contexto, es el sitio tal como se define en el Generador de topologías.  <br/> |
|**Regiones** <br/> |Las regiones definidas se utilizan para reunir SecurityGroups en una región, por ejemplo EMEA.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |El parámetro indica el tamaño máximo del archivo de registro antes de que se cree un nuevo archivo de registro de seguimiento de eventos (.etl). Un nuevo archivo de registro se crea cuando se alcanza el tamaño definido incluso si aún no se ha alcanzado el tiempo máximo establecido en EtlFileRolloverMinutes.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Cantidad máxima definida de tiempo, en minutos, que puede durar un registro antes de que se cree un nuevo archivo .etl. Un nuevo archivo de registro se crea cuando expira el tiempo definido incluso si aún no se ha alcanzado el tamaño máximo establecido en EtlFileRolloverSizeMB.  <br/> |
|**TmfFileSearchPath** <br/> |Ubicación en la que se buscará archivos con formato de mensaje de seguimiento.  <br/> |
|**CacheFileLocalFolders** <br/> |Ruta definida de la ubicación en la que se escriben los archivos de caché en los equipos. CLSAgent escribe los archivos de caché y se ejecuta en el contexto del servicio de red. En este caso, %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. De manera predeterminada, los archivos de caché y los archivos de registro se escriben en el mismo directorio.  <br/> |
|**CacheFileNetworkFolder** <br/> |Puede definir una ruta de acceso UNC (convención de nomenclatura universal) para recibir los archivos de caché durante las operaciones de registro.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Definido como el tiempo máximo, en días, que se pueden retener los archivos de caché.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Definido como el porcentaje de espacio en disco que pueden utilizar los archivos de caché.  <br/> |
|**ComponentThrottleLimit** <br/> |Definido como la cantidad máxima de seguimientos por segundo que puede producir un componente antes de que se active el limitador de aceleración automático.  <br/> |
|**ComponentThrottleSample** <br/> |Cantidad de veces en 60 segundos que puede excederse el ComponentThrottleLimit.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |La versión mínima del CLSAgent que se permite ejecutar. Este elemento está pensado para Microsoft 365 u Office 365.  <br/> |
   

