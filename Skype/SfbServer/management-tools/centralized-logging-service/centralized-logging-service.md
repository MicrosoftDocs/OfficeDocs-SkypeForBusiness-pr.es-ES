---
title: Servicio de registro centralizado en Skype empresarial 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumen: Obtenga información sobre los componentes de servicio y las opciones de configuración del servicio de registro centralizado en Skype empresarial Server 2015.'
ms.openlocfilehash: e65ea3a0a5ed4d86591b630df6d84e436a7efd66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221894"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Servicio de registro centralizado en Skype empresarial 2015
 
**Resumen:** Obtenga información sobre los componentes de servicio y las opciones de configuración del servicio de registro centralizado en Skype empresarial Server 2015.
  
El servicio de registro centralizado puede: 
  
- Iniciar o detener el registro en uno o más equipos y grupos de servidores con un solo comando desde una ubicación central.
    
- Buscar registros en uno o más equipos y grupos de servidores. Puede personalizar la búsqueda para que devuelva todos los registros de todos los equipos o devolver resultados más concisos.
    
- Configurar las sesiones de registro de la siguiente manera:
    
  - Defina un **Escenario** o use un escenario predeterminado. Un escenario en el servicio de registro centralizado se compone de ámbito (global o sitio), un nombre de escenario para identificar el propósito del escenario y uno o más proveedores. Puede ejecutar el escenario predeterminado y un escenario definido en cualquier momento dado en un equipo.
    
  - Use un proveedor existente o cree un nuevo proveedor. Aprovider define lo que recopila la sesión de registro, el nivel de detalle, los componentes que se van a trazar y las marcas que se aplican.
    
    > [!TIP]
    >  Si está familiarizado con OCSLogger, termproviders hace referencia a la colección de **componentes** (por ejemplo, S4, SIPStack), un **tipo de registro** (por ejemplo, WPP, EventLog o IIS logfile), un **nivel de seguimiento** (por ejemplo, All, verbose, Debug) e **indicadores** (por ejemplo, TF_COMPONENT, TF_DIAG). Estos elementos se definen en el proveedor (una variable de Windows PowerShell) y se pasan al comando del servicio de registro centralizado.
  
  - Configure los registros para determinados equipos y grupos.
    
  - Definir el ámbito de la sesión de registro desde el **sitio** de opciones (para ejecutar capturas de registro en equipos de ese sitio únicamente) o **global** (para ejecutar capturas de registro en todos los equipos de la implementación).
    
El servicio de registro centralizado es una eficaz herramienta de solución de problemas para problemas grandes o pequeños, desde el análisis de causa raíz hasta problemas de rendimiento. Todos los ejemplos se muestran con el shell de administración de Skype empresarial Server. Se proporciona ayuda para la herramienta de línea de comandos a través de la propia herramienta, pero hay un conjunto limitado de funciones que se pueden ejecutar desde la línea de comandos. Con el shell de administración de Skype empresarial Server, tiene acceso a un conjunto de características mucho más amplio y mucho más configurable, por lo que siempre debe ser la primera opción. 
  
## <a name="logging-service-components"></a>Componentes del servicio de registro

 El servicio de registro centralizado se ejecuta en todos los servidores de la implementación y está formado por los siguientes agentes y servicios:
  
- El agente del servicio de registro centralizado ClsAgent se ejecuta en todos los equipos con Skype empresarial Server implementado. Escucha (en los puertos **TCP 50001-50003**) los comandos de ClsController a través de WCF y envía respuestas de vuelta al controlador. Administra las sesiones de registro (iniciar/detener/actualizar) y busca registros. También realiza operaciones de mantenimiento como archivado y depuración de registros. 
    
- Cmdlets de la controladora del servicio de registro centralizado el shell de administración de Skype empresarial Server envía los comandos iniciar, detener, vaciar y buscar a ClsAgent. Cuando se envían los comandos de búsqueda, los registros resultantes se devuelven a ClsControllerLib. dll y se agregan. El controlador envía comandos al agente, recibe el estado de dichos comandos y administra los datos del archivo de registro de búsqueda tal y como se devuelven desde todos los agentes de cualquier equipo en el ámbito de búsqueda y agrega los datos de registro en un conjunto de resultados significativo y ordenado. La información de los temas siguientes se centra en el uso del shell de administración de Skype empresarial Server.
    
**ClsController Communications a ClsAgent**

![Relación entre CLSController y CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Puede emitir comandos mediante la interfaz de línea de comandos de Windows Server o mediante el shell de administración de Skype empresarial Server. Los comandos se ejecutan en el equipo en el que ha iniciado sesión y se envían a ClsAgent localmente o en los otros equipos y grupos de la implementación.
  
ClsAgent mantiene un archivo de índice de ALL. Archivos de caché que tiene en el equipo local. ClsAgent los asigna para que se distribuyan uniformemente entre los volúmenes definidos por la opción CacheFileLocalFolders, y nunca consumen más del 80% de cada volumen (es decir, la ubicación de la memoria caché local y el porcentaje se pueden configurar mediante el cmdlet **set-CsClsConfiguration** ). ClsAgent también es responsable de la caducidad de los archivos de registro de seguimiento de eventos (. ETL) almacenados en caché antiguos del equipo local. Después de dos semanas (es decir, el período de tiempo se puede configurar mediante el cmdlet **set-CsClsConfiguration** ) estos archivos se copian en un recurso compartido de archivos y se eliminan del equipo local. Para obtener más información, consulte [set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Cuando se recibe una solicitud de búsqueda, los criterios de búsqueda se usan para seleccionar el conjunto de archivos. ETL en caché para realizar la búsqueda en función de los valores del índice mantenido por el agente.
  
> [!NOTE]
> Los archivos que se mueven al recurso compartido de archivos desde el equipo local pueden ser buscados por ClsAgent. Una vez que ClsAgent mueve los archivos al recurso compartido de archivos, ClsAgent no mantiene la caducidad y la eliminación de los archivos. Debe definir una tarea administrativa para supervisar el tamaño de los archivos en el recurso compartido de archivos y eliminarlos o archivarlos. 
  
Los archivos de registro resultantes se pueden leer y analizar con una amplia variedad de herramientas, entre las que se incluyen **Snooper. exe** y cualquier otra herramienta que pueda leer un archivo de texto, como **Notepad. exe**. Snooper. exe forma parte de las herramientas de depuración de Skype empresarial Server 2015 y está disponible como [descarga de web](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
Al igual que OCSLogger, el servicio de registro centralizado tiene varios componentes de los que se realiza el seguimiento y proporciona opciones para seleccionar marcas, como TF_COMPONENT y TF_DIAG. El servicio de registro centralizado también conserva las opciones de nivel de registro de OCSLogger.
  
La ventaja más importante para usar el shell de administración de Skype empresarial Server a través de la línea de comandos ClsController es que puede configurar y definir nuevos escenarios con los proveedores seleccionados que tienen como objetivo el espacio de problemas, los indicadores personalizados y los niveles de registro. Los escenarios disponibles para ClsController se limitan a los que se definen para el archivo ejecutable.
  
En versiones anteriores, se proporcionaba OCSLogger. exe para permitir que los administradores y el personal de soporte técnico recopilaran archivos de seguimiento de los equipos de la implementación. OCSLogger, para todos sus puntos fuertes ha tenido una deficiencia. Solo se podían recopilar registros en un equipo en un momento dado. Puede iniciar sesión en varios equipos con copias independientes de OCSLogger, pero ha terminado con varios registros y no tiene una forma sencilla de agregar los resultados.
  
Cuando un usuario solicita una búsqueda de registros, el ClsController determina a qué máquinas se debe enviar la solicitud (es decir, en función de los escenarios seleccionados). También determina si es necesario enviar la búsqueda al recurso compartido de archivos donde se encuentran los archivos. ETL guardados. Cuando los resultados de la búsqueda se devuelven a ClsController, el controlador combina los resultados en un único conjunto de resultados ordenado por tiempo que se presenta al usuario. Los usuarios pueden guardar los resultados de la búsqueda en su equipo local para analizarlos más detalladamente.
  
Cuando se inicia una sesión de registro, se especifican escenarios relacionados con el problema que se intenta resolver. Puede tener dos escenarios en ejecución en cualquier momento. Uno de estos dos escenarios debe ser el escenario AlwaysOn. Como su nombre implica, siempre debe estar en ejecución en la implementación, recopilando información en todos los equipos, grupos de servidores y componentes.
  
> [!IMPORTANT]
> De forma predeterminada, el escenario AlwaysOn no se está ejecutando en su implementación. Debe iniciar explícitamente el escenario. Una vez iniciado, continuará ejecutándose hasta que se detenga explícitamente y el estado en ejecución persistirá a lo largo de los reinicios de los equipos. Para obtener más información sobre cómo iniciar y detener escenarios, consulte [Start or STOP CLS log Capture in Skype for Business Server 2015](start-or-stop-log-capture.md). 
  
Cuando se produzca un problema, inicie un segundo escenario relacionado con el problema notificado. Reproduzca el problema y detenga el registro para el segundo escenario. Comience las búsquedas de registros relativas al problema del que se informa. La colección agregada de registros genera un archivo de registro que contiene mensajes de seguimiento de todos los equipos de su sitio o ámbito global de la implementación. Si la búsqueda devuelve más datos de los que puede analizar de manera factible (lo que se conoce normalmente como una relación señal-ruido, en la que el ruido es demasiado alto), se ejecuta otra búsqueda con parámetros más estrechos. En este momento, puede empezar a ver patrones que se muestran y puede ayudarle a tener un enfoque más claro sobre el problema. Por último, después de realizar un par de búsquedas refinadas, puede encontrar datos relevantes para el problema y averiguar la causa raíz.
  
> [!TIP]
> Cuando aparezca un escenario con problemas en Skype empresarial Server, empiece a preguntarse "¿Qué es lo que ya sé sobre el problema?". Si cuantifica los límites del problema, puede eliminar una gran parte de las entidades operativas de Skype empresarial Server. 
  
Considere un escenario de ejemplo en el que sabe que los usuarios no obtienen los resultados actuales al buscar un contacto. No tiene sentido buscar problemas en los componentes multimedia, la telefonía IP empresarial, la Conferencia y varios otros componentes. Lo que quizás no sepa es dónde se encuentra realmente el problema: ¿en el cliente o es un problema del servidor? El replicador de usuarios recopila los contactos de Active Directory y los entrega al cliente mediante el servidor de libreta de direcciones (ABserver). El abcargador obtiene sus actualizaciones de la base de datos RTC (donde el replicador de usuarios las escribió) y las recopila en archivos de la libreta de direcciones, de manera predeterminada-1:30 A.M. Los clientes de Skype empresarial Server recuperan la nueva libreta de direcciones con una programación aleatoria. Como sabe cómo funciona el proceso, puede reducir la búsqueda por la posible causa de un problema relacionado con los datos recopilados desde Active Directory por el replicador de usuarios, que el encargador no recupere y cree los archivos de la libreta de direcciones o que los clientes no descarguen el archivo de la libreta de direcciones.
  
## <a name="current-configuration"></a>Configuración actual

El servicio de registro centralizado está configurado para definir lo que debe recopilar el servicio de registro, cómo lo recopila, dónde se recopilará y cuál será la configuración del registro. Estas opciones se definen de forma global (es decir, para toda la implementación) o para un sitio (es decir, un sitio con nombre de la implementación). Cualquier registro que defina utilizará las configuraciones apropiadas para la identidad que utiliza para iniciar, detener, vaciar y buscar registros.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Para mostrar la configuración actual del servicio de registro centralizado

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.
    
2. Escriba lo siguiente en un símbolo del sistema:
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Puede restringir o ampliar el ámbito de las opciones de configuración que se devuelven al definir `-Identity` y un ámbito, como "site: Redmond" para devolver solo el CsClsConfiguration para el sitio Redmond. Si desea obtener información detallada sobre una parte determinada de la configuración, puede canalizar la salida a otro cmdlet de Windows PowerShell. Por ejemplo, para obtener detalles sobre los escenarios definidos en la configuración del sitio "Redmond", escriba:`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Resultado de ejemplo de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    El resultado del cmdlet muestra la configuración actual del servicio de registro centralizado.
    
|**Opción de configuración**|**Descripción**|
|:-----|:-----|
|**Identidad** <br/> |Identifica el ámbito y el nombre de esta configuración. Hay solamente una configuración global y una configuración por sitio.  <br/> |
|**Scenarios** <br/> |Listado de todos los escenarios que se definen para esta configuración.  <br/> |
|**SearchTerms** <br/> |Términos de búsqueda definidos para la configuración. Microsoft 365 o Office 365, no en implementaciones locales.  <br/> |
|**SecurityGroups** <br/> |Grupos de seguridad definidos que controlan quiénes (es decir, miembros de los grupos de seguridad) pueden ver equipos basados en el sitio en el que se encuentran. Sitio, en este contexto, es el sitio tal como se define en Topology Builder.  <br/> |
|**Regiones** <br/> |Las regiones definidas se utilizan para reunir SecurityGroups en una región, por ejemplo EMEA.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |El parámetro indica el tamaño máximo del archivo de registro antes de que se cree un nuevo archivo de registro de seguimiento de eventos (.etl). Un nuevo archivo de registro se crea cuando se alcanza el tamaño definido incluso si aún no se ha alcanzado el tiempo máximo establecido en EtlFileRolloverMinutes.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Cantidad máxima definida de tiempo, en minutos, que puede durar un registro antes de que se cree un nuevo archivo .etl. Un nuevo archivo de registro se crea cuando expira el tiempo definido incluso si aún no se ha alcanzado el tamaño máximo establecido en EtlFileRolloverSizeMB.  <br/> |
|**TmfFileSearchPath** <br/> |Ubicación en la que se buscará archivos con formato de mensaje de seguimiento.  <br/> |
|**CacheFileLocalFolders** <br/> |Ruta definida de la ubicación en la que se escriben los archivos de caché en los equipos. CLSAgent escribe los archivos de caché y se ejecuta en el contexto del servicio de red. En este caso, %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. De manera predeterminada, los archivos de caché y los archivos de registro se escriben en el mismo directorio.  <br/> |
|**CacheFileNetworkFolder** <br/> |Puede definir una ruta de acceso UNC (convención de nomenclatura universal) para recibir los archivos de caché durante las operaciones de registro.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Definido como el tiempo máximo, en días, que se pueden retener los archivos de caché.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Definido como el porcentaje de espacio en disco que pueden utilizar los archivos de caché.  <br/> |
|**Puede componentthrottlelimit** <br/> |Definido como la cantidad máxima de seguimientos por segundo que puede producir un componente antes de que se active el limitador de aceleración automático.  <br/> |
|**ComponentThrottleSample** <br/> |Cantidad de veces en 60 segundos que puede excederse el ComponentThrottleLimit.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |La versión mínima del CLSAgent que se permite ejecutar. Este elemento está destinado a Microsoft 365 u Office 365.  <br/> |
   

