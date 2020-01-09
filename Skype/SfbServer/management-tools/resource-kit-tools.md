---
title: Documentación de las herramientas del kit de recursos de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: En este tema se describen las herramientas del kit de recursos de Skype empresarial Server 2015, incluido el propósito de cada herramienta y ejemplos de su uso. El kit de recursos de Skype empresarial Server 2015 ayuda a simplificar las tareas rutinarias a los administradores de ti que implementan y administran Skype empresarial Server 2015. Por ejemplo, la herramienta Web Conf Data se puede usar para controlar fácilmente los datos que suben los usuarios durante una reunión de Internet. La herramienta SEFAUtil se puede usar para delegar el desvío de llamadas y respuesta para los usuarios. Recomendamos a los administradores de ti que usen estas herramientas para administrar de forma más eficaz Skype empresarial Server 2015.
ms.openlocfilehash: 0087f4286246833f0266ad0c78636bad00167756
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992537"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Documentación de las herramientas del kit de recursos de Skype Empresarial Server 2015

En este tema se describen las herramientas del kit de recursos de Skype empresarial Server 2015, incluido el propósito de cada herramienta y ejemplos de su uso. El kit de recursos de Skype empresarial Server 2015 ayuda a simplificar las tareas rutinarias a los administradores de ti que implementan y administran Skype empresarial Server 2015. Por ejemplo, la herramienta **Web Conf Data** se puede usar para controlar fácilmente los datos que suben los usuarios durante una reunión de Internet. La herramienta **SEFAUtil** se puede usar para delegar el desvío de llamadas y respuesta para los usuarios. Recomendamos a los administradores de ti que usen estas herramientas para administrar de forma más eficaz Skype empresarial Server 2015.

## <a name="installation-of-the-resource-kit-tools"></a>Instalación de las herramientas del kit de recursos

Para instalar el kit de recursos de Skype empresarial Server 2015, descargue [OCSReskit. msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) desde el centro de descarga.

Ejecute **OCSResKit.msi** para hacer una instalación sencilla. El archivo .msi instala todas las herramientas en la ruta de acceso siguiente: **%Archivos de programa%\Skype Empresarial Server 2015\ResKit**. Las herramientas que son ejecutables independientes se encuentran en esta carpeta. Las herramientas que tienen archivos auxiliares están en sus propias subcarpetas.

## <a name="supported-environments"></a>Entornos compatibles

El kit de recursos de Skype empresarial Server 2015 debe instalarse en un servidor que cumpla con las especificaciones necesarias para Skype empresarial Server 2015, generalmente uno que se usa para ejecutar Skype empresarial Server 2015.

## <a name="resource-kit-tools-overview"></a>Información general sobre las herramientas del kit de recursos

A continuación se muestra una lista de las herramientas que se proporcionan en el kit de recursos de Skype empresarial Server 2015. En las siguientes secciones se incluye una descripción de cada herramienta, además de los requisitos y ejemplos de uso.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Bandwidth Policy Service Monitor (Monitor del servicio de directiva de ancho de banda)](resource-kit-tools.md#bpsm)

- [Bandwidth Utilization Analyzer (Analizador de uso de ancho de banda)](resource-kit-tools.md#bua)

- [Call Parkometer (Estacionamiento de llamadas)](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Import Storage Service Data (Importación de datos del servicio de almacenamiento)](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Lookup User Console (Consola de búsqueda de usuario)](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Network Configuration Viewer (Visor de configuración de red)](resource-kit-tools.md#NCV)

- [Response Group Agent Live (Información en vivo del agente del grupo de respuesta)](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [Unassigned Number Announcements Migration (Migración de anuncios de números sin asignar)](resource-kit-tools.md#UNAM)

- [Web Conf Data](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

La herramienta de configuración del servicio de libreta de direcciones (ABSConfig) es una herramienta administrativa que ayuda a los administradores a personalizar la configuración del servicio de libreta de direcciones en Skype empresarial Server 2015. Esta herramienta también permite a los administradores de Skype empresarial Server 2015 restaurar la configuración predeterminada del servicio de libreta de direcciones.

### <a name="description"></a>Descripción

ABSConfig es una aplicación de interfaz gráfica de usuario que permite a los administradores configurar atributos de servicios de dominio de Active Directory relacionados con el servicio de libreta de direcciones.

Los escenarios principales para la herramienta son los siguientes:

- Para permitir a los administradores asignar atributos de los servicios de dominio de Active Directory a los atributos de Skype empresarial Server 2015.

- Permitir a los administradores especificar el atributo de Active Directory Domain Services que se incluirá o excluirá en los archivos del Servicio de libreta de direcciones.

- Permitir a los administradores restaurar la configuración predeterminada del Servicio de libreta de direcciones.

La herramienta ABSConfig puede iniciarse mediante el archivo ABSConfig.exe. La herramienta se abre en la ficha **configurar atributos** . Esta tabla tiene opciones para asignar atributos de servicios de dominio de Active Directory a los campos de atributo de Skype empresarial Server 2015 y para especificar qué usuarios desea incluir o excluir en archivos del servicio de libreta de direcciones basándose en filtros de atributos específicos. También tiene opciones para personalizar el valor del número de teléfono que se incluirá en el archivo de la libreta de direcciones. La opción **Restaurar valores predeterminados** permite a los administradores restaurar la configuración del Servicio de libreta de direcciones a los valores predeterminados.

> [!NOTE]
> La reasignación de atributos de AD a nombres de campo de OC diferentes solo funciona para la descarga de archivos de la libreta de direcciones y no es compatible con la consulta Web de la libreta de direcciones.

### <a name="output"></a>Salida

ABSConfig guarda la configuración del Servicio de libreta de direcciones en la base de datos.

```PowerShell
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Finalidad

ABSConfig ofrece una manera rápida y fácil de personalizar el servicio de libreta de direcciones de Skype empresarial Server 2015.

### <a name="requirements"></a>Requisitos

#### <a name="computer"></a>Equipo

ABSConfig solo se puede ejecutar desde un equipo unido a un dominio que tenga instalado Skype empresarial Server 2015. En el caso de Skype empresarial Server 2015, Enterprise Edition, esta herramienta se puede ejecutar en cualquier servidor front-end que tenga habilitado el servicio de libreta de direcciones durante la instalación.

#### <a name="network"></a>Red

El equipo debe ser capaz de conectarse al grupo de servidores front-end y a la base de datos back-end.

#### <a name="software"></a>Software

Antes de ejecutar la herramienta ABSConfig es necesario instalar los siguientes componentes de software:

- Skype Empresarial Server 2015

#### <a name="users"></a>Usuarios

Administradores que tienen los permisos necesarios para actualizar la implementación de Skype empresarial Server 2015.

### <a name="examples"></a>Ejemplos

Para iniciar ABSConfig, escriba **ABSConfig.exe** en un símbolo del sistema. A continuación se muestra la interfaz de usuario de la herramienta ABSConfig.

![La herramienta ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Resumen

La herramienta ABSConfig ofrece a los administradores una herramienta rápida y fácil de usar para personalizar el servicio de libreta de direcciones de Skype empresarial Server 2015.

## <a name="bandwidth-policy-service-monitor"></a>Bandwidth Policy Service Monitor (Monitor del servicio de directiva de ancho de banda)
<a name="bpsm"> </a>

La herramienta Bandwidth Policy Service Monitor permite a los administradores ver una lista de lo siguiente:

1. Todos los servicios de directiva de ancho de banda 2015 de Skype empresarial Server configurados (autenticación y núcleo) en la topología

2. Las conexiones que realiza cada servicio con otros servicios de directivas de ancho de banda y a los servidores perimetrales.

3. Todos los vínculos configurados en el documento de configuración de red y el uso de ancho de banda en tiempo real informado por los servicios de directiva de ancho de banda.

### <a name="description"></a>Descripción

La herramienta Bandwidth Policy Service Monitor se implementa como una aplicación basada en GUI. Los administradores pueden ejecutar la herramienta mediante PDPMonUI.exe.

Al iniciar la aplicación, esta intenta detectar la lista de servicios de directiva de ancho de banda en la topología. Después de completar la actualización inicial, en el panel de la izquierda de la ventana se muestra una lista de servicios agrupados por los clústeres a los que pertenecen.

Cuando los administradores seleccionan un servicio de directiva de ancho de banda concreto, en el panel de la derecha se muestra información sobre dicho servicio. Además, el panel también contiene dos pestañas principales con información.

#### <a name="machine-info-tab"></a>Pestaña Información de equipo

La pestaña **Información de equipo** contiene información detallada sobre el servicio de directiva de ancho de banda seleccionado, además de la lista y el estado de todas las conexiones realizadas por dicho servicio de directiva de ancho de banda seleccionado con otros servicios.

#### <a name="topology-info-tab"></a>Pestaña Información de topología

En la pestaña **Información de topología** se muestra una lista de todos los vínculos configurados en las opciones de red. Para cada vínculo se muestra la capacidad de ancho de banda de audio y de vídeo. Además, también se muestra el ancho de banda utilizado actualmente, tanto en kbps como en porcentaje de capacidad. La herramienta utiliza códigos de color para resaltar vínculos cuyo uso está próximo al límite de capacidad, lo que permite a los administradores aislarlos rápidamente.

> [!NOTE]
>  Si la herramienta Monitor de servicio de directivas de ancho de banda experimenta errores cuando se conecta a cualquiera de los servicios de directiva de ancho de banda configurado, la información de las pestañas información del **equipo** y información de la **topología** no se rellenará. Sin embargo, es posible que la herramienta pueda conectarse de forma inicial, pero que posteriormente pierda la conexión al servicio. En estos casos, los administradores podrían ver información desactualizada. En las pestañas hay una marca de tiempo **Última actualización** que permite a los administradores ver cuándo se actualizó por última vez un servicio de directiva de ancho de banda concreto.

### <a name="output"></a>Salida

No hay salida de línea de comandos; la salida del programa está contenida en la interfaz gráfica de usuario (GUI) principal.

### <a name="purpose"></a>Finalidad

El objetivo de la herramienta Bandwidth Policy Service Monitor es permitir a los administradores ver el estado de los servicios de directiva de ancho de banda definidos en la topología. Además, los administradores pueden ver el uso de ancho de banda en tiempo real de todos los vínculos definidos en el documento de configuración de red.

### <a name="requirements"></a>Requisitos

La herramienta Monitor de servicio de directivas de ancho de banda debe ejecutarse en un equipo que forme parte de la topología de Skype empresarial Server.

### <a name="summary"></a>Resumen

La herramienta Bandwidth Policy Service Monitor puede ser un recurso útil para los administradores, ya que permite inspeccionar el estado de todos los servicios de directiva de ancho de banda en la topología y, lo que es aún más importante, les permite conocer el uso de ancho de banda en tiempo real de los vínculos definidos en las opciones de configuración de red.

## <a name="bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer (Analizador de uso de ancho de banda)
<a name="bua"> </a>

Bandwidth Utilization Analyzer es una herramienta que genera informes sobre diferentes vistas de consumo de ancho de banda por los puntos de conexión de comunicaciones unificadas en vínculos WAN de la red empresarial. Estos informes pueden utilizarse para conocer el patrón de consumo de ancho de banda y ayudar a planificar la capacidad de ancho de banda.

### <a name="description"></a>Descripción

El analizador de uso de ancho de banda se implementa como una aplicación basada en GUI. Esta herramienta genera informes específicos para el uso de audio en la red y ayuda a planificar la capacidad. Además, también itera en la capacidad de ancho de banda asignada a diferentes vínculos.

### <a name="output"></a>Salida

El analizador de uso de ancho de banda proporciona representaciones gráficas de la capacidad de ancho de banda y el consumo de audio para todos los vínculos WAN configurados en el sistema.

### <a name="purpose"></a>Finalidad

En cualquier implementación de voz y vídeo, es fundamental supervisar y comprender la tendencia del uso del ancho de banda del tráfico multimedia en toda la red empresarial. La herramienta Bandwidth Utilization Analyzer permite a los administradores conseguir justo eso. Esta herramienta hace lo siguiente:

- Genera informes específicos para el uso de audio en la red

- Mejora la eficacia de planificación de capacidad y la iteración en la capacidad de ancho de banda asignada a diferentes vínculos

El analizador de uso de ancho de banda puede generar las siguientes representaciones gráficas de capacidad de ancho de banda e informes de uso:

- Todos los vínculos WAN en la red empresarial

- Filtrados por los vínculos WAN seleccionados

- Filtrados por los vínculos WAN que han superado la capacidad de vínculos

- Filtrados por los vínculos WAN que no han utilizado toda la capacidad de ancho de banda proporcionada

- Filtrados por los vínculos WAN que han alcanzado niveles críticos (un uso de ancho de banda superior al 90 % de capacidad de ancho de banda del vínculo WAN)

- Filtrados por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregionales y vínculos dentro de un sitio

- Filtrados por región de red

#### <a name="applications"></a>Aplicaciones

El analizador de uso de ancho de banda incluye las siguientes dos aplicaciones (herramientas):

- **WanLinkLogCollector. exe** esta herramienta permite al usuario introducir la información requerida.

- **BandwidthUtilizationAnalyzer. xlsm** el informe de software de hoja de cálculo de Microsoft Excel se inicia automáticamente mediante WanLinkLogCollector. exe. Esta aplicación permite al usuario aplicar filtros al informe, como se muestra posteriormente en este artículo.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fases de uso de Bandwidth Utilization Analyzer

Existen dos fases al usar el analizador de uso de ancho de banda:

- Recopilar registros, que se realiza automáticamente mediante WanLinkLogCollector.exe

- Personalizar informes, que se realiza mediante BandwidthUtilizationAnalyzer.xlsm

> [!IMPORTANT]
> No se recomienda que los usuarios finales inicien BandwidthUtilizationAnalyzer.xlsm de forma manual.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Inicio del analizador de uso de ancho de banda

Inicie WanLinkLogCollector.exe en el símbolo del sistema o mediante el Explorador de Windows.

 **Uso de WanLinkLogCollector.exe**

Hay tres pasos para usar WanLinkLogCollector.exe:

1. **Registrar la escala de tiempo** Proporcionar la escala de tiempo en la que se debe generar el informe

2. **Especificar los directorios de archivos** Proporcionar información de ubicación del archivo

3. **Recopilar los registros e iniciar el visor de informes** Ejecutar el comando para generar el informe

#### <a name="step-1---log-the-timeline"></a>Paso 1: registrar la escala de tiempo

Al registrar la escala de tiempo, el usuario de la herramienta puede especificar lo siguiente como se muestra en la ilustración siguiente. 

1. **Fecha de inicio** Es la fecha de inicio de la escala de tiempo para la que se genera el informe; por ejemplo, 1 de agosto de 2010.

2. **Fecha de finalización** Es la fecha de finalización de la escala de tiempo para la que se genera el informe; por ejemplo, 30 de septiembre de 2010.

     ![Fecha de inicio y fin en el análisis de utilización de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Paso 2: especificar los directorios de archivos

El usuario puede especificar los directorios de archivos siguientes, como se muestra.

- **Ubicación de los archivos de registro del servidor** La ubicación de la carpeta donde se almacenan los registros del servidor de directivas de ancho de banda. Esto \<suele encontrarse\> \\ en un fileserver\><opción de fe \AppServerFiles\PDP.

- **Ubicación de almacenamiento temporal de archivos** Ubicación del archivo temporal donde se almacenan los archivos intermedios mientras se genera el informe.

![Directorios de archivos en análisis de utilización de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> Compruebe que el usuario de la herramienta posee acceso a los archivos de los registros del servidor y a la carpeta donde se almacenan los archivos temporales.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Paso 3: recopilar los registros e iniciar el visor de informes

Para recopilar los registros e iniciar el visor de informes, haga clic en **Ejecutar** como se indica a continuación. Este paso recopila todos los datos necesarios.

![Recopilación de datos en el análisis de utilización de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Cuando la validación de entrada es correcta, se muestra el mensaje que aparece a continuación.

![Notificación de registros recopilados en la utilidad de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Haga clic en **Aceptar**. BandwidthUtilizationAnalyzer.xlsm se iniciará automáticamente. Siga las instrucciones del cuadro de mensaje. Para obtener más información, consulte **Uso de BandwidthUtilizationAnalyzer.xlsm** en la sección siguiente.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Uso de BandwidthUtilizationAnalyzer.xlsm

1. Cuando BandwidthUtilizationAnalyzer.xlsm se inicie automáticamente, haga clic en **Actualizar** como se muestra a continuación.

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Al abrir una carpeta de archivos, seleccione consolidated.csv de la ubicación especificada en el cuadro de mensaje, como se muestra a continuación. También se muestra la ubicación como **C:\Temp**.

     ![Abrir una carpeta en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Haga clic en **Importar**.

4. Se generará automáticamente la representación gráfica. Está disponible cuando desaparece el puntero que indica un proceso en segundo plano.

     ![Aplicación de filtros en la vista de informes.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Aplicar filtros a la vista de informes

Los filtros que se pueden aplicar a la vista de informes son los siguientes:

![Aplicación de filtros en la vista de informes.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Nombre** Filtra por vínculos WAN (el filtro se encuentra en la parte derecha del gráfico). El prefijo indica los siguientes tipos de vínculos; consulte el cuadro vertical (azul):

   - **Sitio S** El vínculo WAN de un sitio de red con una región de red

   - **ES entre sitios** El vínculo WAN entre dos sitios de red

   - **Interregional R** El vínculo WAN entre dos regiones de red

2. **Límite superado** Filtra por vínculos WAN cuyo uso de ancho de banda supera la capacidad de ancho de banda

3. **Niveles críticos** Filtra por vínculos WAN cuyo uso de ancho de banda ha alcanzado el 90 % o más de la capacidad de ancho de banda

4. **Infrautilizados** Filtra por vínculos WAN cuyo uso de ancho de banda ha sido inferior al 25 % de la capacidad de ancho de banda

5. **Tipo de vínculo** Filtra por los siguientes tipos de vínculos WAN:

   - 
            Tipo **sitio de red**

   - 
            Tipo **entre sitios**

   - 
            Tipo **vínculo entre regiones**

6. **Región** Filtra por región de red

En las ilustraciones siguientes se muestran los filtros descritos anteriormente.

Filtrar por **Nombre**. Seleccione la lista de vínculos que han de mostrarse en el gráfico.

![Filtrado por Nombre en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filtrar por **Límite superado**. Seleccione **True** para aplicar el filtro.

![Filtrado por Límite superado.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtrar por **Niveles críticos**. Seleccione **True** para aplicar el filtro.

![Filtrado por Niveles críticos.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtrar por **Infrautilizado**. Seleccione **True** para aplicar el filtro.

![Filtrado por Sin aprovechar.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtrar por **Tipo de vínculo**. Seleccione el tipo o tipos que desee mostrar.

![Filtrado por Tipo de vínculo.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtrar por **Región**. Seleccione una lista de regiones cuyos vínculos desee mostrar.

![Filtrado por Región.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Requisitos

- .NET Framework 3.5

- Microsoft Excel 2010 o Excel 2007

### <a name="summary"></a>Resumen

El analizador de uso de ancho de banda se utiliza para representar el uso de ancho de banda de audio para el tráfico de comunicaciones unificadas en la red. Esta herramienta también se puede utilizar para informar sobre el uso de ancho de banda de vídeo en la red.

## <a name="call-parkometer"></a>Call Parkometer (Estacionamiento de llamadas)
<a name="callpark"> </a>

Call Parkometer es una aplicación de línea de comandos que proporciona acceso rápido a la base de datos de órbitas de estacionamiento de llamadas.

### <a name="description"></a>Descripción

Call Parkometer es una herramienta que se utiliza para realizar un seguimiento de las llamadas estacionadas actualmente. También recopila estadísticas sobre el uso de órbitas y el servidor de estacionamiento de llamadas (CPS). Esta herramienta de línea de comandos proporciona acceso de lectura y escritura a la base de datos de SQL Server de CPS a partir de un equipo conectado local o remoto.

Todas las opciones se excluyen mutuamente. La sintaxis de línea de comandos es la siguiente:

- parámetro **-o** : muestra todos los intervalos de órbita configurados para este grupo.

- parámetro **-n** : muestra todas las órbitas usadas actualmente en este grupo. La información que se muestra es la siguiente:

  - Identificador uniforme de recursos (URI) de SIP del estacionado y el estacionador.

  - Nombre de host del CPS donde se ha estacionado la llamada.

  - Marca de tiempo correspondiente al momento en que se estacionó la llamada.

- parámetro **-f** : muestra el número de órbitas disponibles actualmente en el grupo.

- **-r \<parámetro\> -n** : enumera \<las\> n últimas llamadas aparcadas. La información mostrada es la siguiente:

  - URI de SIP del estacionado.

  - URI de SIP del estacionador.

  - Nombre de host del CPS donde se estacionó la llamada.

  - Marca de tiempo correspondiente al momento en que se recuperó o finalizó la llamada.

- **-t\<n\> ** parámetro-prueba para reservar una órbita en la base de datos para mostrar la aleatoriedad de los números de órbita asignados.

### <a name="output"></a>Salida

Según los parámetros de entrada especificados en el símbolo del sistema, Call Parkometer muestra la salida siguiente:

- Todos los intervalos de órbitas configurados para este grupo de servidores

- Llamadas estacionadas actualmente

- Número de órbitas libres (disponibles)

- Llamadas estacionadas recientemente

- Órbitas reservadas para comprobar valores de órbitas uniformes y aleatorias

### <a name="purpose"></a>Finalidad

El objetivo de la herramienta CPS es proporcionar acceso mediante línea de comandos a la base de datos de CPS. El administrador puede ver el uso de CPS y determinar el número de órbitas asignadas a un grupo de servidores.

### <a name="requirements"></a>Requisitos

No hay requisitos si esta herramienta se ejecuta en el mismo equipo que ejecuta CPS. Si esta herramienta se ejecuta en un equipo remoto, la base de datos de SQL Server usada por Skype empresarial Server 2015 debe estar configurada para permitir el acceso remoto. Llame a Parkometer debe estar configurado con una cadena de conexión de base de datos de SQL Server para conectarse al servidor SQL Server del grupo. Esta cadena de conexión de base de datos de SQL Server se define en el archivo de configuración **parkometer. exe. config**. Debe colocarse en el mismo directorio donde se encuentra parkometer. exe. El siguiente archivo XML es un ejemplo de parkometer. exe. config. Los parámetros que deben configurarse son el nombre de usuario (por ejemplo, mydomain\Administrator), la contraseña (por ejemplo, contraseña) y el nombre de host (por ejemplo, mi nombre).

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

### <a name="examples"></a>Ejemplos

Intervalos de órbita implementados: el parámetro-o muestra todos los intervalos de órbita que están configurados para este grupo, como se muestra

![Órbita de estacionamiento en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Llamadas actualmente estacionadas: el parámetro-n muestra todas las órbitas usadas actualmente en este grupo, como se muestra

![Llamadas actualmente estacionadas en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Número de órbitas gratis: el parámetro-f muestra el número de órbitas libres actualmente en el grupo, como se muestra

![Órbitas libres en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Llamadas aparcadas recientemente: el parámetro \<-\> r n enumera \<las\> n últimas llamadas estacionadas, como se muestra.

![Llamadas recién estacionadas en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Prueba de reserva orbital: el parámetro \<-\> t n prueba la reserva de una órbita en la base de datos tal como se muestra

![Reservas de órbitas de prueba en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Resumen

Call Parkometer es una herramienta de línea de comandos que proporciona información detallada sobre el servidor de estacionamiento de llamadas.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Descripción

DBAnalyze es una herramienta de línea de comandos que permite a los administradores recopilar informes de análisis sobre las bases de datos de Skype empresarial Server 2015. DBAnalyze tiene los modos siguientes: diagnóstico, datos de usuario, conferencia, MCU y fragmentación de disco:

- **Modo de diagnóstico** Crea un informe que incluye información sobre las tablas (número de registros, fragmentación, tamaño de datos y tamaño del índice). tamaño de los archivos de registro y datos, el último tiempo de copia de seguridad, la distribución de contactos entre servidores que ejecutan Microsoft Office Communications Server, el número promedio de permisos, contactos, contenedores, suscripciones, publicaciones, puntos de conexión por usuario, los usuarios alojados incorrectamente, los usuarios que no se pueden enrutar, el número medio de conferencias organizadas y la versión de la base de datos.

    > [!NOTE]
    > La ejecución en modo de diagnóstico puede afectar al rendimiento del servidor.

- **Modo de datos de usuario** Notifica los datos de contacto, contenedor, suscripción, publicación, permisos y grupo de contactos de un usuario específico o de los usuarios que tienen ese usuario en sus listas de contactos y permisos. Este modo también proporciona datos de resumen para conferencias que un usuario organice o a las que esté invitado.

- **Modo de conferencia** Informa de datos detallados para una conferencia determinada, incluidos todos los detalles de tiempo de programación de la Conferencia, la lista de invitados, la lista de tipos de medios permitidos para la Conferencia, los MCU activos (unidades de control multipunto), la lista de participantes activos y el estado de señalización de cada participante.

- **Descodificar el identificador** de la reunión Descodifica un identificador de reunión de red de telefonía pública conmutada (RTC) especificado por el modificador **/pstnid** , pero no se conecta al back-end para obtener información detallada.

- **Resolver Conferencia** Descodifica un identificador de reunión RTC especificado por el modificador **/pstnid** y muestra información sobre la Conferencia indicada por el identificador.

- **Modo MCU** Informa de la identificación, el tipo de medio, la URL, el estado de latido, la carga de la Conferencia y la carga de participantes de cada MCU de la agrupación.

- **Modo de fragmentación de disco** Muestra el estado de fragmentación de todos los discos.

Esta herramienta puede utilizarse para diagnosticar diferentes problemas o para ayudar a los administradores con la planificación de capacidad. Por ejemplo, si la mayoría de los usuarios alojados en el servidor A eligen a usuarios alojados en el servidor B como sus contactos, el administrador puede mover los usuarios del servidor A al servidor B para reducir el tráfico entre servidores.

### <a name="output"></a>Salida

Esta herramienta genera informes predefinidos sobre la base de datos de Skype empresarial Server 2015. **Ruta de acceso**: %Archivos de programa%\Skype Empresarial Server 2015\Reskit

### <a name="purpose"></a>Finalidad

Para instalar Dbanalyze.exe, copie el archivo en una carpeta local y, a continuación, ejecute la herramienta. Para usar la herramienta, ejecute el comando siguiente desde la línea de comandos. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`A continuación se muestran las descripciones de las opciones de la línea de comandos.

![Opciones de la línea de comandos para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Requisitos

 **Equipo informático** DBAnalyze solo se puede ejecutar desde un equipo unido a un dominio que tenga instalado Skype empresarial Server 2015.

 **Red** El equipo debe ser capaz de conectarse a la base de datos back-end.

 **Software** Los componentes del software Skype empresarial Server 2015 deben instalarse antes de ejecutar DBAnalyze.

 **Usuarios** En la tabla siguiente se muestran los administradores que tienen los permisos necesarios para acceder a bases de datos de Skype empresarial Server 2015.

![Tabla de permisos para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Para el modo **/report:disk** se necesita una cuenta de administrador local.

### <a name="examples"></a>Ejemplos

A continuación se muestran varios ejemplos de comandos de Dbanalyze.exe válidos:

```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Resumen

DBAnalyzer proporciona a los administradores una forma rápida y sencilla de analizar bases de datos de Skype empresarial Server 2015.

## <a name="import-storage-service-data"></a>Import Storage Service Data (Importación de datos del servicio de almacenamiento)
<a name="Issd"> </a>

La herramienta de kit de recursos ImportStorageServiceData permite reimportar datos de colas y puntos de conexión que hayan sido vaciados del servicio de almacenamiento (LYSS) de nuevo en el servicio de almacenamiento.

### <a name="description"></a>Descripción

Los datos del servicio de almacenamiento pueden haber sido vaciados de forma automática (periódica) según el estado del elemento de cola o el tamaño de la base de datos. Puede haber ocurrido debido a la invocación manual del cmdlet de la conmutación por error del grupo de servidores o por el cmdlet StorageServiceFullFlush (invocado por el cmdlet de conmutación por error del grupo de servidores). Tenga en cuenta que, idealmente, los datos no se volverán a importar si cualquiera de los servidores de aplicaciones para el usuario del servicio de almacenamiento (LYSS) se encuentra por encima del nivel normal, ya que, por lo tanto, es probable que se vuelvan a exportar más datos. Además, los problemas que podrían haber contribuido a errores que provocaban el aumento de la cola del servicio de almacenamiento (por ejemplo, errores de puntos de conexión de Exchange, problemas de red u otros problemas).

 **Escenario 1:** durante la conmutación por error del grupo de servidores, los archivos pueden vaciarse del servicio de almacenamiento para cada front-end. Después de completar la conmutación por error, debe ejecutarse la herramienta para volver a importar los datos.

 **Escenario 2:** los datos se vacían automáticamente todos los días o cuando el tamaño de la base de datos del servicio de almacenamiento supera determinados umbrales (por ejemplo, 60 %, 80 %, 90 %). El administrador debe volver a importar de forma periódica los datos que hayan sido vaciados de forma automática. En la situación anterior, si no se ha implementado el paquete SCOM de supervisión, hay eventos para el servicio de almacenamiento de Skype empresarial Server relacionados con los datos que se han vaciado del servicio de almacenamiento. Los id. de evento son 32075 (se ha iniciado una operación de vaciado completo), 32076 (se ha completado el vaciado completo), 32082 (se ha iniciado el vaciado de nivel de mantenimiento), 32083 (se ha completado el vaciado de nivel de mantenimiento) y 32089 (se ha producido un vaciado porque se ha llenado la base de datos). Estos identificadores de evento se corresponden con la versión RTM. Cuando un administrador ve estos eventos, significa que hay archivos que se han vaciado. Estos datos deberían importarse rutinariamente con esta herramienta, por ejemplo, una vez por semana.

En el caso de la versión de servicio en línea, si se ha implementado el paquete SCOM para la supervisión de estado de Skype empresarial Server, hay nuevas alertas que se pueden generar y que piden al administrador que vuelva a importar los datos vaciados en el servicio de almacenamiento. Existirá un evento correspondiente en el registro de eventos del servidor front-end que haya activado la alerta. El evento ofrecerá una descripción de la ruta de acceso principal donde se encuentran los archivos de los datos vaciados, así como el número de archivos que cumplen con los criterios de alerta. Los criterios de alerta es que haya X o más archivos en la ruta de acceso primaria con un mínimo de Y días (donde X e Y están predefinidos en el servicio de almacenamiento, pero pueden reemplazarse si se cambia el archivo APPCONFIG). A continuación se muestran dos ejemplos de eventos que pueden activar la alerta de estado, cuya diferencia es la ruta de acceso primaria. Una posibilidad se encuentra en el recurso compartido de archivos del servicio web, mientras que la otra es el directorio de datos de aplicación local de cada front-end (por ejemplo, c:\ProgramData\Microsoft\Skype Empresarial Server 2015\StorageService ). A continuación, el administrador ejecutará esta herramienta de kit de recursos.

Esta herramienta aumentará la carga de CPU y de E/S en el front-end donde se ejecute, así como en otros front-end, si los datos no son propiedad del front-end donde se ejecuta la herramienta. Se recomienda ejecutar esta herramienta cuando los front-end no estén sometidos a cargas elevadas de CPU y de E/S (por ejemplo, en horas de poca actividad). En segundo lugar, esta herramienta puede tardar entre 2 y 3 minutos para importar un archivo de datos. Esto debe tenerse en cuenta al calcular el tiempo de ejecución de la aplicación. El archivo de registro detallado generado por la herramienta aparecerá de forma predeterminada en el almacén de archivos. Elimínelo si no se detectan errores, ya que el tamaño del archivo de registro puede ser de varias decenas de MB o más.

![Eventos de ejemplo del registro de eventos del servidor de almacenamiento.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Requisitos

Instale las herramientas del kit de recursos de Skype empresarial Server 2015. La herramienta se ejecuta en máquinas Unidas al dominio donde está instalado Skype empresarial Server y el shell de administración de Skype empresarial. La herramienta usa un cmdlet del shell de administración para identificar todos los servidores front-end del grupo. En segundo lugar, la herramienta debe ejecutarse desde un equipo del grupo en el que está instalada la base de datos **RtcLocal** . Esta base de datos la usa la herramienta para recuperar la ubicación del recurso compartido de archivos WebService para el grupo. Además, antes de usar la herramienta, cada servidor front-end debe habilitar la comunicación remota de Windows PowerShell con **enable-PSRemoting** en cada servidor front-end, así como en el equipo desde el que se ejecuta la herramienta. De lo contrario, los comandos remotos de Windows PowerShell de esta herramienta producirán errores. La comunicación remota de Windows PowerShell puede desactivarse en todos los servidores front-end del grupo después de que haya terminado. Por último, la cuenta o credencial que invoca la herramienta debe tener permiso de lectura y escritura para el recurso compartido de archivos WebService para el grupo en el que están ejecutando esta herramienta. En caso contrario, la herramienta generará errores de permisos de e/s.

> [!NOTE]
> En Windows Server 2012, el servicio remoto de Windows PowerShell está habilitado de forma predeterminada, pero no en el sistema operativo Windows Server 2008.

### <a name="examples"></a>Ejemplos

```
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
```

## <a name="lcssync"></a>LCSSync
<a name="LCSSync"> </a>

La herramienta LCSSync ayuda a implementar el software de comunicaciones de Skype empresarial Server 2015 en un entorno de varios bosques. Esta herramienta se usa para sincronizar los usuarios y grupos de diferentes bosques de usuarios como un objeto de contacto de los servicios de dominio de Active Directory con un bosque central en el que está instalado Skype empresarial Server 2015.

### <a name="description"></a>Descripción

 LCSSync usa los objetos de contacto de los servicios de dominio de Active Directory sincronizados en el bosque central para habilitar los usuarios de Skype empresarial Server. Para proporcionar un inicio de sesión único, la cuenta de usuario principal debe estar asignada al objeto de contacto de los servicios de dominio de Active Directory en el bosque central de Skype empresarial Server 2015. Esta herramienta ayuda a realizar esa asignación. Esta herramienta proporciona plantillas para crear agentes de administración en Microsoft Identity Integration Server.

### <a name="summary"></a>Resumen

La herramienta LCSSync ayuda a implementar Skype empresarial Server 2015 en un entorno de varios bosques.

## <a name="lookup-user-console"></a>Lookup User Console (Consola de búsqueda de usuario)
<a name="LUC"> </a>

La herramienta LookupUserConsole muestra información de enrutamiento de Skype empresarial interna sobre usuarios específicos. Esta información puede ser útil para que el personal de soporte de Microsoft pueda diagnosticar problemas de implementación y enrutamiento.

### <a name="description"></a>Descripción

 La ejecución de LookupUserConsole. exe abrirá un símbolo del sistema que acepta direcciones SIP e intenta mostrar la información de enrutamiento de Skype empresarial interna relacionada. Escriba **exit** para salir de la herramienta LookupUserConsole.

### <a name="requirements"></a>Requisitos

Instale el kit de recursos de Skype empresarial Server 2015. La herramienta se ejecuta en máquinas Unidas al dominio donde está instalado Skype empresarial Server.

### <a name="examples"></a>Ejemplos

C:\Archivos de Files\Skype para Business Server 2015 \ reskit\>LookupUserConsole. exe

```
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
```

## <a name="msturnping"></a>MsTurnPing
<a name="MsTurnPing"> </a>

La herramienta MSTurnPing permite al administrador del software de comunicaciones Skype empresarial Server 2015 comprobar el estado de los servidores que ejecutan el perímetro de audio/vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan los servicios de directiva de ancho de banda de la topología.

### <a name="description"></a>Descripción

La herramienta MSTurnPing permite al administrador del software de comunicaciones Skype empresarial Server 2015 comprobar el estado de los servidores que ejecutan el perímetro de audio/vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan los servicios de directiva de ancho de banda de la topología.

La herramienta permite a los administradores realizar las pruebas siguientes:

1. Prueba de servidor perimetral de A/V: la herramienta realiza las siguientes pruebas contra todos los servidores perimetrales de A/V en la topología:

   - Comprobar que el servicio de autenticación de audio y vídeo de Skype empresarial Server se ha iniciado y puede emitir las credenciales correctas.

   - Comprobando que el servicio perimetral de audio/vídeo de Skype empresarial Server se ha iniciado y puede asignar los recursos en el borde externo correctamente.

2. Prueba del servicio de directiva de ancho de banda: la herramienta realiza las pruebas siguientes contra todos los servidores que ejecutan los servicios de directiva de ancho de banda en la topología:

   - Comprobar que el servicio de directivas de ancho de banda (autenticación) de Skype empresarial Server se ha iniciado y puede emitir las credenciales correctas.

   - Comprobar que el servicio de directivas de ancho de banda (principal) de Skype empresarial Server está iniciado y puede realizar la comprobación de ancho de banda correctamente.

Esta herramienta debe ejecutarse en un equipo que forme parte de la topología y que tenga instalado el almacén local. 

### <a name="output"></a>Salida

La herramienta genera los resultados de todas las operaciones.

- Si se ejecuta la prueba **AudioVideoEdgeServer**, los resultados de la herramienta son los siguientes:

  - Los resultados de prueba de los equipos que proporcionan el servicio de autenticación de audio y vídeo de Skype empresarial Server 2015 en la topología

  - Los resultados de prueba de los equipos que proporcionan el servicio perimetral de audio/vídeo de Skype empresarial Server 2015 en la topología

- Si se ejecuta la prueba **BandwidthPolicyServer**, los resultados de la herramienta son los siguientes:

  - Los resultados de prueba de los equipos que proporcionan el servicio de directivas de ancho de banda 2015 de Skype empresarial Server (autenticación) en la topología

  - Los resultados de prueba de los equipos que proporcionan el servicio de directivas de ancho de banda 2015 de Skype empresarial Server en la topología

### <a name="requirements"></a>Requisitos

- Esta herramienta debe ejecutarse en un equipo que se encuentre en la topología y que tenga el almacén local.

- La herramienta debe ejecutarse como un administrador con acceso al almacén local.

### <a name="examples"></a>Ejemplos

A continuación se muestra un ejemplo de la entrada de la herramienta.

```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Resumen

Esta herramienta puede ser un valioso recurso a los administradores de Skype empresarial Server 2015 que deseen comprobar el estado de los servidores que ejecutan los servicios de directivas de ancho de banda y audio/vídeo.

## <a name="network-configuration-viewer"></a>Network Configuration Viewer (Visor de configuración de red
<a name="NCV"> </a>

El visor de software de comunicaciones de Skype empresarial Server 2015 puede usar el visor de configuración de red para poder ver la topología de red de control de admisión de llamadas (CAC) para una empresa que se suministra para permitir sesiones de comunicación en tiempo real, como llamadas de voz o videollamadas basadas en la capacidad de ancho de banda especificada. Los administradores de Skype empresarial Server 2015 definen directivas CAC, que exigen los servicios de directivas de ancho de banda que se instalan con Skype empresarial Server 2015.

### <a name="description"></a>Descripción

El visor de configuración de red (NetworkConfigurationViewer.exe) permite a los administradores realizar las tareas siguientes:

- Cargue y vea la topología de red de CAC desde una implementación de Skype empresarial Server 2015 en un formato gráfico.

- Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directiva de ancho de banda en un formato gráfico.

- Guardar y almacenar la topología de red de CAC en formato XML en el disco.

- Guardar y almacenar el diagrama de topología de red de CAC en formato JP o BMP.

- Ver los datos de configuración de la topología de red de CAC.

- Ver la topología de red de CAC en estilo de vista de árbol.

- Definir conectores personalizados para vínculos de topología de red de CAC (por ejemplo, vínculos de sitio a región, de región a región y de sitio a sitio).

- Ver información de sitio de topología de red de CAC, información de región y directivas de ancho de banda y vínculos de red proporcionados.

### <a name="purpose"></a>Finalidad

Ver vínculos de topología de red de CAC de empresa en una interfaz gráfica.

### <a name="examples"></a>Ejemplos

 **Cargar y ver la topología de red CAC de una implementación de Skype empresarial server 2015 en un formato gráfico**: Skype empresarial Server 2015 los administradores pueden cargar y **ver la configuración** de topología de red de CAC en cualquier equipo con Skype empresarial Server 2015, como se muestra en la siguiente ilustración. La herramienta no descarga ni visualiza dicha configuración cuando se implementa en un equipo que no tiene conectividad con el almacén de configuración de Skype empresarial Server 2015.

![Descargar la configuración de red.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Cargar y ver la topología de red de CAC desde un archivo de registro de servidor de directivas de ancho de banda en un formato gráfico:** Los servidores de directivas de ancho de banda de Skype empresarial Server 2015 guardan la topología de red CAC como parte del mecanismo de registro en la ubicación de uso compartido de archivos de Skype empresarial Server 2015. Los administradores de Skype empresarial Server 2015 pueden ver un archivo con formato gráfico con la opción **abrir red** como se muestra a continuación.

![Abrir un archivo de registro de servidor de directiva de ancho de banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Guarde y almacene la topología de red de CAC en formato XML en el disco: los administradores de Skype empresarial Server 2015 pueden guardar el archivo de configuración de topología de red CAC en formato XML con la opción **guardar una copia de configuración de red** , tal como se muestra a continuación. El archivo de configuración guardado puede utilizarse para ver una representación gráfica en un entorno sin conexión.

![Guardar la configuración de red como archivo XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Guardar y almacenar el diagrama de topología de red CAC en formato JPG o BMP: Skype empresarial Server 2015 los administradores pueden guardar la configuración de topología de red CAC en un formato gráfico (formatos de archivo JPG y BMP) con la opción **guardar el diagrama de configuración de red como imagen** , como se muestra a continuación.

![Guardar la configuración de red como imagen.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Ver datos de configuración de topología de red CAC:</strong> Los administradores de Skype empresarial Server 2015 pueden ver datos de configuración de red relacionados, como regiones de red, sitios de red, perfiles de ancho de banda y direcciones IP de subred de sitio en formato de texto, tal y como se muestra a continuación.

![Ver los datos de configuración de red.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Ver la topología de red CAC en un estilo de vista de árbol:** Los administradores de Skype empresarial Server 2015 pueden ver los datos de configuración de red relacionados en un estilo de vista de árbol gráfico mediante el panel de control en el lado izquierdo de la ventana de herramientas, como se muestra a continuación.

![Ver los datos de configuración de red en vista de árbol.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Defina conectores personalizados para los vínculos de topología de red CAC (como vínculos de sitio a región, de región a región y de sitio a sitio):** Los administradores de Skype empresarial Server 2015 pueden definir conectores gráficos personalizados para los vínculos WAN de configuración de red CAC con la opción configuración tal como se muestra a continuación. Esto ayuda a diferenciar entre diferentes tipos de vínculos de red proporcionados en la configuración de red.

![Herramientas](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Ver la información del sitio de la topología CAC, la información de la región y las directivas de ancho de banda aprovisionado:** Los administradores de Skype empresarial Server 2015 pueden ver la información de la región de red CAC, la información del sitio y la información de aprovisionamiento de ancho de banda de CAC mediante las opciones que se muestran a continuación. (Por ejemplo, haga clic en **información** en una región de red o un objeto de sitio de red).

![Definir los conectores personalizados para su red.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Resumen

Esta herramienta puede ser un valioso recurso a los administradores de Skype empresarial Server 2015 que desean ver la topología de red CAC para su implementación en un formato gráfico.

## <a name="response-group-agent-live"></a>Response Group Agent Live (Información en vivo del agente del grupo de respuesta)
<a name="RGAL"> </a>

La aplicación de grupo de respuesta permite a los agentes acceder en tiempo real a información útil mediante el servicio web integrado. Desafortunadamente, no hay disponible una vista gráfica de estos datos fuera de la aplicación. La herramienta del kit de recursos del agente de grupo de respuesta soluciona este problema proporcionando una forma sencilla y gráfica para acceder a esta información, mejorada con la información del software de comunicaciones de Skype empresarial en tiempo real, como la presencia de otros agentes.

### <a name="description"></a>Descripción

Response Group Agent Live es una aplicación para Windows que proporciona funciones de inicio y cierre de sesión, así como determinada información en tiempo real (como pertenencia a grupo y número actual de llamadas) a los agentes del grupo de respuesta. Está pensado para ser una versión mejorada de la página grupos de agentes (accesible desde Skype empresarial.

### <a name="purpose"></a>Finalidad

La aplicación de grupo de respuesta envía las llamadas entrantes a una cola y, a continuación, las redirige a grupos de agentes. Para poder tomar decisiones fundamentadas sobre las llamadas que deben atenderse, los agentes pueden acceder a información en tiempo real sobre sus grupos de agentes, como los agentes disponibles y el número de llamadas que espera en cada cola. Esta información, inicialmente accesible solo mediante el servicio de grupo de respuesta, es facilitada de forma intuitiva por la herramienta Response Group Agent Live.

#### <a name="features"></a>Características

La herramienta agente de grupo de respuesta está integrada en el servicio de grupo de respuesta y el SDK de Skype empresarial 2015. Proporciona a los agentes de grupo de respuesta la información y las funciones disponibles del servicio de grupo de respuesta (como pertenencia a grupo, presencia de otros agentes y número de llamadas en espera).

En la ilustración siguiente se muestra la interfaz principal de la herramienta Response Group Agent Live.

![La herramienta Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Las tres características principales que aparecen a continuación están disponibles para los agentes en Response Group Agent Live:

- **Iniciar y cerrar sesión:** Al contrario que la página de grupos de agentes (accesible desde Skype empresarial Server 2015), el agente de grupo de respuesta permite que solo los agentes inicien sesión o salgan de todos los grupos de agentes a la vez. Esta aplicación proporciona tres formas rápidas para que los agentes inicien sesión o salgan:

  - Hacer clic en los botones de inicio y cierre de sesión (verde y rojo) en la aplicación.

  - Hacer clic en el icono de la bandeja del sistema y seleccionar iniciar sesión o cerrar sesión.

  - Usar los métodos abreviados de teclado configurables.

- **Pertenencia a grupos:** Cuando se selecciona un grupo de agentes, el agente de grupo de respuesta muestra la lista de agentes en este grupo en el panel derecho. Si Skype empresarial Server 2015 se ejecuta en el mismo equipo que esta aplicación, la información de presencia y la tarjeta de contacto se muestran en el grupo de respuesta Agent Live. Los agentes pueden enviar un mensaje instantáneo o llamar a otros agentes directamente desde allí.

- **Estadísticas en tiempo real:** Response Group Agent Live proporciona estadísticas en tiempo real para todos los grupos de agentes. La frecuencia de actualización es de un minuto. Cuando un grupo de respuesta responde a una llamada, se añade un indicador visual junto al nombre del grupo con el número actual de llamadas en cola. Al detener el puntero sobre un grupo, también se muestra el tiempo de espera más largo.

### <a name="requirements"></a>Requisitos

Response Group Agent Live requiere .NET Framework 4.0. Además, para aprovechar las características de presencia y de tarjeta de contacto, Skype empresarial debe instalarse de forma local (y estar ejecutándose).

#### <a name="configuration"></a>Configuración

Response Group Agent Live puede personalizarse según preferencias individuales mediante el cuadro de diálogo de opciones de la aplicación. Además, el administrador puede definir la dirección de host predeterminada al editar directamente la propiedad defaultHostAddress del archivo RGAgentLive.exe.config.

En la ilustración siguiente se muestra el cuadro de diálogo de opciones que los agentes pueden usar para configurar la dirección de host y las teclas de método abreviado. Para acceder a este cuadro de diálogo, haga clic en el botón Opciones de la parte superior derecha de la interfaz principal.

![El cuadro de diálogo de las opciones de Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Las tres opciones siguientes pueden personalizarse en la configuración de Response Group Agent Live:

- Dirección de host: suele ser el FQDN del grupo de servidores web que pertenece al grupo de usuarios domésticos del agente. La dirección exacta del servicio de grupo de respuesta se obtiene automáticamente en segundo plano a partir de esta información (al añadir la ruta de acceso correcta después del host).

- Métodos abreviados de teclado: los métodos abreviados de teclado exactos para iniciar/cerrar sesión se pueden personalizar. La única limitación es que ambos métodos abreviados deben contener la tecla "logotipo de Windows" (además de al menos otra tecla).

- Iniciar con Windows: la aplicación puede configurarse para iniciarse automáticamente con Windows.

### <a name="examples"></a>Ejemplos

En la ilustración siguiente se muestra cómo llamar o enviar un mensaje instantáneo a otro agente; para ello es necesario hacer clic con el botón derecho en el contacto del panel derecho.

![Hacer una llamada o enviar un mensaje instantáneo.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

En la ilustración siguiente aparece cómo Response Group Agent Live muestra el número de llamadas en la cola y el tiempo de espera más largo de todas las llamadas entrantes.

![Ver información de cola.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Resumen

Inicio y cierre de sesión rápidos, pertenencia a grupos y estadísticas básicas en tiempo real son algunas de las características interesantes del agente del grupo de respuesta que solo están disponibles fuera de la aplicación del servicio de grupo de respuesta. Con la herramienta del kit de recursos del agente de grupo de respuesta, los administradores de Skype empresarial Server 2015 pueden proporcionar a sus agentes una aplicación de Windows que les permita realizar tareas de forma más rápida y gráfica.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (la activación de características de extensión secundaria) es una herramienta de línea de comandos que permite a los administradores de software de comunicaciones de Skype empresarial Server 2015 y a los agentes del Departamento de soporte técnico configurar el timbre delegado, el desvío de llamadas, las llamadas simultáneas configuración de llamada de equipo y recogida de llamada grupal en nombre de un usuario de Skype empresarial Server 2015. La herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular. La herramienta SEFAUtil permite al administrador habilitar/deshabilitar/modificar el desvío de llamadas o el timbre simultáneo en nombre del usuario. El administrador puede especificar el destino (en forma de URI del SIP) o usar un destino ya publicado por el usuario. Esta herramienta también permite a los administradores agregar o quitar delegados o miembros del grupo de llamada de equipo en nombre del usuario. Esta herramienta está integrada en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3,0 y requiere que los administradores creen una aplicación de confianza en el almacén de administración central para SEFAUtil.

SEFAUtil (la activación de características de extensión secundaria) permite a los administradores y los agentes del Departamento de soporte técnico de Skype empresarial Server 2015 configurar las llamadas de delegación, el desvío de llamadas, las llamadas simultáneas, la configuración de llamada de equipo y la recogida de llamadas grupales en nombre de un Skype para usuarios de Business Server 2015. Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se haya publicado para un usuario concreto.

### <a name="description"></a>Descripción

La versión actual de SEFAUtil es tan solo una herramienta de línea de comandos; no dispone de una interfaz gráfica de usuario. Esta herramienta se basa en la API administrada de Microsoft Unified Communications (UCMA) 3,0. Las características de esta herramienta permiten a los administradores y agentes del departamento de soporte técnico realizar las acciones siguientes:

- Ver todas las opciones de configuración de enrutamiento de llamadas para un usuario (incluidos el desvío de llamadas, la delegación, llamadas simultáneas, llamadas de equipo y respuestas de llamada de grupo)

- Habilitar/deshabilitar/modificar la configuración del desvío de llamadas (incluidos el destino y el temporizador de llamadas sin respuesta)

- Habilitar/deshabilitar/modificar las configuraciones inmediatas de desvío de llamadas

- Habilitar/deshabilitar/modificar la configuración de delegación

- Habilitar/deshabilitar/modificar la configuración de grupo de llamada de equipo

    > [!NOTE]
    > Novedades de la herramienta SEFAUtil de Skype empresarial Server 2015

- Habilitar/deshabilitar/modificar la configuración de llamadas simultáneas (incluido el destino)

    > [!NOTE]
    > Novedades de la herramienta SEFAUtil de Skype empresarial Server 2015

- Habilitar/deshabilitar/modificar la configuración de respuesta a llamada grupal

    > [!CAUTION]
    > Novedades de la herramienta SEFAUtil de Skype empresarial Server 2015

Esta herramienta tiene las limitaciones siguientes:

- Compatible solo para usuarios alojados en un grupo de servidores de Skype empresarial

- No admite la edición en masa de las opciones de configuración de enrutamiento de llamadas para varios usuarios

### <a name="output"></a>Salida

La versión actual de esta herramienta solo ofrece resultados en la ventana del símbolo del sistema. Para obtener más información, consulte la sección Ejemplos más adelante en este documento.

### <a name="purpose"></a>Finalidad

A continuación se describen algunos de los escenarios donde puede utilizarse esta herramienta:

- Bob es ejecutivo y se ha movido a la telefonía de Skype empresarial Server. Ha configurado la delegación en su sistema PBX existente. Como parte del paso a Skype empresarial Server 2015, el administrador puede configurar el enrutamiento de Bob para que refleje la configuración de delegación preexistente.

- Alicia está de viaje y se da cuenta de que está esperando una llamada importante de uno de sus clientes. Sin embargo, está en un hotel y no tiene acceso a un PC. Entonces, llama al departamento de soporte técnico y solicita que se desvíen a su número de teléfono móvil todas las llamadas realizadas a su número de trabajo. El personal de soporte técnico puede realizar la configuración en su nombre.

- Las llamadas de Juan a su número del trabajo van a su buzón de voz móvil siempre que esté en el trabajo. sin embargo, parecen funcionar correctamente en la mayoría de las demás ubicaciones. El técnico del servicio de asistencia al usuario puede ver la configuración de enrutamiento de Juan y descubre que José tiene configurada la opción de llamada simultánea en su teléfono móvil. El técnico pregunta a José sobre la cobertura móvil en su oficina y puede determinar que la regla de timbres simultáneos es lo que hace que las llamadas vayan al buzón de voz de su teléfono móvil de José cuando su cobertura de red es deficiente.

- Mike es un nuevo empleado de Contoso y se une a un nuevo equipo en el que todos los miembros están configurados para la llamada de equipo, cuando está habilitado para Skype empresarial Server 2015, el administrador puede establecer la configuración del grupo de llamada de equipo para incluir a todos los nuevos miembros del equipo. , además, el administrador agrega Mike como miembro del grupo de llamada de equipo para cada uno de los miembros de su equipo.

- Uno de los procedimientos de atención al cliente en el departamento de recursos humanos de Contoso es proporcionar personal de servicio para todos los autores de llamadas desde la primera llamada. Debido a que todos los miembros del departamento se sientan muy cerca unos de otros, tener todos los teléfonos sonando de forma simultánea con llamadas de equipo es muy molesto para el equipo. Para ofrecer el mejor servicio sin interrumpir a los miembros del equipo, el administrador de Skype empresarial Server 2015 aprovecha la capacidad de recogida de llamadas grupales. El administrador agrega a todos los miembros del departamento al número de respuesta. Cuando Sandra no está en su escritorio, Jorge se da cuenta de que suena el teléfono de Sandra y responde a la llamada desde su escritorio.

### <a name="requirements"></a>Requisitos

La herramienta SEFAUtil solo puede ejecutarse desde un equipo que forme parte de un grupo de aplicaciones de confianza. UCMA 3.0 debe instalarse en dicho equipo. Para ejecutar la herramienta es necesario crear un id. de aplicación de SEFAUtil en el grupo.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Crear una nueva aplicación de confianza para la herramienta SEFAUtil

1. La herramienta SEFAUTil solo puede ejecutarse en un equipo que pertenezca a un grupo de aplicaciones de confianza. Si es necesario, se puede Agregar un grupo como un nuevo grupo de aplicaciones de confianza a través del shell de administración de Skype empresarial Server con el siguiente cmdlet:

   ```PowerShell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > UCMA 3.0 debe estar instalado en todos los equipos que se utilicen para ejecutar la herramienta SEFAUtil.

2. Es necesario definir una aplicación de confianza en la topología para la herramienta SEFAUtil. Para definir SEFAUtil como una nueva aplicación de confianza, use el shell de administración de Skype empresarial Server y ejecute el siguiente cmdlet:

   ```PowerShell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > Si fuera necesario, puede utilizarse un puerto distinto.
    
    > [!NOTE]
    > FQDN del Grupo: el nombre completo del servidor o grupo de servidores que va a hospedar la aplicación de SEFAUtil (generalmente un servidor front-end de Skype empresarial > o grupo).
    > FQDN del registrador de grupos: el FQDN del servidor front-end de Skype empresarial o del grupo de servidores asociado a este grupo de aplicaciones.
    > Sitio de Grupo: el identificador de sitio del sitio en el que se aloja este grupo.

3. Es necesario habilitar los cambios de topología. La habilitación de los cambios de topología se puede realizar mediante el shell de administración de Skype empresarial Server ejecutando el siguiente cmdlet:

   ```PowerShell
   Enable-CsToplogy
   ```

4. Si es necesario, instale las herramientas del kit de recursos de Skype empresarial Server 2015 en el servidor que se usará para ejecutar la herramienta SEFAUtil (el servidor debe formar parte de un grupo de aplicaciones de confianza).

5. Compruebe si SEFAUtil se ejecuta correctamente. Para ello, ejecute la herramienta desde un símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación. De forma predeterminada, la herramienta se ubicará en: ". ..\Archivos de Files\Skype para empresas Server 2015 \ reskit". Para mostrar la configuración de desvío de llamadas de un usuario, utilice el comando siguiente:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    Se mostrará la configuración de desvío de llamadas del usuario.

#### <a name="group-call-pickup"></a>Respuesta de llamadas grupales

La recogida de llamadas grupales requiere configuración adicional en Skype empresarial Server 2015 para que pueda habilitarse por completo. Antes de asignar grupos de respuesta a los usuarios, consulte los pasos de planificación e implementación de esta función en la documentación del producto de respuesta de llamadas grupales.

### <a name="examples"></a>Ejemplos

#### <a name="display-current-call-handling-settings"></a>Mostrar la configuración administración de llamadas actual

El comando siguiente muestra la administración de llamadas para el usuario.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> En este ejemplo se usa el modificador **/Server** para especificar el servidor de Skype empresarial al que se conectará.

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Establecer el desvío de llamadas/destino sin respuesta

En este ejemplo se establece el desvío de llamadas/destino sin respuesta y la demora de timbre. Aquí no se proporciona el modificador/Server; SEFAUtil intenta descubrir la detección automática de Skype empresarial Server 2015.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>Habilitar desvío de llamadas inmediatamente

En este ejemplo se habilita el desvío de llamadas inmediatamente a otro usuario.

```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>Deshabilitar desvío de llamadas inmediatamente

En este ejemplo se deshabilita automáticamente el desvío de llamadas.

```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Agregar un usuario como delegado y configurar las llamadas simultáneas de delegados

En este ejemplo se agrega un usuario como delegado y se configuran las llamadas simultáneas de delegados.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Cambiar la regla de llamadas simultáneas de delegados

En este ejemplo se cambia la regla de llamadas simultáneas configurada en el ejemplo anterior a la regla de demora de timbre.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>Quitar al delegado

En este ejemplo se quita el delegado.

> [!NOTE]
> Al quitar el último delegado, se deshabilita automáticamente la llamada a delegados.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Agregar un delegado y configurar la regla de desvío de llamadas a delegados

En este ejemplo se agrega un delegado y se configura la regla de desvío de llamadas a delegados.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Habilitar las llamadas simultáneas y establecer un número de destino

En este ejemplo se habilitan las llamadas simultáneas y se establece un número de destino de llamadas simultáneas.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Para cambiar el número de destino de las llamadas simultáneas de un usuario que ya tenga habilitadas las llamadas simultáneas, mantenga el comando con el modificador /enablesimulring, ya que en caso contrario no se cambiaría el número de destino.

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Deshabilitar llamadas simultáneas

En este ejemplo se deshabilitan las llamadas simultáneas.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Agregar un miembro para llamada de equipo y configurar las llamadas simultáneas en el grupo de miembros de llamada de equipo

En este ejemplo se agrega un miembro de equipo al grupo de llamada de equipo de un usuario y se habilitan las llamadas simultáneas al grupo de llamada de equipo.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Al agregar a un miembro a un grupo de llamada de equipo de un usuario se cambiará automáticamente a la configuración de llamadas simultáneas de los usuarios para llamar simultáneamente a su grupo de llamada de equipo.

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Quitar a un miembro del grupo de llamada de equipo

En este ejemplo se quita a un miembro del equipo del grupo de llamada de equipo de un usuario.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Si el miembro que va a quitarse es el único miembro del grupo de llamada de equipo, se deshabilitarán automáticamente las llamadas simultáneas al grupo de llamada de equipo.

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Establecer la demora de timbre al grupo de llamada de equipo

En este ejemplo se cambia la configuración de hora de demora de timbre al grupo de llamada de equipo.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>Habilitar llamada de equipo

En este ejemplo se habilita la llamada de equipo para un usuario concreto.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Si el grupo de llamada de equipo del usuario no tiene miembros, la llamada al equipo no se habilitará.

 **Salida**

#### <a name="disable-team-call"></a>Deshabilitar la llamada de equipo

En este ejemplo se deshabilita la llamada de equipo para un usuario concreto.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Habilitar la respuesta de llamadas grupales y asignar un grupo de respuesta a un usuario

En este ejemplo se asigna un grupo de respuesta a un usuario y se habilita la respuesta de llamadas grupales.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **Salida**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>Deshabilitar la respuesta de llamadas grupales

En este ejemplo se deshabilita la respuesta de llamadas grupales para un usuario concreto.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Cuando se deshabilita la respuesta de llamadas grupales para un usuario, no se conserva el número de grupo que se asignó al usuario. Si posteriormente quiere volver a habilitar la respuesta de llamadas grupales para ese usuario, deberá volver a asignar el número de grupo con el modificador /enablegrouppickup.

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Descripción

SYSPrep. PS1 es un script de Windows PowerShell que instalará los siguientes requisitos previos de Skype empresarial Server 2015 en el equipo del sistema operativo Windows Server 2008.

- Microsoft .NET Framework 4.5

- Microsoft SQL Server Express

- Windows Powershell versión 3.0

- Paquete redistribuible de Visual C++ 2010

- Actualizaciones de Internet Information Server

- Windows Identity Foundation

- Archivos principales de Skype empresarial Server 2015

  Aunque el nombre del script es parecido a la herramienta de preparación del sistema de los sistemas operativos Microsoft Windows, en realidad son distintos. Este script solo instalará los requisitos previos necesarios para Skype empresarial Server 2015. Después de instalar estos requisitos previos, puede utilizarse la herramienta SYSPrep de Windows para crear una imagen del servidor.

### <a name="requirements"></a>Requisitos

Antes de ejecutar el script SYSPrep. ps1, debe copiar los archivos necesarios en una carpeta local del equipo del sistema operativo Windows Server 2008 (por ejemplo **, D:\setup)**. Esta carpeta también debe incluir una copia de los archivos de Skype empresarial Server 2015, específicamente **setup. exe.** Los archivos de requisitos previos pueden descargarse desde las ubicaciones siguientes:


| **Requisito previo**                                | **Ubicación**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| Windows Powershell versión 3.0  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| Paquete redistribuible de Visual C++ 2010  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| Actualizaciones de Internet Information Server  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| Setup. exe de Skype empresarial Server 2015  <br/> | Copiar desde los medios de Skype empresarial Server 2015  <br/>                   |

### <a name="parameter"></a>Parámetro

El parámetro **-SetupFolder** toma como argumento la ubicación del directorio de los archivos de requisitos previos

### <a name="examples"></a>Ejemplos

Para ejecutar el script SYSPrep. PS1 e instalar los requisitos previos de Skype empresarial Server 2015, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Unassigned Number Announcements Migration (Migración de anuncios de números sin asignar)
<a name="UNAM"> </a>

La herramienta de migración anuncios de números no asignados permite a un administrador de Skype empresarial Server 2015 mover la configuración de números no asignados que es atendida por la aplicación de presentación de un servidor o grupo de servidores de Skype empresarial de origen a un Servidor o grupo de servidores de Skype empresarial de destino.

### <a name="description"></a>Descripción

La herramienta Unassigned Number Announcements Migration es un script de Windows PowerShell script que mueve la configuración de los números sin asignar de la aplicación del anuncio desde un servidor o grupo de origen a un servidor o grupo distinto.

Al ejecutar el script Unassigned Number Announcements Migration realizará las operaciones siguientes:

1. Mueve todos los archivos de audio utilizados en los anuncios de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen al almacén de archivos del servidor o grupo de destino.

    > [!NOTE]
    > Los archivos de audio se eliminan del grupo de origen una vez que se copian en el grupo de destino.

2. Mueve todos los anuncios de números sin asignar configurados para la aplicación del anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.

3. Reasigna todos los intervalos de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.

Después de ejecutar correctamente el script, todos los intervalos de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen serán atendidos por la misma configuración por el destino o grupo de destino.

### <a name="output"></a>Salida

El script **Move-CsAnnouncementConfiguration** se indica en la ventana del shell de administración de Skype empresarial, desde donde se ejecuta el éxito o el fracaso de la operación de migración.

Si la ejecución de la operación es interrumpida por algún error, los intervalos de números sin asignar que se hayan movido correctamente al destino permanecerán en este de forma operativa, mientras que el resto de intervalos de números sin asignar que aún no hayan sido migrados permanecerán en el origen también de forma operativa. Para completar la migración del resto de la configuración, vuelva a ejecutar el script después de corregir el error.

### <a name="purpose"></a>Finalidad

El script Unassigned Number Announcements Migration puede utilizarse en los tres casos siguientes:

- **Migrar las opciones de configuración a una nueva versión de Skype empresarial Server:** Contoso está en proceso de migrar a Skype empresarial Server 2015 y, como parte del proceso de migración, el administrador de Skype empresarial Server desea mover la configuración de los números no asignados atendida por la aplicación de presentación de la implementación de Lync Server 2013 a la nueva implementación de Skype empresarial Server 2015. Para mover la configuración, el administrador de Skype empresarial Server usa la herramienta de migración anuncios de números no asignados.

- **Reversión de una implementación de Skype empresarial server 2015 a Lync Server 2013:** Debido a los factores inesperados, Contoso tiene que revertir la migración a la nueva implementación de Skype empresarial Server 2015. Para minimizar las interrupciones en el servicio, el administrador de Skype empresarial Server usa la herramienta de migración anuncios de números no asignados para revertir la configuración de la implementación de Skype empresarial Server 2015 a la implementación de Lync Server 2013.

- **Mover datos entre implementaciones:** Contoso está en proceso de reemplazar todos los servidores de un grupo por servidores más nuevos. Su estrategia es implementar un nuevo grupo de servidores de Skype empresarial 2015, mover todos los datos del antiguo al nuevo grupo y, a continuación, descartar el antiguo grupo. Después de implementar el nuevo grupo de servidores, la herramienta Unassigned Number Announcements Migration se utiliza para mover la configuración del grupo anterior al nuevo.

#### <a name="requirements"></a>Requisitos

Estos son los requisitos principales para ejecutar correctamente la herramienta:

1. El script debe ejecutarse desde un equipo que tenga instalado el shell de administración de Skype empresarial Server.

2. La aplicación de anuncios debe implementarse correctamente en los servidores o agrupaciones de Skype empresarial de origen y destino.

#### <a name="move-csannouncementconfiguration-script"></a>Script Move-CsAnnouncementConfiguration

El script Move-CsAnnouncementConfiguration requiere los dos parámetros descritos en la tabla siguiente. 

![Parámetros Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Ejemplos

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Mover la configuración de anuncios de números sin asignar de un grupo de 2013 de Lync Server a un grupo de servidores de Skype empresarial 2015

En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Lync Server 2013) al grupo de destino (Skype empresarial Server 2015).

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Skype empresarial 2015 a un grupo de servidores de Lync 2013

En este ejemplo se mueven los anuncios de números sin asignar de la agrupación de origen (Skype empresarial Server 2015) al grupo de destino (Lync Server 2013).

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf Data
<a name="WebConfData"> </a>

La herramienta de datos Web conf permite a un administrador de software de comunicaciones de Skype empresarial Server 2015 tener más control sobre los datos asociados a las conferencias web del organizador. Los escenarios incluyen la posibilidad de eliminar los datos de la reunión de un usuario específico en función de un criterio de marca de tiempo.

### <a name="description"></a>Descripción

Esta herramienta permite al administrador realizar las tareas siguientes:

1. Buscar todos los datos de conferencias web asociados con un usuario concreto.

2. Eliminar todos los datos de conferencias web asociados con un usuario concreto.

3. Eliminar todos los datos de conferencias web asociados con un usuario concreto anteriores a una fecha concreta

4. Mover todos los datos de conferencias web asociados con un usuario concreto al mover a dicho usuario desde un grupo a otro.

> [!NOTE]
> Las herramientas del kit de recursos para Lync Server 2010 admiten el traslado de todos los datos de conferencias web asociados con un solo usuario cuando este se mueve de un grupo a otro. Dicha funcionalidad ya no se utiliza en favor del parámetro **MoveConferenceData**. Para obtener más información sobre este parámetro, vea el cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .

Esta herramienta elimina únicamente los datos de las reuniones inactivas. Las reuniones activas (o reuniones en sesiones) no se pueden eliminar.

Esta herramienta debe ejecutarse desde un equipo que se encuentre en el mismo grupo que el usuario de destino. El usuario cuyos datos de contenidos de reuniones vayan a ser administrados por esta herramienta ha de ser hospedado en el mismo grupo de usuarios.

### <a name="output"></a>Salida

Esta herramienta informa de los resultados de todas las operaciones:

- Si se realiza una consulta, la herramienta genera una lista de todas las carpetas de datos de reuniones inactivas que tengan al usuario como organizador.

- Si se eliminan datos, la herramienta genera una lista de todas las carpetas de datos de reuniones cuyos datos se eliminarán.

### <a name="requirements"></a>Requisitos

La herramienta ha de ejecutarse en el mismo grupo donde esté hospedado actualmente el organizador.

La herramienta debe ejecutarse con privilegios de administrador con acceso al almacén de archivos de contenido.

### <a name="examples"></a>Ejemplos

En la tabla siguiente se describen los parámetros, algunos de los cuales se han utilizado en los ejemplos.

![Parámetros de herramientas de datos de configuración web.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

En el ejemplo anterior se mostraba el funcionamiento de un comando de consulta. La salida de dicho comando sería una lista de todas las carpetas de contenido de reuniones que serían afectadas por esta herramienta.

```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

En el ejemplo anterior se muestra el comando delete. Este comando elimina todas las carpetas de reuniones inactivas de este usuario.

### <a name="summary"></a>Resumen

Esta herramienta puede ser un recurso útil para administradores que necesiten un control más preciso en los datos de reuniones de conferencias.


