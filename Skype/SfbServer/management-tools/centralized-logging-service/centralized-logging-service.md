---
title: Servicio de registro centralizado en Skype Empresarial 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Resumen: Obtenga información sobre los componentes de servicio y opciones de configuración para el servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: 6f1766e97c318a11095aa2f064cd09a0785c1562
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877758"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Servicio de registro centralizado en Skype Empresarial 2015
 
**Resumen:** Obtenga información sobre los componentes de servicio y opciones de configuración para el servicio de registro centralizado en Skype para Business Server 2015.
  
El servicio de registro centralizado puede: 
  
- Iniciar o detener el registro en uno o varios equipos y grupos de servidores con un solo comando desde una ubicación central.
    
- Buscar registros en uno o más equipos y grupos. Puede adaptar la búsqueda para devolver todos los registros en todos los equipos o devolver los resultados más concisos.
    
- Configure las sesiones de registro de la siguiente manera:
    
  - Defina un **Escenario** o use un escenario predeterminado. Un escenario en el servicio de registro centralizado se compone de ámbito (global o sitio), un nombre de escenario para identificar el propósito del escenario y uno o más proveedores. Puede ejecutar el escenario predeterminado y un escenario definido en un momento dado en un equipo.
    
  - Use un proveedor existente o cree uno. Aprovider define lo que recopila la sesión de registro, ¿qué nivel de detalle, ¿qué componentes de seguimiento y se aplican los indicadores.
    
    > [!TIP]
    >  Si está familiarizado con OCSLogger, la termproviders hace referencia a la colección de **componentes** (por ejemplo, S4, SIPStack), un **tipo de registro** (por ejemplo, archivo de registro IIS, EventLog o WPP), un **nivel de seguimiento** (por ejemplo, todos los, verbose, debug) y los **indicadores** (por ejemplo, TF_COMPONENT, TF_DIAG). Estos elementos se definen en el proveedor (una variable de Windows PowerShell) y se pasan en el comando del servicio de registro centralizado.
  
  - Configurar los registros de determinados equipos y grupos de servidores.
    
  - Defina el ámbito para la sesión de registro desde las opciones **Sitio** (para ejecutar capturas de registro en equipos solo en ese sitio) o **Global** (para ejecutar capturas de registro en todos los equipos de la implementación).
    
El servicio de registro centralizado es una eficaz herramienta de solución de problemas para problemas grandes o pequeños, desde el análisis de causa raíz a problemas de rendimiento. Todos los ejemplos se muestran utilizando el Skype para Shell de administración de servidor empresarial. La propia herramienta brinda ayuda para la herramienta de línea de comandos, pero hay una serie limitada de funciones que se pueden ejecutar desde la línea de comandos. Mediante el uso de Skype para Shell de administración de servidor empresarial, tiene acceso a un conjunto mucho más grande y mucho más configurable de características, por lo siempre debe ser la primera opción. 
  
## <a name="logging-service-components"></a>Componentes del servicio de registro

 El servicio de registro centralizado se ejecuta en todos los servidores de la implementación y se compone de los siguientes servicios y agentes:
  
- Centralizado la agente de servicio de registro con ClsAgent se ejecuta en cada equipo con Skype para Business Server implementado. Escucha (en los puertos **TCP 50001-50003**) para los comandos de ClsController a través de WCF y envía respuestas al controlador. Administra las sesiones de registro (iniciar/detener/actualizar) y busca en los registros. Además, realiza tareas de mantenimiento, como la purga y el archivado de registros. 
    
- Centralizado registro servicio controlador Cmdlets el Skype para Shell de administración de Business Server envía comandos iniciar, detener, vaciado y búsqueda con la clsagent. Cuando se envían los comandos de búsqueda, los registros de resultados se devuelven a ClsControllerLib.dll y se agregan. El controlador envía comandos al agente, recibe el estado de esos comandos y administra los datos de los archivos de registro de búsqueda, tal como los devuelven todos los agentes de todos los equipos en el ámbito de búsqueda, y agrega los datos de registro en un conjunto de salida significativo y ordenado. La información en los temas siguientes se centra en utilizando el Skype para Shell de administración de servidor empresarial.
    
**Comunicaciones de ClsController con ClsAgent**

![Relación entre CLSController y CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Emitir comandos mediante la interfaz de línea de comandos de Windows Server o mediante el Skype de consola de administración de servidor empresarial. Los comandos se ejecutan en el equipo donde haya iniciado sesión y se envían a ClsAgent de forma local o a los demás equipos y grupos de la implementación.
  
ClsAgent mantiene un archivo de índice de todos los archivos .CACHE disponibles en la máquina local. ClsAgent los asigna de manera que se distribuyan uniformemente entre todos los volúmenes definidos por la opción CacheFileLocalFolders, sin consumir nunca más del 80 % de cada volumen (es decir, la ubicación de la memoria caché local y el porcentaje se pueden configurar con el cmdlet **Set-CsClsConfiguration**). ClsAgent también es responsable de limpiar los archivos de registro de seguimiento de eventos (.etl) antiguos almacenados en la memoria caché de la máquina local. Después de dos semanas (que es el período de tiempo que se puede configurar con el cmdlet **Set-CsClsConfiguration**), estos archivos se copian a un recurso compartido de archivos y se eliminan del equipo local. Para más detalles, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Cuando se recibe una solicitud de búsqueda, se usan los criterios de búsqueda para seleccionar el conjunto de archivos .etl en la memoria caché a fin de realizar la búsqueda en función de los valores del índice que mantiene el agente.
  
> [!NOTE]
> ClsAgent puede buscar en los archivos que se trasladan al recurso compartido de archivos desde el equipo local. Después de que ClsAgent mueve los archivos al recurso compartido de archivos, ClsAgent no realiza el mantenimiento de limpieza y eliminación de archivos. Es necesario definir una tarea administrativa para supervisar el tamaño de los archivos en el recurso compartido de archivos y eliminarlos o archivarlos. 
  
Los archivos de registro resultantes se pueden leer y analizar con distintas herramientas, incluyendo **Snooper.exe** y cualquier herramienta que pueda leer un archivo de texto, como **Notepad.exe**. Snooper.exe forma parte de la Skype para las herramientas de depuración de Business Server 2015 y está disponible como una [descarga de Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
Al igual que OCSLogger, el servicio de registro centralizado tiene varios componentes para realizar un seguimiento contra y proporciona opciones para seleccionar los indicadores, por ejemplo, TF_COMPONENT y TF_DIAG. Servicio de registro centralizado también conserva las opciones de nivel de registro de OCSLogger.
  
La ventaja más importante al uso el Skype para el Shell de administración de servidor empresarial a través de la línea de comandos ClsController es que puede configurar y definir nuevos escenarios de uso de proveedores seleccionados que el espacio de problema, indicadores personalizados y niveles de registro de destino. Los escenarios disponibles para ClsController se limitan a los que están definidos para el archivo ejecutable.
  
En versiones anteriores, OCSLogger.exe se proporcionaba para que los administradores y el personal de soporte pudieran recopilar archivos de seguimiento de los equipos de la implementación. A pesar de sus ventajas, OCSLogger tenía una limitación. Solo se podían recopilar los registros de un equipo al mismo tiempo. Podía realizar el registro de varios equipos usando copias diferentes de OCSLogger, pero al final obtenía varios registros y ninguna manera sencilla de agregar los resultados.
  
Cuando un usuario solicita una búsqueda de registros, ClsController determina a qué máquinas se enviará la solicitud (en función de los escenarios seleccionados). También determina si es necesario enviar la búsqueda al recurso compartido de archivos donde se encuentran los archivos .etl guardados. Cuando los resultados de búsqueda se devuelven a ClsController, el controlador combina los resultados en un único conjunto de resultados ordenados por tiempo, que se presenta al usuario. Los usuarios pueden guardar los resultados de búsqueda en la máquina local para su posterior análisis.
  
Cuando inicia una sesión de registro, especifica los escenarios relativos al problema que está intentando resolver. Puede tener dos escenarios en ejecución al mismo tiempo. Uno de los dos tiene que ser el escenario AlwaysOn. Como su nombre indica, siempre necesita estar en ejecución en la implementación, recopilando información sobre todos los equipos, grupos y componentes.
  
> [!IMPORTANT]
> De forma predeterminada, el escenario AlwaysOn no se ejecuta en la implementación. Es preciso iniciarlo explícitamente. Una vez iniciado, continuará ejecutándose hasta que se detenga explícitamente, y el estado en ejecución persistirá aunque se reinicien los equipos. Para obtener información detallada sobre cómo iniciar y detener escenarios, vea [iniciar o detener la captura de registro CLS en Skype para Business Server 2015](start-or-stop-log-capture.md). 
  
Cuando se produce un problema, inicie un segundo escenario relacionado con el problema notificado. Reproduzca el problema y detenga el registro del segundo escenario. Empiece las búsquedas de registros relativas al problema notificado. La colección agregada de registros produce un archivo de registro que contiene mensajes de seguimiento de todos los equipos del ámbito de sitio o global de la implementación. Si la búsqueda devuelve más datos de los que es razonable analizar (lo que normalmente se conoce como relación señal-ruido, en la que el ruido es demasiado alto), ejecute otra búsqueda con parámetros más limitados. En este punto, puede empezar a observar que aparecen patrones que le ayudarán a centrarse mejor en el problema. Por último, después de realizar un par de búsquedas más refinadas, podrá encontrar los datos relativos al problema y averiguar la causa principal.
  
> [!TIP]
> Si dispone de un escenario del problema en Skype para Business Server, empiece por preguntando "¿qué ya saber sobre el problema?" Si cuantificar los límites del problema, puede eliminar una gran parte de las entidades operativas de Skype para Business Server. 
  
Considere un escenario de ejemplo en el que sabe que los usuarios no están obteniendo resultados actualizados cuando buscan un contacto. No hay ningún punto en busca de problemas en los componentes de medios, Enterprise Voice, conferencias y un número de otros componentes. Lo que quizás no sepa es dónde está realmente el problema: ¿en el cliente o es un problema del lado del servidor? Los contactos se recopila el Replicador de usuarios de Active Directory y entrega al cliente mediante el servidor de la libreta de direcciones (ABServer). El ABServer obtiene sus actualizaciones desde la base de datos RTC (donde del replicador de usuarios ha escrito) y recopila en archivos de la libreta de direcciones, de forma predeterminada, 1:30 AM. El Skype para los clientes de Business Server recupere la nueva libreta de direcciones en una programación aleatoria. Dado que sabe cómo funciona el proceso, puede reducir la búsqueda de la causa posible a un problema relacionado con los datos recopilados de Active Directory por el Replicador de usuarios, la ABServer no recuperar y crear los archivos de la libreta de direcciones o los clientes no descarga del archivo de la libreta de direcciones.
  
## <a name="current-configuration"></a>Configuración actual

El servicio de registro centralizado está configurado para definir qué es el servicio de registro pensado para recopilar, cómo recopila, desde donde se recopilará y ¿cuáles son las opciones de registro. Define estas configuraciones de modo global (es decir, para toda la implementación) o para un sitio (es decir, para un sitio específico de la implementación). Cualquier registro que defina utilizará la configuración apropiada de la identidad que utiliza para iniciar, detener, vaciar y buscar registros.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Para mostrar la configuración actual del servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en un símbolo de la línea de comandos:
    
   ```
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Puede restringir o ampliar el ámbito de las opciones de configuración que se devuelven mediante la definición de `-Identity` y un ámbito, como "Site: Redmond" para devolver únicamente la CsClsConfiguration para el sitio de Redmond. Si desea obtener información detallada acerca de una determinada parte de la configuración, puede canalizar el resultado a otro cmdlet de Windows PowerShell. Por ejemplo, para obtener detalles acerca de los escenarios definidos en la configuración de sitio "Redmond", escriba:`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Salida de ejemplo de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    El resultado del cmdlet muestra la configuración actual del servicio de registro centralizado.
    
|**Opciones de configuración**|**Descripción**|
|:-----|:-----|
|**Identity** <br/> |Identifica el ámbito y el nombre de esta configuración. Hay solamente una configuración global y una configuración por sitio.  <br/> |
|**Scenarios** <br/> |Listado de todos los escenarios que se definen para esta configuración.  <br/> |
|**SearchTerms** <br/> |Términos de búsqueda definidas para la configuración. Office 365, no las implementaciones locales.  <br/> |
|**SecurityGroups** <br/> |Grupos de seguridad definidos que controlan quiénes (es decir, qué miembros de los grupos de seguridad) pueden ver equipos basados en el sitio en el que se encuentran. Sitio, en este contexto, es el sitio tal como se define en el generador de topología.  <br/> |
|**Regions** <br/> |Las regiones definidas se utilizan para recopilar SecurityGroups en una región, por ejemplo EMEA.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |El parámetro indica el tamaño máximo del archivo de registro antes de que se cree un archivo de registro de seguimiento de eventos (.etl). Un nuevo archivo de registro se crea cuando se alcanza el tamaño definido, incluso si aún no se ha alcanzado el tiempo máximo establecido en EtlFileRolloverMinutes.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Cantidad máxima definida de tiempo, en minutos, que puede durar un registro antes de que se cree un nuevo archivo .etl. Un nuevo archivo de registro se crea cuando expira el tiempo definido incluso si aún no se ha alcanzado el tamaño máximo establecido en EtlFileRolloverSizeMB.  <br/> |
|**TmfFileSearchPath** <br/> |Ubicación en la que se buscarán archivos con formato de mensaje de seguimiento.  <br/> |
|**CacheFileLocalFolders** <br/> |Ruta de acceso definida de la ubicación en la que se escriben los archivos caché en los equipos. CLSAgent escribe los archivos caché y se ejecuta en el contexto del servicio de red. En este caso, %TEMP% se expande a %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. De manera predeterminada, los archivos caché y los archivos de registro se escriben en el mismo directorio.  <br/> |
|**CacheFileNetworkFolder** <br/> |Puede definir una ruta de acceso de convención de nomenclatura universal (UNC) para recibir los archivos caché durante las operaciones de registro.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Definido como el tiempo máximo, en días, que se pueden retener los archivos caché.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Definido como el porcentaje de espacio en disco que pueden utilizar los archivos caché.  <br/> |
|**ComponentThrottleLimit** <br/> |Definido como la cantidad máxima de seguimientos por segundo que puede producir un componente antes de que se active el limitador de aceleración automático.  <br/> |
|**ComponentThrottleSample** <br/> |Cantidad de veces en 60 segundos que puede excederse el ComponentThrottleLimit.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |La versión mínima del CLSAgent que se permite ejecutar. Este elemento está pensado para Office 365.  <br/> |
   

