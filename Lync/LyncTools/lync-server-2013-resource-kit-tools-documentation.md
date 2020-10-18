---
title: Documentación de las herramientas del kit de recursos de Lync Server 2013
description: Documentación de las herramientas del kit de recursos de Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6866e04615014daa7e93f7e7f1081b10325d087d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573566"
---
# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Documentación de las herramientas del kit de recursos de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-09_

En este tema se describen las herramientas que forman parte del kit de recursos de Lync Server 2013, incluido el propósito de cada herramienta y ejemplos de su uso. Las herramientas del kit de recursos de Lync Server 2013, que ayudan a facilitar las tareas rutinarias a los administradores de ti que implementan y administran Lync Server 2013. Por ejemplo, la herramienta de **datos Web conf** puede usarse para controlar fácilmente los datos cargados por los usuarios durante una reunión en línea. La herramienta **SEFAUtil** se puede usar para configurar el desvío de llamadas de delegado y responder para los usuarios. Recomendamos a los administradores de ti que usen estas herramientas para administrar de forma más eficaz Lync Server 2013.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Instalación de las herramientas del kit de recursos

Para instalar las herramientas del kit de recursos de Lync Server 2013, descargue **OCSReskit.msi**. Puede descargar el instalador de las herramientas del kit de recursos desde el centro de descarga en [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429) .

Ejecute **OCSResKit.msi** para realizar una instalación sencilla. El archivo. msi instala todas las herramientas en la siguiente ruta de acceso: **% Program Files% \\ Microsoft Lync Server 2013 \\ reskit**. Las herramientas que son ejecutables independientes se encuentran en esta carpeta. Las herramientas que también tienen archivos se encuentran en sus propias subcarpetas.

</div>

<div>

## <a name="supported-environments"></a>Entornos compatibles

Para obtener un rendimiento óptimo, debe instalar las herramientas del kit de recursos de Lync Server 2013 en el mismo entorno y con las mismas especificaciones necesarias para Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Introducción a las herramientas del kit de recursos

En la siguiente lista se describen las herramientas que se proporcionan en el kit de recursos de Lync Server 2013. En la siguiente sección se describe una descripción de cada herramienta, incluidos los requisitos y el uso de ejemplo.

  - ABSConfig

  - Monitor del servicio de directiva de ancho de banda

  - Analizador de uso de ancho de banda

  - Llamar a Parkometer

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - Visor de configuración de red

  - Response Group Agent Live

  - SEFAUtil

  - SYSPrep.ps1

  - Número de anuncios no asignados a la migración

  - Datos de conf de Web

</div>

<div>

## <a name="absconfig"></a>ABSConfig

La herramienta de configuración del servicio de libreta de direcciones (ABSConfig) es una herramienta administrativa que ayuda a los administradores a personalizar la configuración del servicio de libreta de direcciones en Lync Server 2013. Esta herramienta también permite a los administradores de Lync Server 2013 restaurar la configuración predeterminada del servicio de libreta de direcciones.

<div>

## <a name="description"></a>Descripción

ABSConfig es una aplicación de interfaz de usuario gráfica que permite a los administradores configurar los atributos de servicios de dominio de Active Directory relacionados con el servicio de libreta de direcciones.

Los escenarios principales de la herramienta son los siguientes:

  - Permitir a los administradores asignar atributos en los servicios de dominio de Active Directory a los atributos para Lync Server 2013.

  - Permitir a los administradores especificar el atributo de servicios de dominio de Active Directory que se va a incluir o excluir en los archivos del servicio de libreta de direcciones.

  - Para permitir a los administradores restaurar la configuración predeterminada del servicio de libreta de direcciones.

La herramienta ABSConfig se puede iniciar mediante el archivo absConfig.exe. La herramienta se abre en la ficha **configurar atributos** . Esta tabla tiene opciones para asignar atributos de servicios de dominio de Active Directory a los campos de atributo de Lync Server 2013 y para especificar qué usuarios se deben incluir o excluir en los archivos del servicio de libreta de direcciones basándose en filtros de atributo específicos. También tiene opciones para personalizar el valor del número de teléfono que se incluirá en el archivo de la libreta de direcciones. La opción **Restaurar valores predeterminados** permite a los administradores restaurar la configuración del servicio de libreta de direcciones en los valores predeterminados.

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>Cambios de Lync Server 2010

En la herramienta de configuración del ABS de Lync Server 2013, es posible quitar atributos (filas) desactivando la casilla "habilitar" del atributo. Esto tiene el mismo efecto que eliminar la fila en Lync Server 2010.

<div>


> [!NOTE]  
> La casilla de verificación Habilitar está en la columna situada en el extremo derecho; es posible que deba desplazarse hacia la derecha para ver la columna



</div>

</div>

<div>

## <a name="output"></a>Output

ABSConfig almacena la configuración del servicio de libreta de direcciones en la base de datos.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>Finalidad

ABSConfig proporciona una forma rápida y sencilla de personalizar el servicio de libreta de direcciones de Lync Server 2013.

</div>

<div>

## <a name="requirements"></a>Requirements

<div>

## <a name="computer"></a>Equipo

ABSConfig solo puede ejecutarse desde un equipo unido a un dominio que tenga instalado Lync Server 2013. En el caso de Lync Server 2013, Enterprise Edition, esta herramienta se puede ejecutar en cualquier servidor front-end que tenga habilitado el servicio de libreta de direcciones durante la instalación.

</div>

<div>

## <a name="network"></a>Red

El equipo debe ser capaz de conectarse al grupo de servidores front-end y a la base de datos back-end.

</div>

<div>

## <a name="software"></a>Software

Los siguientes componentes de software deben instalarse antes de ejecutar la herramienta ABSConfig:

  - Microsoft Lync Server 2013

</div>

<div>

## <a name="users"></a>Usuarios

Administradores que tienen los permisos necesarios para actualizar la implementación de Lync Server 2013.

</div>

</div>

<div>

## <a name="examples"></a>Ejemplos

ABSConfig se puede iniciar escribiendo **ABSConfig.exe** en un símbolo del sistema. A continuación se muestra la interfaz de usuario de la herramienta ABSConfig.

![La herramienta de ABSConfig.exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "La herramienta de ABSConfig.exe.")

</div>

<div>

## <a name="summary"></a>Resumen

La herramienta ABSConfig proporciona a los administradores una herramienta rápida y fácil de usar para personalizar el servicio de libreta de direcciones de Lync Server 2013.

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>Monitor del servicio de directiva de ancho de banda

La herramienta de supervisión del servicio de directiva de ancho de banda está diseñada para permitir a los administradores ver una lista de las siguientes opciones:

1.  Todos los servicios de directiva de ancho de banda de Lync Server 2013 (autenticación y núcleo) configurados en la topología

2.  Las conexiones que realiza cada servicio a otros servicios de directiva de ancho de banda y a los servidores perimetrales.

3.  Todos los vínculos configurados en el documento de configuración de red y el uso de ancho de banda en tiempo real tal y como lo indica cada uno de los servicios de directiva de ancho de banda

<div>

## <a name="description"></a>Descripción

La herramienta de supervisión del servicio de directiva de ancho de banda se implementa como una aplicación basada en GUI. Los administradores inician la herramienta mediante la ejecución de PDPMonUI.exe.

Cuando se inicia la herramienta, intenta descubrir la lista de servicios de directivas de ancho de banda en la topología. Una vez realizada la actualización inicial, el panel de la izquierda de la ventana se rellena con una lista de servicios agrupados por los clústeres a los que pertenecen.

Cuando los administradores seleccionan un servicio de directiva de ancho de banda en particular, el panel de la derecha muestra la información sobre ese servicio en particular. Ese panel también tiene dos pestañas principales que muestran información.

<div>

## <a name="machine-info-tab"></a>Ficha información del equipo

La ficha **información del equipo** muestra los detalles del servicio de directiva de ancho de banda seleccionado y la lista y el estado de todas las conexiones realizadas por el servicio de directiva de ancho de banda seleccionado a otros servicios.

</div>

<div>

## <a name="topology-info-tab"></a>Pestaña información de topología

La ficha **información de topología** muestra una lista de todos los vínculos que se configuran en las opciones de configuración de red. Para cada vínculo, se muestra la capacidad de ancho de banda de audio y vídeo. Además, se muestra el ancho de banda utilizado actualmente, tanto en Kbps como en un porcentaje de la capacidad. La herramienta usa código de colores para resaltar los vínculos que tienen un uso similar al de la capacidad, lo que permite a los administradores aislar rápidamente estos vínculos.

<div>


> [!NOTE]  
> Si la herramienta de supervisión del servicio de directiva de ancho de banda experimenta errores cuando se conecta a cualquiera de los servicios de directiva de ancho de banda configurados, la información de las fichas información del <STRONG>equipo</STRONG> y información de la <STRONG>topología</STRONG> no se rellenará. Sin embargo, es posible que la herramienta se conecte inicialmente pero que pierda su conexión al servicio. En estos casos, los administradores pueden ver información obsoleta. Hay una marca de hora de <STRONG>última actualización</STRONG> en cada una de las pestañas que permite a los administradores ver cuándo se actualizó por última vez los datos de un servicio de directivas de ancho de banda determinado.



</div>

</div>

</div>

<div>

## <a name="output"></a>Output

No hay resultados en la línea de comandos; la salida del programa está contenida en la interfaz gráfica de usuario (GUI) principal.

</div>

<div>

## <a name="purpose"></a>Finalidad

La finalidad de la herramienta de supervisión del servicio de directiva de ancho de banda es permitir a los administradores ver el estado de cada uno de los servicios de directivas de ancho de banda que se definen en la topología. Además, los administradores pueden ver el uso de ancho de banda en tiempo real para todos los vínculos definidos en el documento de configuración de red.

</div>

<div>

## <a name="requirements"></a>Requirements

La herramienta de supervisión del servicio de directiva de ancho de banda debe ejecutarse en un equipo que forme parte de la topología de Lync Server.

</div>

<div>

## <a name="summary"></a>Resumen

La herramienta de supervisión del servicio de directiva de ancho de banda puede ser un recurso valioso para los administradores, de modo que puedan inspeccionar el estado de todos los servicios de directivas de ancho de banda de la topología y, lo que sea más importante, puedan obtener un uso de ancho de banda en tiempo real para los vínculos definidos en las opciones de configuración de red.

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>Analizador de uso de ancho de banda

El analizador de uso de ancho de banda es una herramienta que crea informes sobre diversas vistas de consumo de ancho de banda por los puntos de conexión de UC a través de vínculos WAN en la red empresarial. Estos informes se pueden usar para comprender el patrón de consumo de ancho de banda actual y para ayudar a planear la capacidad de ancho de banda.

<div>

## <a name="description"></a>Descripción

El analizador de uso de ancho de banda se implementa como una aplicación basada en la interfaz gráfica de usuario. Esta herramienta genera informes específicos para el uso de audio en la red y ayuda a planear la capacidad. También recorre en iteración la capacidad de ancho de banda asignada a varios vínculos.

</div>

<div>

## <a name="output"></a>Output

El analizador de uso de ancho de banda proporciona gráficos al al de la capacidad de ancho de banda y utilización de audio para todos los vínculos WAN configurados en el sistema.

</div>

<div>

## <a name="purpose"></a>Finalidad

En cualquier implementación de voz y vídeo, es fundamental supervisar y comprender la tendencia del uso de ancho de banda del tráfico multimedia en toda la red de la empresa. La herramienta analizador de uso de ancho de banda permite que un administrador logre exactamente eso. Esta herramienta hace lo siguiente:

  - Genera informes específicos para el uso de audio en la red

  - Ayuda a planear y iterar la capacidad con mayor eficacia en la capacidad de ancho de banda asignada a varios vínculos

El analizador de uso de ancho de banda puede generar trazados gráficos de la capacidad de ancho de banda e informes de utilización; son los siguientes:

  - Todos los vínculos WAN en la red empresarial

  - Filtrados por los vínculos WAN seleccionados que se han elegido

  - Filtrados por los vínculos WAN que han superado la capacidad de vínculo

  - Filtrados por los vínculos WAN que han estado bajo el uso del ancho de banda aprovisionado

  - Filtra por vínculos WAN que han alcanzado niveles críticos (un uso de ancho de banda superior al 90% de la capacidad de ancho de banda del vínculo WAN)

  - Filtrados por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregionales y vínculos dentro de un sitio

  - Filtrados por región de red

<div>

## <a name="applications"></a>Aplicaciones

El analizador de uso de ancho de banda tiene las dos aplicaciones siguientes (herramientas):

  - **WanLinkLogCollector.exe**     Esta herramienta permite al usuario especificar la información necesaria.

  - **BandwidthUtilizationAnalyzer.xlsm**    WanLinkLogCollector.exe inicia automáticamente un informe de software de hoja de cálculo de Microsoft Excel. Esta aplicación permite al usuario aplicar filtros al informe, tal como se muestra más adelante en este artículo.

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fases del uso del analizador de uso de ancho de banda

Hay dos fases al usar el analizador de uso de ancho de banda:

  - Recopilar registros, que se realiza mediante WanLinkLogCollector.exe

  - Personalización de informes, que se realiza con BandwidthUtilizationAnalyzer.xlsm

<div>


> [!IMPORTANT]  
> Se recomienda encarecidamente que BandwidthUtilizationAnalyzer.xlsm no sea iniciado manualmente por los usuarios finales.



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>Inicio del analizador de uso de ancho de banda

Inicie WanLinkLogCollector.exe en el símbolo del sistema o con el explorador de Windows.

**Uso de WanLinkLogCollector.exe**

Hay tres pasos para usar WanLinkLogCollector.exe:

1.  **Registrar la escala de tiempo**     Proporcionar la escala de tiempo que debe generarse el informe para

2.  **Especificar los directorios**     de archivos Proporcionar información de ubicación de archivos

3.  **Recopilar los registros e iniciar el visor**    de informes Ejecutar el comando para generar el informe

<div>

## <a name="step-1---log-the-timeline"></a>Paso 1: registrar la escala de tiempo

El registro de la escala de tiempo permite que el usuario de la herramienta especifique lo siguiente, tal como se muestra en la figura siguiente.

1.  **Fecha de inicio** Esta es la fecha de inicio de la escala de tiempo para la que se generará el informe; por ejemplo, 1 de agosto de 2010.

2.  **Fecha de finalización** Esta es la fecha de finalización de la escala de tiempo para la que se generará el informe; por ejemplo, 30 de septiembre de 2010.
    
    ![Fechas de inicio y finalización en el uso del ancho de banda](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Fechas de inicio y finalización en el uso del ancho de banda")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>Paso 2: especificar los directorios de archivos

El usuario puede especificar los siguientes directorios de archivos, tal y como se muestra.

  - **Ubicación de los archivos de registro del servidor** La ubicación de la carpeta donde se almacenan los registros del servidor de directivas de ancho de banda. Suele estar en \<fileserver\> \\ \<choice of FE\> \\ PDP de AppServerFiles \\ .

  - **Ubicación de almacenamiento de archivos temporales** Ubicación del archivo temporal donde se almacenan los archivos intermedios mientras se genera el informe.

![Directorios de archivos en el banda de uso de ancho de banda](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Directorios de archivos en el banda de uso de ancho de banda")

<div>


> [!NOTE]  
> Asegúrese de que el acceso a los registros del servidor y la carpeta de almacén de archivos temporales sea suficiente para el usuario de la herramienta.



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Paso 3: recopilar los registros e iniciar el visor de informes

Para recopilar los registros e iniciar el visor de informes, haga clic en **Ejecutar** como se muestra a continuación. Este paso recopila los datos necesarios.

![Recopilar datos en el banda de uso de ancho de banda](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Recopilar datos en el banda de uso de ancho de banda")

Cuando la validación de entrada es correcta, se muestra el mensaje que se muestra a continuación.

![Registros recopilados de la notificación en el uso de ancho de banda](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Registros recopilados de la notificación en el uso de ancho de banda")

Haga clic en **Aceptar**. BandwidthUtilizationAnalyzer.xlsm se inicia automáticamente. Siga las instrucciones del cuadro de mensaje. Para obtener información detallada, consulte **Using BandwidthUtilizationAnalyzer.xlsm** en la sección siguiente.

</div>

<div>


**Uso de BandwidthUtilizationAnalyzer.xlsm**

1.  Cuando se inicie BandwidthUtilizationAnalyzer.xlsm automáticamente, haga clic en **Actualizar** como se muestra a continuación.
    
    ![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")

2.  Cuando se abre una carpeta de archivos, seleccione consolidated.csv de la ubicación especificada en el cuadro de mensaje como se muestra a continuación. También se muestra la ubicación como **C: \\ temp**.
    
    ![Abrir una carpeta en BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Abrir una carpeta en BandwidthUtilizationAnalyzer.")

3.  Haga clic en **Importar**.

4.  El trazado gráfico se genera automáticamente. Está disponible cuando desaparece el puntero de trabajo en segundo plano.
    
    ![Aplicar filtros en la vista informe.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicar filtros en la vista informe.")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>Aplicación de filtros a la vista de informe

Los filtros que se pueden aplicar a la vista informes, tal como se muestra a continuación, se describen a continuación:

![Aplicar filtros en la vista informe.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicar filtros en la vista informe.")

1.  **Nombre** de Filtrar por vínculos WAN (el filtro está en el lado derecho del gráfico). El prefijo denota los siguientes tipos de vínculos; Vea el cuadro vertical (azul):
    
      - **Sitio S** Vínculo WAN de un sitio de red a una región de red
    
      - **Es entre sitios** El vínculo WAN entre dos sitios de red
    
      - **R inter-region** El vínculo WAN entre dos regiones de red

2.  **Límite superado** Filtra por vínculos WAN cuyo uso de ancho de banda es mayor que la capacidad de ancho de banda

3.  **Niveles críticos** Filtra por vínculos WAN cuyo uso de ancho de banda ha alcanzado el 90% o más de la capacidad de ancho de banda

4.  **Subutilizado** Filtra por vínculos WAN cuyo uso de ancho de banda ha sido inferior al 25% de la capacidad de ancho de banda

5.  **Tipo de vínculo** Filtrar por los siguientes tipos de vínculos WAN:
    
      - Tipo de **sitio de red**
    
      - Tipo **entre sitios**
    
      - Tipo **de vínculo entre regiones**

6.  **Región** Filtrar por región de red

Las figuras siguientes muestran los filtros descritos anteriormente.

Filtrar por **nombre**. Seleccione la lista de vínculos que deben mostrarse en el gráfico.

![Filtrado por nombre en BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtrado por nombre en BandwidthUtilizationAnalyzer.")

Filtrar por **límite superado**. Seleccione **true** para aplicar el filtro.

![Filtrado por límite superado.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtrado por límite superado.")

Filtrar por **niveles críticos**. Seleccione **true** para aplicar el filtro.

![Filtrado por niveles críticos.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtrado por niveles críticos.")

Filtrar por **en uso**. Seleccione **true** para aplicar el filtro.

![Filtrado por en uso.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtrado por en uso.")

Filtra por **tipo de vínculo**. Seleccione el tipo o tipos que deben mostrarse.

![Filtrado por tipo de vínculo.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtrado por tipo de vínculo.")

Filtrar por **región**. Seleccione una lista de regiones cuyos vínculos se deben mostrar.

![Filtrado por región.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtrado por región.")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>Requirements

  - .NET Framework 3,5

  - Microsoft Excel 2010 o Excel 2007

</div>

<div>

## <a name="summary"></a>Resumen

El analizador de uso de ancho de banda se usa para trazar el uso del ancho de banda de audio para tráfico de comunicaciones unificadas en la red. Esta herramienta se puede usar también para informar del uso de ancho de banda de vídeo en la red.

</div>

</div>

<div>

## <a name="call-parkometer"></a>Llamar a Parkometer

Call Parkometer es una aplicación de línea de comandos que proporciona acceso sencillo a la base de datos de órbitas de estacionamiento de llamadas.

<div>

## <a name="description"></a>Descripción

Call Parkometer es una herramienta para realizar un seguimiento de las llamadas estacionadas actualmente. También recopila estadísticas sobre las órbitas y el uso del servidor de estacionamiento de llamadas (CPS). Esta herramienta de línea de comandos proporciona acceso de lectura y escritura a la base de datos de SQL Server de CPS de la órbita desde un equipo conectado local o remoto.

Todas las opciones se excluyen mutuamente. La sintaxis de la línea de comandos es la siguiente:

  - parámetro **– o** : enumera todos los intervalos de órbita configurados para este grupo de servidores.

  - parámetro **– n** : enumera todas las órbitas usadas actualmente en este grupo. La información mostrada es la siguiente:
    
      - Identificador uniforme de recursos (URI) de SIP del parque y Estacionador.
    
      - Nombre de host de la CPS donde se estaciona la llamada.
    
      - Marca de tiempo del momento en el que se estaciona la llamada.

  - **– f** parámetro: enumera el número de órbitas libres actualmente en el grupo.

  - **– r \<n\> ** parámetro: muestra las \<n\> últimas llamadas estacionadas. La información mostrada es la siguiente:
    
      - URI del SIP estacionado.
    
      - URI del SIP Estacionador.
    
      - Nombre de host de la CPS en la que se estaciona la llamada.
    
      - Marca de tiempo de Cuándo se recuperó o se quitó la llamada.

  - **-t \<n\> ** parámetro: comprueba la reserva de una órbita en la base de datos para mostrar la aleatoriedad de los números de órbitas asignados.

</div>

<div>

## <a name="output"></a>Output

En función de los parámetros de entrada que se especifiquen en un símbolo del sistema, Call Parkometer muestra el siguiente resultado:

  - Todos los intervalos de órbitas que están configurados para este grupo

  - Llamadas estacionadas actualmente

  - Número de órbitas libres (disponibles)

  - Llamadas estacionadas recientemente

  - Órbitas reservadas para probar valores de órbitas uniformes y aleatorios

</div>

<div>

## <a name="purpose"></a>Finalidad

La finalidad de la herramienta CPS es proporcionar acceso desde la línea de comandos a la base de datos de CPS. El administrador puede ver el uso de CPS y determinar el número de órbitas asignadas a un grupo de servidores.

</div>

<div>

## <a name="requirements"></a>Requirements

No hay requisitos si esta herramienta se ejecuta en el mismo equipo que ejecuta CPS. Si esta herramienta se ejecuta en un equipo remoto, la base de datos de SQL Server que usa Lync Server 2013 debe estar configurada para permitir el acceso remoto. Llamar a Parkometer debe configurarse con una cadena de conexión de base de datos de SQL Server para conectarse al servidor SQL Server del grupo. Esta cadena de conexión de base de datos de SQL Server se define en el archivo de configuración, **parkometer.exe.config**. Debe colocarse en el mismo directorio en el que se encuentra parkometer.exe. El siguiente archivo XML es un ejemplo de parkometer.exe.config. Los parámetros que deben configurarse son el nombre de usuario (por ejemplo, administrador de dominio \\ ), la contraseña (por ejemplo, contraseña) y el nombre de host (por ejemplo, mi servidor).

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
       <add key="SQL" value="server=myserver\RTC;
    database=cpsdyn;
    User Id=mydomain\Administrator;
    Password=mypassword.;
    Integrated Security=false;"/>
      </appSettings>
    </configuration>
```

</div>

<div>

## <a name="examples"></a>Ejemplos

Intervalos de órbita implementados: el parámetro – o muestra todos los intervalos de órbitas que están configurados para este grupo de servidores, tal y como se muestra.

![Intervalos de órbita en llamada Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Intervalos de órbita en llamada Parkometer.")

Llamadas estacionadas actualmente: el parámetro – n enumera todas las órbitas usadas actualmente en este grupo de servidores, tal como se muestra

![Llamadas estacionadas actualmente en Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Llamadas estacionadas actualmente en Call Parkometer.")

Número de órbitas libres: el parámetro – f enumera el número de órbitas libres actualmente en el grupo, tal como se muestra

![Órbitas libres en llamadas Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Órbitas libres en llamadas Parkometer.")

Llamadas estacionadas recientemente: el parámetro – r \<n\> enumera las \<n\> últimas llamadas estacionadas, como se muestra

![Llamadas estacionadas recientemente en Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Llamadas estacionadas recientemente en Call Parkometer.")

Prueba de reserva orbital: el parámetro – t comprueba la reserva \<n\> de una órbita en la base de datos tal como se muestra.

![Pruebe las reservas de órbitas en Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Pruebe las reservas de órbitas en Call Parkometer.")

</div>

<div>

## <a name="summary"></a>Resumen

Call Parkometer es una herramienta de línea de comandos que proporciona información detallada sobre el servidor de estacionamiento de llamadas.

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

La herramienta del kit de recursos de CleanupStorageServiceData permite eliminar datos huérfanos de la base de datos usada por el servicio de almacenamiento de Lync Server (LYSS). Una función del servicio de almacenamiento es almacenar en búfer la comunicación entre Lync Server y varios extremos de almacenamiento de datos back-end, como SQL Server y Exchange.

<div>

## <a name="description"></a>Descripción

Para admitir la alta disponibilidad, LYSS acepta y guarda copias de los datos en varios servidores front-end del grupo de servidores temporalmente y quita esos datos una vez que se han entregado a su ubicación de almacenamiento de largo plazo final. Hay situaciones inusuales que se pueden producir durante otro funcionamiento normal, cuando un servidor puede bloquear o experimentar un problema de procesamiento, y es posible que algunos datos no se limpien correctamente. Estos datos son inocuos, pero consumen recursos de procesamiento limitados. Gran parte del mantenimiento de datos normal es automatizado, pero esta herramienta permite la identificación segura y la eliminación de datos huérfanos cuando no es posible la eliminación automática. El uso de esta herramienta se indica cuando se genera una alerta de System Center Operations Manager (SCOM) de supervisión de estado que pide al administrador que quite los datos innecesarios de las bases de datos de LYSS locales del grupo. Habrá un evento correspondiente en el registro de eventos en el servidor front-end que activó la alerta. Los detalles del evento contendrán información sobre la cantidad de datos huérfanos contenidos en el front-end y se produce cuando dichos datos superen determinados umbrales previos a la determinación

</div>

<div>

## <a name="requirements"></a>Requirements

Instale las herramientas del kit de recursos de Lync Server 2013. La herramienta se ejecuta en equipos Unidos a un dominio en los que se han instalado Lync Server y Lync Server 2013 Management Shell. La herramienta usa un cmdlet desde el shell de administración para identificar todos los servidores front-end del grupo. En segundo lugar, la herramienta debe ejecutarse desde un equipo en el grupo de servidores que tenga instalada la base de datos **RtcLocal** . Esta base de datos se usa con la herramienta CleanupStorageServiceData para obtener los detalles de conexión necesarios para comunicarse con el servicio de enrutamiento de Lync Server. por último, la cuenta o credencial que invoca la herramienta debe tener permiso de lectura y escritura en el recurso compartido de archivos en el que desea escribir el registro de salida. Además, esta herramienta depende de que el grupo esté en un estado estable. En esencia, esto significa que cada servidor front-end debe estar activo y en funcionamiento, la instancia de SQL Server LYNCLOCAL y la base de datos LYSS deben poder conectarse a y cada grupo de enrutamiento debe tener un conjunto completo de 1 servidor front-end principal y 2 servidores front-end secundarios.

</div>

<div>

## <a name="examples"></a>Ejemplos

C: \\ archivos de programa \\ Microsoft Lync Server 2013 \\ reskit \\ StorageService \> ImportStorageServiceData.exe

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a>DBAnalyze

<div>

## <a name="description"></a>Descripción

DBAnalyze es una herramienta de línea de comandos que ayuda a los administradores a recopilar informes de análisis sobre las bases de datos de Lync Server 2013. DBAnalyze tiene los siguientes modos: diagnóstico, datos de usuario, Conferencia, MCU y fragmentación de disco:

  - **Modo**     de diagnóstico Crea un informe que incluye información sobre tablas (el número de registros, la fragmentación, el tamaño de los datos y el tamaño del índice), los tamaños de los archivos de registro y de datos. el último tiempo de copia de seguridad, la distribución de contactos entre servidores que ejecutan Microsoft Office Communications Server, el número promedio de permisos, contactos, contenedores, suscripciones, publicaciones, extremos por usuario, los usuarios alojados incorrectamente, los usuarios que no se pueden enrutar, el número medio de conferencias organizadas por usuario, conferencias programadas, conferencias activas y la versión
    
    <div>
    

    > [!NOTE]  
    > El modo de diagnóstico en ejecución puede afectar al rendimiento del servidor.

    
    </div>

  - Modo de datos de **usuario**   Informa sobre los datos del contacto, el contenedor, la suscripción, la publicación, el permiso y el grupo de contactos para un usuario específico o para los usuarios que tienen ese usuario en sus listas de contactos y permisos. Este modo también informa de los datos de Resumen de las conferencias a las que un usuario organiza o al que está invitado.

  - **Modo**     de conferencia Informa de datos detallados para una conferencia específica, incluidos todos los detalles de tiempo de programación de la Conferencia, la lista de invitados, la lista de tipos de medios permitidos para la Conferencia, las MCU activas (unidades de control multipunto), la lista de participantes activos y el estado de señalización de cada participante.

  - IDENTIFICADOR de reunión de **descodificación**    Descodifica un identificador de reunión de la red telefónica conmutada (RTC) que especifica el conmutador **/pstnid** pero no se conecta al back-end para obtener información detallada.

  - **Resolver Conferencia**     Descodifica un identificador de reunión RTC especificado por el modificador **/pstnid** y muestra información sobre la Conferencia indicada por el identificador.

  - **Modo MCU**    Informa del identificador, el tipo de medio, la dirección URL, el estado de latido, la carga de conferencia y la carga de participantes de cada MCU del grupo.

  - Modo de fragmentación de **disco**    Muestra el estado de fragmentación de todos los discos.

Esta herramienta se puede usar para diagnosticar varios problemas o ayudar a los administradores con la planeación de la capacidad. Por ejemplo, si la mayoría de los usuarios hospedados en el servidor A eligen a los usuarios hospedados en el servidor B como sus contactos, el administrador puede mover a los usuarios del servidor a al servidor B para reducir el tráfico entre servidores.

</div>

<div>

## <a name="output"></a>Output

Esta herramienta genera informes predefinidos sobre la base de datos de Lync Server 2013. **Ruta de acceso:** % ProgramFiles% \\ Microsoft Lync Server 2013 \\ reskit

</div>

<div>

## <a name="purpose"></a>Finalidad

Para instalar Dbanalyze.exe, cópielo en una carpeta local y, a continuación, ejecute la herramienta. Para usar la herramienta, ejecute el siguiente comando desde la línea de comandos.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` A continuación se muestran las descripciones de las opciones de la línea de comandos.

![Opciones de la línea de comandos para Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Opciones de la línea de comandos para Dbanalyze.exe.")

</div>

<div>

## <a name="requirements"></a>Requirements

**Equipo** DBAnalyze solo puede ejecutarse desde un equipo unido a un dominio que tenga instalado Lync Server 2013.

**Red** El equipo debe ser capaz de conectarse a la base de datos back-end.

**Software** de Los componentes de software de Lync Server 2013 deben estar instalados antes de ejecutar DBAnalyze.

**Usuarios** de En la tabla siguiente se muestran los administradores que tienen los permisos necesarios para acceder a las bases de datos de Lync Server 2013.

![Tabla de permisos para obtener Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tabla de permisos para obtener Dbanalyze.exe.")

<div>


> [!NOTE]  
> Se requiere una cuenta de administrador local para <STRONG>/Report:</STRONG> modo de disco.



</div>

</div>

<div>

## <a name="examples"></a>Ejemplos

Los siguientes son ejemplos de comandos de Dbanalyze.exe válidos:

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>Resumen

DBAnalyzer proporciona a los administradores un análisis rápido y sencillo de las bases de datos de Lync Server 2013.

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

La herramienta del kit de recursos de ImportStorageServiceData permite volver a importar datos de cola y de extremo que se han vaciado del servicio de almacenamiento (LYSS) de nuevo en el servicio de almacenamiento.

<div>

## <a name="description"></a>Descripción

Los datos vaciados del servicio de almacenamiento podrían haber sido automáticos (periódicos) según el estado de los elementos de la cola o la base de datos. Podría haber sucedido debido a la invocación manual del cmdlet de conmutación por error del grupo o al cmdlet StorageServiceFullFlush (que invoca el cmdlet de conmutación por error del grupo de servidores). Tenga en cuenta que los datos no deberían volver a importarse si el tamaño de la base de datos del servicio de almacenamiento (LYSS) de los servidores front-end es superior al nivel normal, ya que, por lo tanto, es probable que solo se exporten más datos hacia atrás. Además, los problemas que podrían haber contribuido a errores que provocaron el crecimiento de la cola del servicio de almacenamiento deberían resolverse en primer lugar (por ejemplo, errores de punto de conexión de Exchange, problemas de red u otros problemas).

**Escenario 1:** durante la conmutación por error del grupo, es posible que los archivos se vacíen del servicio de almacenamiento para cada front-end. Una vez completada la conmutación por error, debe ejecutarse la herramienta para volver a importar los datos.

**Escenario 2:** los datos se vacían automáticamente cada día o en respuesta a la base de datos del servicio de almacenamiento que supera determinados umbrales de tamaño (por ejemplo, 60%, 80%, 90% completo). El administrador debe volver a importar periódicamente los datos vaciados de forma automática. En la situación anterior, si no se implementa el paquete SCOM de supervisión, hay eventos para el servicio de almacenamiento de Lync Server relacionados con los datos que se vacían del servicio de almacenamiento. Se han iniciado los identificadores de evento de 32075 (operación de vaciado completa), 32076 (vaciado completo), 32082 (se inició el vaciado de nivel de mantenimiento), 32083 (vaciado de nivel de mantenimiento completo), 32089 (vaciado debido a rellenar la base de datos). Nota estos identificadores de evento corresponden a la versión RTM. Cuando un administrador ve estos eventos, significa que hay archivos que se han vaciado. Estos datos deben volver a importarse rutinariamente con esta herramienta, por ejemplo, una vez por semana.

Para la versión de servicio en línea, si se implementa el paquete SCOM de supervisión de mantenimiento de Lync Server, hay nuevas alertas que se pueden plantear y que piden al administrador que vuelva a importar los datos vaciados en el servicio de almacenamiento. Habrá un evento correspondiente en el registro de eventos del servidor front-end que activó la alerta. El evento proporcionará una descripción de la ruta de acceso principal en la que se ubican los archivos de datos vaciados, así como el número de archivos que cumplen los criterios de alerta. Los criterios de alerta son que hay X o más archivos en la ruta de acceso del elemento primario concreta que tienen al menos días Y de antigüedad (donde X e Y están preestablecidos en el StorageService, pero se pueden invalidar cambiando el archivo APPCONFIG). A continuación, se muestran dos ejemplos de eventos que pueden desencadenar la alerta de mantenimiento, con la diferencia de que la ruta de acceso principal. Una posibilidad está en el uso compartido de archivos del servicio Web, mientras que la otra posibilidad es el directorio de datos de la aplicación local de cada front-end. (por ejemplo, c: \\ ProgramData \\ Microsoft \\ Lync Server \\ StorageService). A continuación, el administrador ejecutará esta herramienta de reskit.

Esta herramienta aumentará la carga de la CPU y de e/s en el front-end en el que se ejecuta, así como otros front-end, en la situación en que los datos no son propiedad del servidor front-end en el que se ejecuta la herramienta. Se recomienda ejecutar esta herramienta cuando los servidores front-end no tienen una carga de CPU y de e/s intensa, por ejemplo, fuera de las horas pico. En segundo lugar, esta herramienta puede tener entre 2 y 3 minutos para importar un archivo de datos. Tenga esto en cuenta al estimar cuánto tiempo se ejecutará la herramienta. El archivo de registro detallado generado por la herramienta aparecerá de forma predeterminada en el almacén de archivos. Elimínelo si no se han notificado errores, ya que el archivo de registro puede tener decenas de MB o más.

![Ejemplo de eventos del registro de eventos del servidor de almacenamiento.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Ejemplo de eventos del registro de eventos del servidor de almacenamiento.")

</div>

<div>

## <a name="requirements"></a>Requirements

Instale las herramientas del kit de recursos de Lync Server 2013. La herramienta se ejecuta en equipos Unidos a un dominio donde se instalan Lync Server y Lync Server Management Shell. La herramienta usa un cmdlet desde el shell de administración para identificar todos los servidores front-end del grupo. En segundo lugar, la herramienta debe ejecutarse desde un equipo en el grupo de servidores que tenga instalada la base de datos **RtcLocal** . Esta base de datos la usa la herramienta para recuperar la ubicación del recurso compartido de archivos WebService para el grupo de servidores. Además, antes de usar la herramienta, cada servidor front-end debe habilitar la comunicación remota de Windows PowerShell con **enable-PSRemoting** en cada servidor front-end, así como el equipo desde el que se ejecuta la herramienta. De lo contrario, se producirá un error en los comandos remotos de Windows PowerShell de esta herramienta. La comunicación remota de Windows PowerShell puede desactivarse en todos los servidores front-end del grupo una vez finalizado. Por último, la cuenta o credencial que invoca la herramienta debe tener permiso de lectura y escritura en el recurso compartido de archivos WebService para el grupo en el que está ejecutando esta herramienta. De lo contrario, la herramienta producirá errores de permiso de e/s.

<div>


> [!NOTE]  
> En Windows Server 2012, la comunicación remota de Windows PowerShell está habilitada de forma predeterminada, pero no en el sistema operativo Windows Server 2008.



</div>

</div>

<div>

## <a name="examples"></a>Ejemplos

    >  C:\StorageService>ImportStorageServiceData.exe
    Description:
    This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
    Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
    Additional Options:
    -Verbose                    : Turn verbose output on.
    
    -StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                        
    -FileSharePath              : Import only all data from just under the UNC path specified.
    
    ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
    Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
    Using NetNamedPipeBinding...
    OnTopologyChanged Event received
    Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService
    
    Front Ends:
    server.vdomain.com
    server2.vdomain.com
    server1.vdomain.com
    server3.vdomain.com
    Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
    # Files found: 8
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    Items deserialized: 20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
    3832e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
    86684d3832e4__0.xml
    
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
    ain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
    287dd6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
    b46a42287dd6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
    d251e6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
    e08a15d251e6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
    17c220__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
    949ff817c220__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
    6d5317__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
    749be66d5317__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
    86b565__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
    657eda86b565__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
    All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
    vices-1\StorageService
    Importing files for: server.vdomain.com
    No files founds.
    Importing files for: server2.vdomain.com
    No files founds.
    Importing files for: server1.vdomain.com
    No files founds.
    Importing files for: server3.vdomain.com
    No files founds.
    Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
    Log20120910_1609SS
    Tool has finished execution.
    >  C:\StorageService>

</div>

</div>

<div>

## <a name="lcssync"></a>LCSSync

La herramienta LCSSync ayuda a implementar el software de comunicaciones de Lync Server 2013 en un entorno de varios bosques. Esta herramienta se usa para sincronizar usuarios y grupos de bosques de usuarios diferentes como un objeto de contacto de servicios de dominio de Active Directory para un bosque central en el que Lync Server 2013 está instalado.

<div>

## <a name="description"></a>Descripción

LCSSync usa los objetos de contacto de los servicios de dominio de Active Directory sincronizados en el bosque central para habilitar a los usuarios para Lync Server. Para proporcionar un inicio de sesión único, la cuenta de usuario principal debe estar asignada al objeto de contacto de servicios de dominio de Active Directory en el bosque central de Lync Server 2013. Esta herramienta ayuda a realizar esa asignación. Esta herramienta proporciona plantillas para crear agentes de administración en Microsoft Identity Integration Server.

</div>

<div>

## <a name="summary"></a>Resumen

La herramienta LCSSync ayuda a implementar Lync Server en un entorno de varios bosques.

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

La herramienta LookupUserConsole muestra información de enrutamiento de Lync Server interno sobre usuarios específicos. Esta información puede ser útil para que Microsoft admita personal en el diagnóstico de problemas de implementación y enrutamiento.

<div>

## <a name="description"></a>Descripción

Al ejecutar LookupUserConsole.exe se abrirá un símbolo del sistema que acepta direcciones SIP e intenta Mostrar información de enrutamiento de Lync Server interna relacionada. Escriba **Exit** para salir de la herramienta LookupUserConsole.

</div>

<div>

## <a name="requirements"></a>Requirements

Instale las herramientas del kit de recursos de Lync Server 2013. La herramienta se ejecuta en equipos Unidos a un dominio donde Lync Server está instalado

</div>

<div>

## <a name="examples"></a>Ejemplos

C: \\ archivos de programa \\ Microsoft Lync Server 2013 \\ reskit \>LookupUserConsole.exe

    > sip:john.doe@vdomain.com
    
      Execution time (ms):                            171.094
      Exeuction result:                               Success
      SIP URI:                                        sip:john.doe@vdomain.com
      User info:
        SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
        Grouping ID:                                  00000000-0000-0000-0000-...
        Line URI:                                     <null>
        Policy assignment:                            TenantId={00000000--0000-000....
        SIP enabled:                                  True
        UC enabled:                                   False
        Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
        Active cluster:                               pool0.vdomain.com
        Backup registrar cluster:                     <null>
        Deployment location:                          <null>
        Home Front-End FQDN:                          SERVER.vdomain.com
        Primary Registrar cluster:                    pool0.vdomain.com
        Remote Director external SIP FQDN:            <null>
        Remote Director internal SIP FQDN:            <null>
        Remote Director Web FQDN:                     <null>
        Routing group ID:                             4501e04e-ae48-5605-9346...
        Service tag ID:                               1266953005
        User Front-End resolved:                      True
        User in local forest:                         True
        User in remote forest:                        False
        User in split domain:                         False
        User-Services cluster:                        pool0.vdomain.com
    
    > sip:nouser@vdomain.com
    
      Execution time (ms):                            948.7574
      Exeuction result:                               UserDoesNotExist
    
    > exit

</div>

</div>

<div>

## <a name="msturnping"></a>MsTurnPing

La herramienta MSTurnPing permite a un administrador del software de comunicaciones Microsoft Lync Server 2013 comprobar el estado de los servidores que ejecutan el servidor perimetral de audio y vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan los servicios de directivas de ancho de banda en la topología.

<div>

## <a name="description"></a>Descripción

La herramienta MSTurnPing permite a un administrador del software de comunicaciones Lync Server 2013 comprobar el estado de los servidores que ejecutan el servidor perimetral de audio y vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan los servicios de directivas de ancho de banda en la topología.

La herramienta permite al administrador realizar las siguientes pruebas:

1.  Prueba del servidor perimetral a/V: la herramienta realiza pruebas en todos los servidores perimetrales A/V de la topología mediante el siguiente procedimiento:
    
      - Comprobando que el servicio de autenticación de audio y vídeo de Lync Server se ha iniciado y que puede emitir las credenciales correctas.
    
      - Comprobando que el servicio perimetral de audio y vídeo de Lync Server se ha iniciado y que puede asignar correctamente los recursos en el servidor perimetral externo.

2.  Prueba del servicio de directiva de ancho de banda: la herramienta realiza pruebas en todos los servidores que ejecutan los servicios de directiva de ancho de banda de la topología haciendo lo siguiente:
    
      - Comprobar que el servicio de directiva de ancho de banda (autenticación) de Lync Server se ha iniciado y puede emitir las credenciales correctas.
    
      - Comprobando que el servicio de directiva de ancho de banda (principal) de Lync Server se ha iniciado y puede realizar la comprobación de ancho de banda correctamente.

Esta herramienta debe ejecutarse desde un equipo que forme parte de la topología y tenga instalado el almacén local.

</div>

<div>

## <a name="output"></a>Output

La herramienta genera los resultados de cada una de las operaciones.

  - Si se realiza la prueba **AudioVideoEdgeServer** , los resultados de la herramienta son los siguientes:
    
      - Los resultados de la prueba de los equipos que proporcionan el servicio de autenticación de audio y vídeo de Lync Server en la topología
    
      - Los resultados de la prueba de los equipos que proporcionan el servicio perimetral de audio y vídeo de Lync Server en la topología

  - Si se realiza la prueba **BandwidthPolicyServer** , los resultados de la herramienta son los siguientes:
    
      - Los resultados de la prueba de los equipos que proporcionan el servicio de directiva de ancho de banda (autenticación) de Lync Server en la topología
    
      - Los resultados de la prueba de los equipos que proporcionan el servicio de directiva de ancho de banda (principal) de Lync Server en la topología

</div>

<div>

## <a name="requirements"></a>Requirements

  - Esta herramienta debe ejecutarse desde un equipo que esté en la topología y que tenga el almacén local.

  - La herramienta debe ejecutarse como un administrador que tenga acceso al almacén local.

</div>

<div>

## <a name="examples"></a>Ejemplos

El siguiente es un ejemplo de la entrada de la herramienta.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>Resumen

Esta herramienta puede ser un recurso valioso para los administradores de Lync Server 2013 que quieran comprobar el estado de los servidores que ejecutan los servicios de directivas de audio y vídeo y de ancho de banda.

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>Visor de configuración de red

Los administradores de software de comunicaciones de Microsoft Lync Server 2013 pueden usar el visor de configuración de red para ver la topología de red de control de admisión de llamadas (CAC) para una empresa que se aprovisiona para permitir sesiones de comunicación en tiempo real, como llamadas de voz o vídeo basadas en la capacidad de ancho de banda especificada. Lync Server 2013 los administradores definen directivas de CAC, que aplican los servicios de directivas de ancho de banda que se instalan con Lync Server 2013.

<div>

## <a name="description"></a>Descripción

El visor de configuración de red (NetworkConfigurationViewer.exe) permite a los administradores realizar las siguientes tareas:

  - Cargar y ver la topología de red de CAC de una implementación de Lync Server 2013 en un formato gráfico.

  - Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directivas de ancho de banda en un formato gráfico.

  - Guarde y almacene la topología de red de CAC en formato XML en el disco.

  - Guarde y almacene el diagrama de topología de red de CAC en formato JPG o BMP.

  - Ver los datos de configuración de la topología de red de CAC.

  - Ver la topología de red de CAC en un estilo de vista de árbol.

  - Defina los conectores personalizados para los vínculos de topología de red de CAC (por ejemplo, vínculos de sitio a región, de región a región y de sitio a sitio).

  - Ver información del sitio de la topología de red de CAC, información de región y directivas de ancho de banda aprovisionadas y vínculos de red.

</div>

<div>

## <a name="purpose"></a>Finalidad

Ver los vínculos de topología de red CAC empresarial en una interfaz gráfica.

</div>

<div>

## <a name="examples"></a>Ejemplos

**Cargar y ver la topología de red de CAC desde una implementación de Lync Server 2013 en formato gráfico:** Lync Server 2013 los administradores pueden cargar y ver la configuración de la topología de red de CAC en cualquier equipo de Lync Server 2013 mediante la opción **Descargar configuración de red** , tal como se muestra en la figura siguiente. La herramienta no podrá descargar ni ver dicha configuración cuando se implemente en un equipo que no tiene conectividad con el almacén de configuración de Lync.

![Descargar la configuración de red.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Descargar la configuración de red.")

**Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directivas de ancho de banda en formato gráfico:** Los servidores de directivas de ancho de banda de Lync Server 2013 guardan la topología de red de CAC como parte del mecanismo de registro en la ubicación del recurso compartido de archivos de Lync Server 2013. Los administradores de Lync Server pueden ver este archivo en un formato gráfico con la opción **abrir configuración de red** , tal como se muestra a continuación.

![Abrir un archivo de registro de servidor de directivas de ancho de banda.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Abrir un archivo de registro de servidor de directivas de ancho de banda.")

Guarde y almacene la topología de red de CAC en formato XML en el disco: Lync Server 2013 los administradores pueden guardar el archivo de configuración de la topología de red CAC en formato XML mediante la opción **guardar una copia de la configuración de red** , tal como se muestra a continuación. El archivo de configuración guardado puede usarse sin conexión para fines de visualización gráfica.

![Guardar la configuración de red como un archivo XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Guardar la configuración de red como un archivo XML.")

Guarde y almacene el diagrama de topología de red de CAC en formato JPG o BMP: Lync Server 2013 los administradores pueden guardar la configuración de la topología de red de CAC en formato gráfico (formatos de archivo JPG y BMP) mediante la opción **Guardar diagrama de configuración de red como imagen** , como se muestra a continuación.

![Guardar la configuración de red como una imagen.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Guardar la configuración de red como una imagen.")

**Ver los datos de configuración de la topología de red de CAC:** Lync Server 2013 los administradores pueden ver los datos de configuración de red relacionados, como regiones de red, sitios de red, perfiles de ancho de banda y direcciones IP de subred de sitio en formato de texto, mediante la opción ver datos de configuración de red, tal como se muestra a continuación.

![Ver los datos de configuración de la red.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Ver los datos de configuración de la red.")

**Ver la topología de red de CAC en un estilo de vista de árbol:** Lync Server 2013 los administradores pueden ver los datos de configuración de red relacionados en un estilo de vista de árbol gráfico usando el panel de control en el lado izquierdo de la ventana de herramientas, tal como se muestra a continuación.

![Ver los datos de configuración de red en una vista de árbol.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Ver los datos de configuración de red en una vista de árbol.")

**Definir conectores personalizados para los vínculos de topología de red de CAC (como vínculos de sitio a región, de región a región y de sitio a sitio):** Lync Server 2013 los administradores pueden definir conectores gráficos personalizados para los vínculos WAN de configuración de red de CAC mediante la opción configuración, tal como se muestra a continuación. Esto ayuda a diferenciar entre varios tipos de vínculos de red que se aprovisionan en la configuración de red.

![Definir conectores personalizados para la topología de red de CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definir conectores personalizados para la topología de red de CAC")

**Ver la información del sitio de la topología de red de CAC, información de región y directivas de ancho de banda aprovisionadas:** Lync Server 2013 los administradores pueden ver la información de región de red CAC, la información del sitio y la información de aprovisionamiento de ancho de banda de CAC relacionadas mediante las opciones que se muestran a continuación. (Por ejemplo, haga clic en **información** en una región de red o un objeto de sitio de red).

![Definir conectores personalizados para la red.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definir conectores personalizados para la red.")

</div>

<div>

## <a name="summary"></a>Resumen

Esta herramienta puede ser un recurso valioso para los administradores de Lync Server 2013 que quieran ver la topología de red de CAC para su implementación en un formato gráfico.

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>Response Group Agent Live

La aplicación de grupo de respuesta ofrece a los agentes la capacidad de tener acceso a información útil en tiempo real mediante su servicio Web integrado. Desafortunadamente, no hay ninguna vista gráfica de estos datos disponibles fuera de la aplicación. La herramienta de kit de recursos Live Response Agent Live Report resuelve este problema proporcionando una forma sencilla y gráfica para obtener acceso a esta información, mejorada con información de software de comunicaciones en tiempo real de Microsoft Lync 2013, como la presencia de otros agentes.

<div>

## <a name="description"></a>Descripción

Response Group Agent Live es una aplicación de Windows que proporciona la funcionalidad de inicio y cierre de sesión, así como información en tiempo real (como la pertenencia a grupos y el número actual de llamadas) a los agentes del grupo de respuesta. Está diseñada para ser una versión mejorada de la página grupos de agentes (accesible desde Lync 2013.

</div>

<div>

## <a name="purpose"></a>Finalidad

La aplicación de grupo de respuesta pone en cola las llamadas entrantes y, a continuación, las enruta a los grupos de agentes. Para tomar decisiones informadas sobre las llamadas al servicio, los agentes pueden obtener acceso a información en tiempo real sobre sus grupos de agentes, como qué otros agentes están disponibles y cuántas llamadas están esperando en cada cola. Esta información, inicialmente accesible solo a través del servicio de grupo de respuesta, está disponible de forma intuitiva mediante Response Group Agent Live.

<div>

## <a name="features"></a>Características

La herramienta Response Group Agent Live se basa en el servicio de grupo de respuesta y el SDK de Microsoft Lync 2013. Proporciona agentes de grupo de respuesta información y capacidades que están disponibles en el servicio de grupo de respuesta (como la pertenencia a grupos, la presencia de otros agentes y el número de llamadas en espera).

La ilustración siguiente muestra la interfaz principal de Response Group Agent Live.

![La herramienta Response Group Agent Live.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "La herramienta Response Group Agent Live.")

Las siguientes tres características principales están disponibles para los agentes en Response Group Agent Live:

  - **Iniciar/cerrar sesión:** Al contrario que la página grupos de agentes (accesible desde Lync 2013), el agente de grupo de respuesta Live permite que solo los agentes inicien o salgan de todos los grupos de agentes a la vez. Esta aplicación proporciona tres métodos rápidos para que los agentes inicien o cierren sesión:
    
      - Haga clic en los botones de inicio y cierre de sesión (verde y rojo) dentro de la aplicación.
    
      - Haga clic con el botón derecho en el icono de la bandeja del sistema y seleccione iniciar sesión o cerrar sesión.
    
      - Usar métodos abreviados de teclado configurables.

  - **Pertenencia a grupos:** Cuando se selecciona un grupo de agentes, Response Group Agent Live muestra la lista de agentes de este grupo en el panel derecho. Si Lync 2013 se está ejecutando en el mismo equipo que esta aplicación, la información de presencia y la tarjeta de contacto se muestran en el Group Response Agent Live. Los agentes pueden enviar un mensaje instantáneo o llamar a otros agentes directamente desde allí.

  - **Estadísticas en tiempo real:** Response Group Agent Live proporciona estadísticas en tiempo real para todos los grupos de agentes. La frecuencia de actualización es un minuto. Cuando un grupo de respuesta responde a una llamada, se agrega un indicador visual junto al nombre del grupo con el número actual de llamadas en cola. Al pausar el puntero sobre un grupo, también se muestra el tiempo de espera más largo.

</div>

</div>

<div>

## <a name="requirements"></a>Requirements

Response Group Agent Live requiere .NET Framework 4,0. Además, para aprovechar las características de presencia y tarjeta de contacto, Lync 2013 debe estar instalado de forma local (y estar en ejecución).

<div>

## <a name="configuration"></a>Configuración

Response Group Agent Live puede personalizarse según las preferencias individuales mediante el cuadro de diálogo Opciones de la aplicación. Además, el administrador puede definir la dirección de host predeterminada editando directamente la propiedad defaultHostAddress del archivo de RGAgentLive.exe.config.

La ilustración siguiente muestra el cuadro de diálogo Opciones que los agentes pueden usar para configurar las teclas de acceso directo y dirección de host. Para obtener acceso a este cuadro de diálogo, haga clic en el botón Opciones de la parte superior derecha de la interfaz principal.

![El cuadro de diálogo Opciones del agente de respuesta dinámica del grupo de respuesta.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "El cuadro de diálogo Opciones del agente de respuesta dinámica del grupo de respuesta.")

Las siguientes tres opciones de configuración distintas se pueden personalizar en la configuración de agente de grupo de respuesta:

  - Dirección de host: suele ser el FQDN del grupo de servidores web que pertenece al grupo principal del agente. La dirección exacta del servicio del grupo de respuesta se deriva automáticamente en segundo plano a partir de esta información (anexando la ruta de acceso correcta después del host).

  - Accesos directos: los métodos abreviados exactos para iniciar y cerrar sesión pueden personalizarse. La única limitación es que ambos métodos abreviados deben contener la tecla del logotipo de Windows (además de, al menos, otra tecla).

  - Iniciar con Windows: la aplicación se puede configurar para iniciarse automáticamente con Windows.

</div>

</div>

<div>

## <a name="examples"></a>Ejemplos

En la siguiente figura se muestra cómo llamar o enviar un mensaje instantáneo a otro agente haciendo clic con el botón secundario en el contacto en el panel derecho.

![Hacer una llamada o enviar un mensaje instantáneo.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Hacer una llamada o enviar un mensaje instantáneo.")

La ilustración siguiente muestra cómo Response Group Agent Live muestra el número actual de llamadas en la cola y el tiempo de espera más largo entre todas estas llamadas entrantes.

![Ver información de cola.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Ver información de cola.")

</div>

<div>

## <a name="summary"></a>Resumen

La rapidez en el inicio y el cierre de sesión, la pertenencia a grupos y las estadísticas básicas en tiempo real son características interesantes del agente de grupo de respuesta que solo están disponibles fuera de la aplicación desde el servicio de grupo de respuesta. Con la herramienta del kit de recursos del agente de grupo de respuesta Live, los administradores de Lync pueden proporcionar a sus agentes una aplicación de Windows que les permita realizar tareas de una manera gráfica y rápida.

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

SEFAUtil (la activación de características de extensión secundaria) es una herramienta de línea de comandos que permite a los administradores de software de comunicaciones de Microsoft Lync Server 2013 y a los agentes de asistencia técnica configurar las llamadas delegadas, el desvío de llamadas, las llamadas simultáneas, la configuración de llamada de equipo y la recogida de llamadas de grupo en nombre de un usuario de Lync Server 2013. La herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular. La herramienta SEFAUtil permite al administrador habilitar/deshabilitar/modificar el desvío de llamadas o las llamadas simultáneas en nombre del usuario. El administrador puede especificar el destino (en forma de URI de SIP) o usar un destino ya publicado por el usuario. Esta herramienta también permite a los administradores agregar o quitar delegados o miembros del grupo de llamada de equipo en nombre del usuario. Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3,0 y requiere que los administradores creen una aplicación de confianza en el almacén de administración central para SEFAUtil

SEFAUtil (activación de características de extensión secundaria) permite a los administradores y los agentes del Departamento de soporte técnico de Lync Server 2013 configurar llamadas delegadas, el desvío de llamadas, las llamadas simultáneas, la configuración de llamada de equipo y la recogida de llamadas de grupo en nombre de un usuario de Lync Server 2013. Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular.

<div>

## <a name="description"></a>Descripción

La versión actual de SEFAUtil es solo una herramienta de línea de comandos; no hay ninguna interfaz gráfica de usuario compatible. Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3,0. Las características de esta herramienta permiten que los administradores y los agentes del Departamento de soporte técnico hagan lo siguiente:

  - Ver toda la configuración de enrutamiento de llamadas de un usuario (incluye el desvío de llamadas, la delegación, las llamadas simultáneas, la llamada de equipo y la atención de llamadas de grupo)

  - Habilitar/deshabilitar/modificar la configuración de desvío de llamadas (incluye el destino y el temporizador sin respuesta)

  - Habilitar/deshabilitar/modificar las configuraciones inmediatas de reenvío de llamadas

  - Habilitar/deshabilitar/modificar la configuración de la delegación

  - Habilitar/deshabilitar/modificar la configuración de grupo de llamada de equipo
    
    <div>
    

    > [!NOTE]  
    > Nueva en Lync Server 2013 herramienta SEFAUtil

    
    </div>

  - Habilitar/deshabilitar/modificar la configuración de llamadas simultáneas (incluye el destino)
    
    <div>
    

    > [!NOTE]  
    > Nueva en Lync Server 2013 herramienta SEFAUtil

    
    </div>

  - Habilitar/deshabilitar/modificar la configuración de RECALL de llamadas de grupo
    
    <div>
    

    > [!WARNING]  
    > Nueva en Lync Server 2013 herramienta SEFAUtil

    
    </div>

Esta herramienta tiene las siguientes limitaciones:

  - Compatible solo para usuarios hospedados en un grupo de servidores de Lync Server

  - No se admite la edición en masa de la configuración de enrutamiento de llamadas para varios usuarios

</div>

<div>

## <a name="output"></a>Output

La versión actual de esta herramienta proporciona resultados sólo en la ventana del símbolo del sistema. Para obtener más información, vea la sección ejemplos más adelante en este documento.

</div>

<div>

## <a name="purpose"></a>Finalidad

A continuación se muestran algunos de los escenarios clave en los que se puede usar esta herramienta:

  - Bob es un ejecutivo y se ha movido a la telefonía de Lync Server. Ha delegado en su sistema PBX existente. Como parte de la migración a Lync, el administrador puede configurar el enrutamiento de Bob para reflejar su configuración de delegación preexistente.

  - Alicia está viajando y se da cuenta de que espera una llamada importante de uno de sus clientes. Sin embargo, se encuentra en un hotel y no tiene acceso a un equipo. Llama al Departamento de soporte técnico y solicita que se reenvíen a su número de teléfono móvil todas las llamadas realizadas a su número de trabajo. El personal del Departamento de soporte técnico puede realizar la configuración en su nombre.

  - Las llamadas de Joe a su número de trabajo van a su correo de voz móvil siempre que esté en el trabajo; sin embargo, las cosas parecen funcionar correctamente en la mayoría de las demás ubicaciones. El técnico del Departamento de soporte técnico puede ver la configuración de enrutamiento de Joe y detecta que José ha configurado las llamadas simultáneas a su teléfono móvil. El técnico pregunta a Joe sobre la cobertura móvil en su oficina y puede determinar que la regla de timbre simultáneo es lo que está causando que las llamadas se desplazan al correo de voz móvil de Joe cuando su cobertura de red es deficiente.

  - Mike es un nuevo empleado de Contoso y se une a un nuevo equipo en el que todos los miembros están configurados para la llamada de equipo, cuando se habilita para Microsoft Lync, el administrador puede establecer la configuración del grupo de llamada de equipo para incluir a todos los nuevos miembros del equipo, además, el administrador agrega Mike como miembro del grupo de llamada de equipo para cada miembro de su equipo

  - Una práctica de servicio al cliente en el Departamento de recursos humanos de Contoso es proporcionar servicio personal para todos los autores de llamadas desde la primera llamada. Dado que todos los miembros del Departamento se encuentran muy cercanos entre sí, tener todos los teléfonos que suenen al mismo tiempo con la llamada de equipo es muy disruptiva para el equipo. Para proporcionar el mejor servicio sin interrumpir a los miembros del equipo, el administrador de Lync aprovecha la capacidad de RECALL de llamadas grupales. El administrador agrega todos los miembros del Departamento a un grupo de recogida y se comunica con el número de grupo de recogida del Departamento. Cuando Samantha no está en su escritorio, Joe detecta su timbre telefónico y continúa respondiendo a la llamada desde su escritorio.

</div>

<div>

## <a name="requirements"></a>Requirements

La herramienta SEFAUtil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza. UCMA 3,0 debe estar instalado en el equipo. Para ejecutar la herramienta, se debe crear una nueva aplicación de confianza con el identificador de la aplicación SEFAUtil en ese grupo de servidores.

**Creación de una nueva aplicación de confianza para la herramienta SEFAUtil**

1.  La herramienta SEFAUTil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza. Si es necesario, puede Agregar un grupo de servidores como un nuevo grupo de aplicaciones de confianza mediante el shell de administración de Lync Server con el siguiente cmdlet:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > UCMA 3,0 debe instalarse en cualquier equipo que se use para ejecutar la herramienta SEFAUtil.

    
    </div>

2.  Una aplicación de confianza debe definirse en la topología de la herramienta SEFAUtil. Para definir SEFAUtil como una nueva aplicación de confianza, use el shell de administración de Lync Server y ejecute el siguiente cmdlet:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Si es necesario, se puede usar un puerto diferente.

    
    </div>

3.  Los cambios en la topología deben estar habilitados. La habilitación de los cambios en la topología se puede realizar mediante el shell de administración de Lync Server ejecutando el siguiente cmdlet:
    
        Enable-CsToplogy

4.  Si es necesario, instale las herramientas del kit de recursos de Lync Server 2013 en el servidor que se usará para ejecutar la herramienta SEFAUtil (el servidor debe formar parte de un grupo de aplicaciones de confianza).

5.  Compruebe que la SEFAUtil se está ejecutando correctamente. Para ello, ejecute la herramienta desde un símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación. De forma predeterminada, la herramienta estará ubicada en: "... \\ Archivos de programa \\ Microsoft Lync Server 2013 \\ reskit ". Para mostrar la configuración de desvío de llamadas de un usuario, use el siguiente comando:
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    Se debe mostrar la configuración de desvío de llamadas del usuario.

<div>

## <a name="group-call-pickup"></a>Atender llamada grupal

La atención de llamadas grupales requiere una configuración adicional en Lync Server para que la capacidad esté totalmente habilitada. Antes de asignar grupos de recogida a los usuarios, consulte la documentación del producto de recogida de llamadas de grupo para conocer los pasos de planeación e implementación de esta función.

</div>

</div>

<div>

## <a name="examples"></a>Ejemplos

<div>

## <a name="display-current-call-handling-settings"></a>Mostrar la configuración de control de llamadas actual

El siguiente comando muestra el control de llamadas del usuario. `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> En este ejemplo se usa el modificador <STRONG>/Server</STRONG> para especificar el servidor de Lync al que se va a conectar.



</div>

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>Establecer el destino de desvío de llamadas/sin respuesta

En este ejemplo se establece el destino de desvío de llamadas y de no respuesta y el retraso del timbre. Aquí no se proporciona el modificador/Server; SEFAUtil intenta detectar automáticamente el Lync Server.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>Habilitar el desvío de llamadas inmediatamente

En este ejemplo se habilita inmediatamente el desvío de llamadas a otro usuario.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a>Deshabilitar el desvío de llamadas inmediatamente

En este ejemplo se deshabilita inmediatamente el desvío de llamadas.

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Adición de un usuario como delegado y configuración de llamadas simultáneas de delegados

En este ejemplo se agrega un usuario como delegado y se configura la llamada simultánea de los delegados.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>Cambiar la regla de llamadas simultáneas de delegados

En este ejemplo se cambia la regla de llamadas simultáneas que se estableció en el ejemplo anterior por la regla de timbre aplazado.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a>Quitar el delegado

En este ejemplo se quita el delegado.

<div>


> [!NOTE]  
> Cuando se quita el último delegado, se deshabilita automáticamente el timbre de delegación.



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Adición de un delegado y configuración de la regla de Call-Forward a delegados

En este ejemplo se agrega un delegado y se configura la regla de desvío de llamadas a delegados.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Habilitar llamadas simultáneas y establecer un número de destino

En este ejemplo se habilitan las llamadas simultáneas y se establece un número de destino de llamadas simultáneas.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> Para cambiar el número de destino de llamadas simultáneas de un usuario que ya tiene habilitada la llamada simultánea, mantenga el comando con el modificador/enablesimulring; de lo contrario, no se cambiará el número de destino.



</div>

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a>Deshabilitar las llamadas simultáneas

En este ejemplo se deshabilita la característica de llamadas simultáneas.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Adición de un integrante del grupo para Team-Call y configuración de llamadas simultáneas al grupo miembros del Team-Call

En este ejemplo se agrega un integrante del grupo al grupo de llamada de equipo de un usuario y se habilita la característica de llamadas simultáneas al grupo de llamada de equipo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> Al agregar un miembro al grupo de llamada de equipo de un usuario, se cambiará automáticamente el configuración de llamadas simultáneas de los usuarios para situaciones su grupo de llamada de equipo.



</div>

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a>Quitar un miembro del grupo de Team-Call

En este ejemplo se quita un miembro del equipo del grupo de llamada de equipo de un usuario.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> Si el miembro que se va a quitar es el único miembro del grupo de llamada de equipo, las llamadas simultáneas al grupo de llamada de equipo se deshabilitarán de forma automática.



</div>

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>Establecer el anillo retrasado en el grupo de Team-Call

En este ejemplo se cambia el timbre retrasado a la configuración de hora de grupo de llamada de equipo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a>Habilitar Team-Call

En este ejemplo se habilita la llamada de equipo para un usuario determinado.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> Si el grupo de llamada de equipo del usuario no tiene miembros, la llamada de equipo no se habilitará.



</div>

**Resultado**

</div>

<div>

## <a name="disable-team-call"></a>Deshabilitar Team-Call

En este ejemplo se deshabilita la llamada de equipo para un usuario determinado.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Habilitar la atención de llamadas grupales y asignar un grupo de recogida a un usuario

En este ejemplo se asigna un grupo de recogida a un usuario y se habilita la recogida de llamadas grupales.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**Resultado**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a>Deshabilitar la recogida de llamadas de grupo

En este ejemplo se deshabilita la llamada de llamadas grupales para un usuario determinado.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> Cuando se deshabilita la recepción de llamadas de grupo para un usuario, no se conserva el número de grupo que se asignó al usuario. Si, posteriormente, desea volver a habilitar la atención de llamadas grupales para ese usuario, debe volver a asignar el número de grupo con el modificador/enablegrouppickup.



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a>SYSPrep.ps1

<div>

## <a name="description"></a>Descripción

SYSPrep.ps1 es un script de Windows PowerShell que instalará los siguientes requisitos previos de Lync Server 2013 en el equipo del sistema operativo Windows Server 2008.

  - Microsoft .NET Framework 4,5

  - Microsoft SQL Server Express

  - Windows PowerShell versión 3,0

  - Paquete redistribuible de Visual C++ 2010

  - Actualizaciones de Internet Information Server

  - Windows Identity Foundation

  - Lync Server 2013 archivos principales

Aunque el nombre del script es similar a la herramienta de preparación del sistema para los sistemas operativos de Microsoft Windows, son diferentes. Este script solo instalará los requisitos previos necesarios para Lync Server 2013. Una vez instalados estos requisitos previos, puede usar la herramienta SYSPrep de Windows para crear una imagen del servidor.

</div>

<div>

## <a name="requirements"></a>Requirements

Antes de ejecutar el script de SYSPrep.ps1, debe copiar los archivos de requisitos previos en una carpeta local del equipo del sistema operativo Windows Server 2008 (por ejemplo, **D: \\ Setup)**. Esta carpeta también debe incluir una copia de los archivos de Lync Server 2013, en concreto **Setup.exe.** Los archivos de requisitos previos se pueden descargar desde las siguientes ubicaciones:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Requisitos previos</th>
<th>Ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .NET Framework 4,5</p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows PowerShell versión 3,0</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Paquete redistribuible de Visual C++ 2010</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Actualizaciones de Internet Information Server</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup.exe</p></td>
<td><p>Copiar desde medios de Lync Server 2013</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a>Parámetro

El parámetro **– SetupFolder** toma como argumento la ubicación del directorio de los archivos de requisitos previos

</div>

<div>

## <a name="examples"></a>Ejemplos

Para ejecutar el script de SYSPrep.ps1 e instalar los requisitos previos de Lync Server 2013, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados:

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>Número de anuncios no asignados a la migración

La herramienta de migración de anuncios de números sin asignar permite que un administrador de Lync mueva la configuración de números sin asignar a la que presta servicio la aplicación de anuncio de un servidor o grupo de Lync de origen a un servidor o grupo de servidores de Lync de destino.

<div>

## <a name="description"></a>Descripción

La herramienta de migración de anuncios de números sin asignar es un script de Windows PowerShell que mueve la configuración de números sin asignar que recibe el servicio de la aplicación de anuncio de un servidor o grupo de origen a otro servidor o grupo de servidores.

Cuando se ejecuta, el script de migración de números sin asignar de anuncios realizará las siguientes operaciones:

1.  Mueva todos los archivos de audio usados por los anuncios de números sin asignar de la aplicación de anuncio hospedada en el servidor o grupo de origen al almacén de archivos del servidor o grupo de destino.
    
    <div>
    

    > [!NOTE]  
    > los archivos de audio se quitan del grupo de origen una vez que se copian en el grupo de servidores de destino.

    
    </div>

2.  Se mueven todos los anuncios de números sin asignar configurados para la aplicación de anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.

3.  Reasignar todos los intervalos de números no asignados que reciben servicio de la aplicación de anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.

Después de ejecutar correctamente el script, todos los intervalos de números sin asignar que provienen de la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen se proporcionarán con la misma configuración que el servidor o el grupo de destino.

</div>

<div>

## <a name="output"></a>Output

El script **Move-CsAnnouncementConfiguration** indica en la ventana del shell de administración de Lync desde donde se ejecuta el éxito o el fracaso de la operación de migración.

Si cualquier error interrumpe la ejecución de la operación, los intervalos de números sin asignar que se movieron correctamente al destino permanecerán en el destino en un formulario operativo y el resto de los intervalos de números sin asignar que se van a migrar permanecerán en el origen también en un formulario operativo. Para migrar por completo el resto de la configuración, vuelva a ejecutar el script después de solucionar el error.

</div>

<div>

## <a name="purpose"></a>Finalidad

Se puede usar el script de migración de anuncios de números sin asignar en los tres escenarios siguientes:

  - **Migrar las opciones de configuración a una nueva versión de Lync Server:** Contoso está en proceso de migrar a Lync Server 2013 y, como parte del proceso de migración, el administrador de Lync Server desearía mover la configuración de números no asignados a la que el anuncio ha dado servicio desde la implementación de Lync Server 2010 a la nueva implementación de Lync Server 2013. Para mover las opciones de configuración, el administrador de Lync Server usa la herramienta de migración de anuncios de números sin asignar.

  - **Revertir una implementación de Lync server 2013 a Lync server 2010:** Debido a los factores inesperados, Contoso tiene que revertir la migración a la nueva implementación de Lync Server 2013. Para minimizar las interrupciones en el servicio, el administrador de Lync Server usa la herramienta de migración de anuncios de números sin asignar para revertir la configuración de la implementación de Lync Server 2013 a la implementación de Lync Server 2010.

  - **Movimiento de datos entre implementaciones de Lync:** Contoso está en proceso de reemplazar todos los servidores de un grupo por los nuevos servidores. Su estrategia es implementar un nuevo grupo de servidores de Lync Server 2013, mover todos los datos del antiguo al nuevo y, a continuación, deshacer el grupo anterior. Una vez que se haya implementado el nuevo grupo de servidores, se usará la herramienta de migración de anuncios de números sin asignar para mover la configuración del grupo anterior al nuevo.

<div>

## <a name="requirements"></a>Requirements

Los siguientes son los requisitos principales necesarios para ejecutar correctamente la herramienta:

1.  El script debe ejecutarse desde un equipo que tenga instalado el shell de administración de Lync Server 2013.

2.  La aplicación de anuncio tiene que implementarse correctamente en los servidores o grupos de Lync de origen y de destino.

<div>

## <a name="move-csannouncementconfiguration-script"></a>Script de Move-CsAnnouncementConfiguration

La secuencia de comandos Move-CsAnnouncementConfiguration requiere los dos parámetros que se describen en la tabla siguiente.

![Parámetros Move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Parámetros de Move-CsAnnouncementConfiguration.")

</div>

</div>

</div>

<div>

## <a name="examples"></a>Ejemplos

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Lync Server 2010 a un grupo de servidores de Lync Server 2013

En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Lync Server 2010) al grupo de servidores de destino (Lync Server 2013).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Lync Server 2013 a un grupo de servidores de Lync Server 2010

En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Lync Server 2013) al grupo de servidores de destino (Lync Server 2010).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>Datos de conf de Web

La herramienta de datos Web conf permite que un administrador del software de comunicaciones Lync Server 2013 tenga más control sobre los datos asociados con las conferencias web del organizador. Los escenarios incluyen la capacidad de eliminar los datos específicos de una reunión de un usuario en función de los criterios de marca de tiempo.

<div>

## <a name="description"></a>Descripción

Esta herramienta permite al administrador realizar las siguientes operaciones:

1.  Buscar todos los datos de conferencias web asociados con un único usuario.

2.  Eliminar todos los datos de conferencias web asociados con un único usuario.

3.  Elimine todos los datos de conferencias web asociados con un único usuario que sea anterior a una fecha concreta.

4.  Se mueven todos los datos de conferencias web asociados con un usuario único cuando este usuario se mueve de un grupo de servidores a otro.

<div>


> [!NOTE]  
> Las herramientas del kit de recursos para Lync Server 2010 admiten el traslado de todos los datos de conferencias web asociados con un usuario único cuando se mueve a ese usuario de un grupo de servidores a otro. Esa funcionalidad ahora está en desuso de esta herramienta en favor del parámetro <STRONG>MoveConferenceData</STRONG> . Para obtener más información sobre este parámetro, consulte el cmdlet <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> .



</div>

La herramienta elimina los datos de la reunión solo para las reuniones inactivas. Las reuniones activas (o reuniones en sesiones) no se pueden eliminar.

Esta herramienta debe ejecutarse desde un equipo que esté en el mismo grupo de servidores que el usuario de destino. El usuario cuyos datos de contenido de reunión se administran mediante esta herramienta debe estar hospedado en el mismo grupo de usuarios.

</div>

<div>

## <a name="output"></a>Output

Esta herramienta genera los resultados de cada una de las operaciones:

  - Si se realiza una consulta, la herramienta genera la lista de todas las carpetas de datos de reuniones inactivas que el usuario tiene como organizador.

  - Si se realiza una eliminación, la herramienta genera la lista de todas las carpetas de datos de la reunión cuyos datos se eliminarán.

</div>

<div>

## <a name="requirements"></a>Requirements

La herramienta debe ejecutarse en el mismo grupo de servidores donde está hospedada actualmente el organizador.

La herramienta debe ejecutarse con privilegios de administrador con acceso al almacén de archivos de contenido.

</div>

<div>

## <a name="examples"></a>Ejemplos

En la tabla siguiente se describen los parámetros, algunos de los cuales se usan en los ejemplos.

![Parámetros de la herramienta de datos Web conf.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parámetros de la herramienta de datos Web conf.")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

En el ejemplo anterior se muestra el funcionamiento de un comando de consulta. El resultado de un comando de este tipo sería una lista de todas las carpetas de contenido de reuniones que se verían afectadas por esta herramienta.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

El ejemplo anterior es un ejemplo de un comando DELETE. El comando eliminar quitará todas las carpetas de reuniones inactivas de este usuario.

</div>

<div>

## <a name="summary"></a>Resumen

Esta herramienta puede ser un recurso útil para los administradores que necesitan un control más preciso sobre los datos de las reuniones de conferencia.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
