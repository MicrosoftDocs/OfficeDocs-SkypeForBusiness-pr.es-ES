---
title: Documentación de las herramientas del kit de recursos de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: En este tema se describen las herramientas del kit de recursos de Skype empresarial Server 2015, incluido el propósito de cada herramienta y ejemplos de uso. El kit de recursos de Skype empresarial Server 2015 ayuda a simplificar las tareas rutinarias para los administradores de ti que implementan y administran Skype empresarial Server 2015. Por ejemplo, la herramienta de datos Web conf puede usarse para controlar fácilmente los datos cargados por los usuarios durante una reunión en línea. La herramienta SEFAUtil se puede usar para configurar el desvío de llamadas de delegado y responder para los usuarios. Recomendamos a los administradores de ti que usen estas herramientas para administrar de forma más eficaz Skype empresarial Server 2015.
ms.openlocfilehash: 7269d7c82736be8e533a0782548a94d14aafcfb5
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160774"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Documentación de las herramientas del kit de recursos de Skype empresarial Server 2015

En este tema se describen las herramientas del kit de recursos de Skype empresarial Server 2015, incluido el propósito de cada herramienta y ejemplos de uso. El kit de recursos de Skype empresarial Server 2015 ayuda a simplificar las tareas rutinarias para los administradores de ti que implementan y administran Skype empresarial Server 2015. Por ejemplo, la herramienta de **datos Web conf** puede usarse para controlar fácilmente los datos cargados por los usuarios durante una reunión en línea. La herramienta **SEFAUtil** se puede usar para configurar el desvío de llamadas de delegado y responder para los usuarios. Recomendamos a los administradores de ti que usen estas herramientas para administrar de forma más eficaz Skype empresarial Server 2015.

## <a name="installation-of-the-resource-kit-tools"></a>Instalación de las herramientas del kit de recursos

Para instalar el kit de recursos de Skype empresarial Server 2015, descargue [OCSReskit. msi](https://www.microsoft.com/download/details.aspx?id=52631) desde el centro de descarga.

Ejecute **OCSResKit. msi** para realizar una instalación sencilla. El. msi instala todas las herramientas en la siguiente ruta de acceso: **% Program Programa%\skype for Business Server 2015 \ reskit**. Las herramientas que son ejecutables independientes se encuentran en esta carpeta. Las herramientas que también tienen archivos auxiliares están en sus propias subcarpetas.

## <a name="supported-environments"></a>Entornos compatibles

El kit de recursos de Skype empresarial Server 2015 debe instalarse en un servidor que cumpla las especificaciones requeridas para Skype empresarial Server 2015, normalmente uno que se usa para ejecutar Skype empresarial Server 2015.

## <a name="resource-kit-tools-overview"></a>Introducción a las herramientas del kit de recursos

A continuación se muestra una lista de las herramientas que se proporcionan en el kit de recursos de Skype empresarial Server 2015. En las siguientes secciones se describe una descripción de cada herramienta, incluidos los requisitos y el uso de ejemplo.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Monitor del servicio de directiva de ancho de banda](resource-kit-tools.md#bpsm)

- [Analizador de uso de ancho de banda](resource-kit-tools.md#bua)

- [Llamar a Parkometer](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Importar datos del servicio de almacenamiento](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Consola del usuario de búsqueda](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Visor de configuración de red](resource-kit-tools.md#NCV)

- [Response Group Agent Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep. ps1](resource-kit-tools.md#SYSPrep)

- [Número de anuncios no asignados a la migración](resource-kit-tools.md#UNAM)

- [Datos de conf de Web](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

La herramienta de configuración del servicio de libreta de direcciones (ABSConfig) es una herramienta administrativa que ayuda a los administradores a personalizar la configuración del servicio de libreta de direcciones en Skype empresarial Server 2015. Esta herramienta también permite a los administradores de Skype empresarial Server 2015 restaurar la configuración predeterminada del servicio de libreta de direcciones.

### <a name="description"></a>Descripción

ABSConfig es una aplicación de interfaz de usuario gráfica que permite a los administradores configurar los atributos de servicios de dominio de Active Directory relacionados con el servicio de libreta de direcciones.

Los escenarios principales de la herramienta son los siguientes:

- Permitir a los administradores asignar atributos en los servicios de dominio de Active Directory a los atributos de Skype empresarial Server 2015.

- Permitir a los administradores especificar el atributo de servicios de dominio de Active Directory que se va a incluir o excluir en los archivos del servicio de libreta de direcciones.

- Para permitir a los administradores restaurar la configuración predeterminada del servicio de libreta de direcciones.

La herramienta ABSConfig se puede iniciar mediante el archivo ABSConfig. exe. La herramienta se abre en la ficha **configurar atributos** . Esta tabla tiene opciones para asignar atributos de servicios de dominio de Active Directory a los campos de atributo de Skype empresarial Server 2015 y para especificar qué usuarios se deben incluir o excluir en los archivos del servicio de libreta de direcciones basándose en filtros de atributo específicos. También tiene opciones para personalizar el valor del número de teléfono que se incluirá en el archivo de la libreta de direcciones. La opción **Restaurar valores predeterminados** permite a los administradores restaurar la configuración del servicio de libreta de direcciones en los valores predeterminados.

> [!NOTE]
> La reasignación de atributos de AD a distintos nombres de campo OC solo funciona con la descarga del archivo de la libreta de direcciones y no es compatible con la consulta Web de la libreta de direcciones.

### <a name="output"></a>Output

ABSConfig almacena la configuración del servicio de libreta de direcciones en la base de datos.

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Finalidad

ABSConfig proporciona una forma rápida y sencilla de personalizar el servicio de libreta de direcciones de Skype empresarial Server 2015.

### <a name="requirements"></a>Requirements

#### <a name="computer"></a>Equipo

ABSConfig solo puede ejecutarse desde un equipo unido a un dominio que tenga instalado Skype empresarial Server 2015. En el caso de Skype empresarial Server 2015, Enterprise Edition, esta herramienta se puede ejecutar en cualquier servidor front-end que tenga habilitado el servicio de libreta de direcciones durante la instalación.

#### <a name="network"></a>Red

El equipo debe ser capaz de conectarse al grupo de servidores front-end y a la base de datos back-end.

#### <a name="software"></a>Software

Los siguientes componentes de software deben instalarse antes de ejecutar la herramienta ABSConfig:

- Skype Empresarial Server 2015

#### <a name="users"></a>Usuarios

Administradores que tienen los permisos necesarios para actualizar la implementación de Skype empresarial Server 2015.

### <a name="examples"></a>Ejemplos

Para iniciar ABSConfig, escriba **ABSConfig. exe** en un símbolo del sistema. A continuación se muestra la interfaz de usuario de la herramienta ABSConfig.

![La herramienta ABSConfig. exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Resumen

La herramienta ABSConfig proporciona a los administradores una herramienta rápida y fácil de usar para personalizar el servicio de libreta de direcciones de Skype empresarial Server 2015.

## <a name="bandwidth-policy-service-monitor"></a>Monitor del servicio de directiva de ancho de banda
<a name="bpsm"> </a>

La herramienta de supervisión del servicio de directiva de ancho de banda está diseñada para permitir a los administradores ver una lista de las siguientes opciones:

1. Todos los servicios de directiva de ancho de banda de Skype empresarial Server 2015 (autenticación y núcleo) configurados en la topología

2. Las conexiones que realiza cada servicio a otros servicios de directiva de ancho de banda y a los servidores perimetrales.

3. Todos los vínculos configurados en el documento de configuración de red y el uso de ancho de banda en tiempo real tal y como lo indica cada uno de los servicios de directiva de ancho de banda

### <a name="description"></a>Descripción

La herramienta de supervisión del servicio de directiva de ancho de banda se implementa como una aplicación basada en GUI. Los administradores inician la herramienta ejecutando PDPMonUI. exe.

Cuando se inicia la herramienta, intenta descubrir la lista de servicios de directivas de ancho de banda en la topología. Una vez realizada la actualización inicial, el panel de la izquierda de la ventana se rellena con una lista de servicios agrupados por los clústeres a los que pertenecen.

Cuando los administradores seleccionan un servicio de directiva de ancho de banda en particular, el panel de la derecha muestra la información sobre ese servicio en particular. Ese panel también tiene dos pestañas principales que muestran información.

#### <a name="machine-info-tab"></a>Ficha información del equipo

La ficha **información del equipo** muestra los detalles del servicio de directiva de ancho de banda seleccionado y la lista y el estado de todas las conexiones realizadas por el servicio de directiva de ancho de banda seleccionado a otros servicios.

#### <a name="topology-info-tab"></a>Pestaña información de topología

La ficha **información de topología** muestra una lista de todos los vínculos que se configuran en las opciones de configuración de red. Para cada vínculo, se muestra la capacidad de ancho de banda de audio y vídeo. Además, se muestra el ancho de banda utilizado actualmente, tanto en Kbps como en un porcentaje de la capacidad. La herramienta usa código de colores para resaltar los vínculos que tienen un uso similar al de la capacidad, lo que permite a los administradores aislar rápidamente estos vínculos.

> [!NOTE]
>  Si la herramienta de supervisión del servicio de directiva de ancho de banda experimenta errores cuando se conecta a cualquiera de los servicios de directiva de ancho de banda configurados, la información de las fichas información del **equipo** y información de la **topología** no se rellenará. Sin embargo, es posible que la herramienta se conecte inicialmente pero que pierda su conexión al servicio. En estos casos, los administradores pueden ver información obsoleta. Hay una marca de hora de **última actualización** en cada una de las pestañas que permite a los administradores ver cuándo se actualizó por última vez los datos de un servicio de directivas de ancho de banda determinado.

### <a name="output"></a>Output

No hay resultados en la línea de comandos; la salida del programa está contenida en la interfaz gráfica de usuario (GUI) principal.

### <a name="purpose"></a>Finalidad

La finalidad de la herramienta de supervisión del servicio de directiva de ancho de banda es permitir a los administradores ver el estado de cada uno de los servicios de directivas de ancho de banda que se definen en la topología. Además, los administradores pueden ver el uso de ancho de banda en tiempo real para todos los vínculos definidos en el documento de configuración de red.

### <a name="requirements"></a>Requirements

La herramienta de supervisión del servicio de directiva de ancho de banda debe ejecutarse en un equipo que forme parte de la topología de Skype empresarial Server.

### <a name="summary"></a>Resumen

La herramienta de supervisión del servicio de directiva de ancho de banda puede ser un recurso valioso para los administradores, de modo que puedan inspeccionar el estado de todos los servicios de directivas de ancho de banda de la topología y, lo que sea más importante, puedan obtener un uso de ancho de banda en tiempo real para los vínculos que se se define en las opciones de configuración de red.

## <a name="bandwidth-utilization-analyzer"></a>Analizador de uso de ancho de banda
<a name="bua"> </a>

El analizador de uso de ancho de banda es una herramienta que crea informes sobre diversas vistas de consumo de ancho de banda por los puntos de conexión de UC a través de vínculos WAN en la red empresarial. Estos informes se pueden usar para comprender el patrón de consumo de ancho de banda actual y para ayudar a planear la capacidad de ancho de banda.

### <a name="description"></a>Descripción

El analizador de uso de ancho de banda se implementa como una aplicación basada en la interfaz gráfica de usuario. Esta herramienta genera informes específicos para el uso de audio en la red y ayuda a planear la capacidad. También recorre en iteración la capacidad de ancho de banda asignada a varios vínculos.

### <a name="output"></a>Output

El analizador de uso de ancho de banda proporciona gráficos al al de la capacidad de ancho de banda y utilización de audio para todos los vínculos WAN configurados en el sistema.

### <a name="purpose"></a>Finalidad

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

#### <a name="applications"></a>Aplicaciones

El analizador de uso de ancho de banda tiene las dos aplicaciones siguientes (herramientas):

- **WanLinkLogCollector. exe** esta herramienta permite al usuario especificar la información necesaria.

- **BandwidthUtilizationAnalyzer. xlsm** se inicia automáticamente un informe de software de hoja de cálculo de Microsoft Excel mediante WanLinkLogCollector. exe. Esta aplicación permite al usuario aplicar filtros al informe, tal como se muestra más adelante en este artículo.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fases del uso del analizador de uso de ancho de banda

Hay dos fases al usar el analizador de uso de ancho de banda:

- Recopilar registros, que se realiza mediante WanLinkLogCollector. exe

- Personalización de informes, que se realiza mediante BandwidthUtilizationAnalyzer. xlsm

    > [!IMPORTANT]
    > Se recomienda encarecidamente que los usuarios finales no inicien manualmente BandwidthUtilizationAnalyzer. xlsm.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Inicio del analizador de uso de ancho de banda

Inicie WanLinkLogCollector. exe en el símbolo del sistema o mediante el explorador de Windows.

 **Uso de WanLinkLogCollector. exe**

Hay tres pasos para usar WanLinkLogCollector. exe:

1. **Registrar la escala de tiempo** Proporcionar la escala de tiempo que debe generarse el informe para

2. **Especificar los directorios de archivos** Proporcionar información de ubicación de archivos

3. **Recopilar los registros e iniciar el visor de informes** Ejecutar el comando para generar el informe

#### <a name="step-1---log-the-timeline"></a>Paso 1: registrar la escala de tiempo

El registro de la escala de tiempo permite que el usuario de la herramienta especifique lo siguiente, tal como se muestra en la figura siguiente.

1. **Fecha de inicio** Esta es la fecha de inicio de la escala de tiempo para la que se generará el informe; por ejemplo, 1 de agosto de 2010.

2. **Fecha de finalización** Esta es la fecha de finalización de la escala de tiempo para la que se generará el informe; por ejemplo, 30 de septiembre de 2010.

     ![Fechas de inicio y finalización en el uso del ancho de banda](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Paso 2: especificar los directorios de archivos

El usuario puede especificar los siguientes directorios de archivos, tal y como se muestra.

- **Ubicación de los archivos de registro del servidor** La ubicación de la carpeta donde se almacenan los registros del servidor de directivas de ancho de banda. Esto se suele en \<fileserver\> \\<opción de\>fe \AppServerFiles\PDP.

- **Ubicación de almacenamiento de archivos temporales** Ubicación del archivo temporal donde se almacenan los archivos intermedios mientras se genera el informe.

    ![Directorios de archivos en el banda de uso de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > Asegúrese de que el acceso a los registros del servidor y la carpeta de almacén de archivos temporales sea suficiente para el usuario de la herramienta.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Paso 3: recopilar los registros e iniciar el visor de informes

Para recopilar los registros e iniciar el visor de informes, haga clic en **Ejecutar** como se muestra a continuación. Este paso recopila los datos necesarios.

![Recopilar datos en el banda de uso de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Cuando la validación de entrada es correcta, se muestra el mensaje que se muestra a continuación.

![Registros recopilados de la notificación en el uso de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Haga clic en **Aceptar**. BandwidthUtilizationAnalyzer. xlsm se inicia automáticamente. Siga las instrucciones del cuadro de mensaje. Para obtener más información, consulte **uso de BandwidthUtilizationAnalyzer. xlsm** en la siguiente sección.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Uso de BandwidthUtilizationAnalyzer. xlsm

1. Cuando BandwidthUtilizationAnalyzer. xlsm se inicie automáticamente, haga clic en **Actualizar** como se muestra a continuación.

     ![BandwidthUtilizationAnalyzer. xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Cuando se abre una carpeta de archivos, seleccione Consolidated. csv en la ubicación que se especifica en el cuadro de mensaje, como se muestra a continuación. También muestra la ubicación como **C:\temp**.

     ![Abrir una carpeta en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Haga clic en **Importar**.

4. El trazado gráfico se genera automáticamente. Está disponible cuando desaparece el puntero de trabajo en segundo plano.

     ![Aplicar filtros en la vista informe.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Aplicación de filtros a la vista de informe

Los filtros que se pueden aplicar a la vista informes, tal como se muestra a continuación, se describen a continuación:

![Aplicar filtros en la vista informe.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Nombre** de Filtrar por vínculos WAN (el filtro está en el lado derecho del gráfico). El prefijo denota los siguientes tipos de vínculos; Vea el cuadro vertical (azul):

   - **Sitio S** Vínculo WAN de un sitio de red a una región de red

   - **Es entre sitios** El vínculo WAN entre dos sitios de red

   - **R inter-region** El vínculo WAN entre dos regiones de red

2. **Límite superado** Filtra por vínculos WAN cuyo uso de ancho de banda es mayor que la capacidad de ancho de banda

3. **Niveles críticos** Filtra por vínculos WAN cuyo uso de ancho de banda ha alcanzado el 90% o más de la capacidad de ancho de banda

4. **Subutilizado** Filtra por vínculos WAN cuyo uso de ancho de banda ha sido inferior al 25% de la capacidad de ancho de banda

5. **Tipo de vínculo** Filtrar por los siguientes tipos de vínculos WAN:

   - Tipo de **sitio de red**

   - Tipo **entre sitios**

   - Tipo **de vínculo entre regiones**

6. **Región** Filtrar por región de red

Las figuras siguientes muestran los filtros descritos anteriormente.

Filtrar por **nombre**. Seleccione la lista de vínculos que deben mostrarse en el gráfico.

![Filtrado por nombre en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filtrar por **límite superado**. Seleccione **true** para aplicar el filtro.

![Filtrado por límite superado.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtrar por **niveles críticos**. Seleccione **true** para aplicar el filtro.

![Filtrado por niveles críticos.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtrar por **en uso**. Seleccione **true** para aplicar el filtro.

![Filtrado por en uso.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtra por **tipo de vínculo**. Seleccione el tipo o tipos que deben mostrarse.

![Filtrado por tipo de vínculo.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtrar por **región**. Seleccione una lista de regiones cuyos vínculos se deben mostrar.

![Filtrado por región.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Requirements

- .NET Framework 3,5

- Microsoft Excel 2010 o Excel 2007

### <a name="summary"></a>Resumen

El analizador de uso de ancho de banda se usa para trazar el uso del ancho de banda de audio para tráfico de comunicaciones unificadas en la red. Esta herramienta se puede usar también para informar del uso de ancho de banda de vídeo en la red.

## <a name="call-parkometer"></a>Llamar a Parkometer
<a name="callpark"> </a>

Call Parkometer es una aplicación de línea de comandos que proporciona acceso sencillo a la base de datos de órbitas de estacionamiento de llamadas.

### <a name="description"></a>Descripción

Call Parkometer es una herramienta para realizar un seguimiento de las llamadas estacionadas actualmente. También recopila estadísticas sobre las órbitas y el uso del servidor de estacionamiento de llamadas (CPS). Esta herramienta de línea de comandos proporciona acceso de lectura y escritura a la base de datos de SQL Server de CPS de la órbita desde un equipo conectado local o remoto.

Todas las opciones se excluyen mutuamente. La sintaxis de la línea de comandos es la siguiente:

- parámetro **-o** : enumera todos los intervalos de órbita configurados para este grupo de servidores.

- parámetro **-n** : enumera todas las órbitas usadas actualmente en este grupo. La información mostrada es la siguiente:

  - Identificador uniforme de recursos (URI) de SIP del parque y Estacionador.

  - Nombre de host de la CPS donde se estaciona la llamada.

  - Marca de tiempo del momento en el que se estaciona la llamada.

- parámetro **-f** : enumera el número de órbitas libres actualmente en el grupo.

- **-r \<el\> parámetro-n** : \<enumera\> las n últimas llamadas estacionadas. La información mostrada es la siguiente:

  - URI del SIP estacionado.

  - URI del SIP Estacionador.

  - Nombre de host de la CPS en la que se estaciona la llamada.

  - Marca de tiempo de Cuándo se recuperó o se quitó la llamada.

- **-t\<n\> ** parámetro-pruebas que reservan una órbita en la base de datos para mostrar la aleatoriedad de los números de órbitas asignados.

### <a name="output"></a>Output

En función de los parámetros de entrada que se especifiquen en un símbolo del sistema, Call Parkometer muestra el siguiente resultado:

- Todos los intervalos de órbitas que están configurados para este grupo

- Llamadas estacionadas actualmente

- Número de órbitas libres (disponibles)

- Llamadas estacionadas recientemente

- Órbitas reservadas para probar valores de órbitas uniformes y aleatorios

### <a name="purpose"></a>Finalidad

La finalidad de la herramienta CPS es proporcionar acceso desde la línea de comandos a la base de datos de CPS. El administrador puede ver el uso de CPS y determinar el número de órbitas asignadas a un grupo de servidores.

### <a name="requirements"></a>Requirements

No hay requisitos si esta herramienta se ejecuta en el mismo equipo que ejecuta CPS. Si esta herramienta se ejecuta en un equipo remoto, la base de datos de SQL Server usada por Skype empresarial Server 2015 debe estar configurada para permitir el acceso remoto. Llamar a Parkometer debe configurarse con una cadena de conexión de base de datos de SQL Server para conectarse al servidor SQL Server del grupo. Esta cadena de conexión de base de datos de SQL Server se define en el archivo de configuración, **parkometer. exe. config**. Debe colocarse en el mismo directorio donde se encuentra parkometer. exe. El siguiente archivo XML es un ejemplo de parkometer. exe. config. Los parámetros que deben configurarse son el nombre de usuario (por ejemplo, mydomain\Administrator), la contraseña (por ejemplo, contraseña) y el nombre de host (por ejemplo, mi servidor).

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

Intervalos de órbitas implementados: el parámetro-o muestra todos los intervalos de órbitas que están configurados para este grupo de servidores, tal y como se muestra

![Intervalos de órbita en llamada Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Llamadas estacionadas actualmente: el parámetro-n enumera todas las órbitas usadas actualmente en este grupo de servidores, tal como se muestra

![Llamadas estacionadas actualmente en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Número de órbitas libres: el parámetro-f enumera el número de órbitas libres actualmente en el grupo, tal como se muestra

![Órbitas libres en llamadas Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Llamadas estacionadas recientemente: el parámetro- \<r\> n enumera las \<llamadas\> de las que se han estacionado las n últimas, como se muestra

![Llamadas estacionadas recientemente en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Prueba de reserva orbital: el parámetro \<-\> t n comprueba la reserva de una órbita en la base de datos tal como se muestra

![Pruebe las reservas de órbitas en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Resumen

Call Parkometer es una herramienta de línea de comandos que proporciona información detallada sobre el servidor de estacionamiento de llamadas.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Descripción

DBAnalyze es una herramienta de línea de comandos que ayuda a los administradores a recopilar informes de análisis sobre las bases de datos de Skype empresarial Server 2015. DBAnalyze tiene los siguientes modos: diagnóstico, datos de usuario, Conferencia, MCU y fragmentación de disco:

- **Modo de diagnóstico** Crea un informe que incluye información sobre tablas (el número de registros, la fragmentación, el tamaño de los datos y el tamaño del índice), tamaño de los archivos de registro y de datos, el último tiempo de copia de seguridad, la distribución entre los servidores que ejecutan Microsoft Office Communications Server, el número promedio de permisos, contactos, contenedores, suscripciones, publicaciones, extremos por usuario, los usuarios alojados incorrectamente, los usuarios que no se pueden enrutar, el número medio de conferencias organizadas por usuario, conferencias programa y la versión de la base de datos.

    > [!NOTE]
    > El modo de diagnóstico en ejecución puede afectar al rendimiento del servidor.

- **Modo de datos de usuario** Informa sobre los datos del contacto, el contenedor, la suscripción, la publicación, el permiso y el grupo de contactos para un usuario específico o para los usuarios que tienen ese usuario en sus listas de contactos y permisos. Este modo también informa de los datos de Resumen de las conferencias a las que un usuario organiza o al que está invitado.

- **Modo de conferencia** Informa de datos detallados para una conferencia específica, incluidos todos los detalles de tiempo de programación de la Conferencia, la lista de invitados, la lista de tipos de medios permitidos para la Conferencia, las MCU activas (unidades de control multipunto), la lista de participantes activos y el estado de señalización de cada participante.

- **Identificador de reunión de descodificación** Descodifica un identificador de reunión de la red telefónica conmutada (RTC) que especifica el conmutador **/pstnid** pero no se conecta al back-end para obtener información detallada.

- **Resolver Conferencia** Descodifica un identificador de reunión RTC especificado por el modificador **/pstnid** y muestra información sobre la Conferencia indicada por el identificador.

- **Modo MCU** Informa del identificador, el tipo de medio, la dirección URL, el estado de latido, la carga de conferencia y la carga de participantes de cada MCU del grupo.

- **Modo de fragmentación de disco** Muestra el estado de fragmentación de todos los discos.

Esta herramienta se puede usar para diagnosticar varios problemas o ayudar a los administradores con la planeación de la capacidad. Por ejemplo, si la mayoría de los usuarios hospedados en el servidor A eligen a los usuarios hospedados en el servidor B como sus contactos, el administrador puede mover a los usuarios del servidor a al servidor B para reducir el tráfico entre servidores.

### <a name="output"></a>Output

Esta herramienta genera informes predefinidos sobre la base de datos de Skype empresarial Server 2015. **Ruta de acceso**:%programfiles%\Skype para Business Server 2015 \ reskit

### <a name="purpose"></a>Finalidad

Para instalar Dbanalyze. exe, cópielo en una carpeta local y, a continuación, ejecute la herramienta. Para usar la herramienta, ejecute el siguiente comando desde la línea de comandos. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`A continuación se muestran las descripciones de las opciones de la línea de comandos.

![Opciones de la línea de comandos para Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Requirements

 **Equipo** DBAnalyze solo puede ejecutarse desde un equipo unido a un dominio que tenga instalado Skype empresarial Server 2015.

 **Red** El equipo debe ser capaz de conectarse a la base de datos back-end.

 **Software** de Los componentes de software de Skype empresarial Server 2015 deben estar instalados antes de ejecutar DBAnalyze.

 **Usuarios** de En la tabla siguiente se muestran los administradores que tienen los permisos necesarios para acceder a las bases de datos de Skype empresarial Server 2015.

![Tabla de permisos para Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Se requiere una cuenta de administrador local para **/Report:** modo de disco.

### <a name="examples"></a>Ejemplos

Los siguientes son ejemplos de comandos Dbanalyze. exe válidos:

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Resumen

DBAnalyzer proporciona a los administradores un análisis rápido y sencillo de las bases de datos de Skype empresarial Server 2015.

## <a name="import-storage-service-data"></a>Importar datos del servicio de almacenamiento
<a name="Issd"> </a>

La herramienta del kit de recursos de ImportStorageServiceData permite volver a importar datos de cola y de extremo que se han vaciado del servicio de almacenamiento (LYSS) de nuevo en el servicio de almacenamiento.

### <a name="description"></a>Descripción

Los datos vaciados del servicio de almacenamiento podrían haber sido automáticos (periódicos) según el estado de los elementos de la cola o la base de datos. Podría haber sucedido debido a la invocación manual del cmdlet de conmutación por error del grupo o al cmdlet StorageServiceFullFlush (que invoca el cmdlet de conmutación por error del grupo de servidores). Tenga en cuenta que los datos no deberían volver a importarse si el tamaño de la base de datos del servicio de almacenamiento (LYSS) de los servidores front-end es superior al nivel normal, ya que, por lo tanto, es probable que solo se exporten más datos hacia atrás. Además, los problemas que podrían haber contribuido a errores que provocaron el crecimiento de la cola del servicio de almacenamiento deberían resolverse en primer lugar (por ejemplo, errores de punto de conexión de Exchange, problemas de red u otros problemas).

 **Escenario 1:** durante la conmutación por error del grupo, es posible que los archivos se vacíen del servicio de almacenamiento para cada front-end. Una vez completada la conmutación por error, debe ejecutarse la herramienta para volver a importar los datos.

 **Escenario 2:** los datos se vacían automáticamente cada día o en respuesta a la base de datos del servicio de almacenamiento que supera determinados umbrales de tamaño (por ejemplo, 60%, 80%, 90% completo). El administrador debe volver a importar periódicamente los datos vaciados de forma automática. En la situación anterior, si no se implementa el paquete SCOM de supervisión, hay eventos para el servicio de almacenamiento de Skype empresarial Server relacionados con los datos que se vacían del servicio de almacenamiento. Se han iniciado los identificadores de evento de 32075 (operación de vaciado completa), 32076 (vaciado completo), 32082 (se inició el vaciado de nivel de mantenimiento), 32083 (vaciado de nivel de mantenimiento completo), 32089 (vaciado debido a rellenar la base de datos). Nota estos identificadores de evento corresponden a la versión RTM. Cuando un administrador ve estos eventos, significa que hay archivos que se han vaciado. Estos datos deben volver a importarse rutinariamente con esta herramienta, por ejemplo, una vez por semana.

Para la versión de servicio en línea, si se ha implementado el paquete SCOM de supervisión de mantenimiento de Skype empresarial Server, hay nuevas alertas que se pueden plantear que piden al administrador que vuelva a importar los datos vaciados en el servicio de almacenamiento. Habrá un evento correspondiente en el registro de eventos del servidor front-end que activó la alerta. El evento proporcionará una descripción de la ruta de acceso principal en la que se ubican los archivos de datos vaciados, así como el número de archivos que cumplen los criterios de alerta. Los criterios de alerta son que hay X o más archivos en la ruta de acceso del elemento primario concreta que tienen al menos días Y de antigüedad (donde X e Y están preestablecidos en el StorageService, pero se pueden invalidar cambiando el archivo APPCONFIG). A continuación, se muestran dos ejemplos de eventos que pueden desencadenar la alerta de mantenimiento, con la diferencia de que la ruta de acceso principal. Una posibilidad está en el uso compartido de archivos del servicio Web, mientras que la otra posibilidad es el directorio de datos de la aplicación local de cada front-end. (por ejemplo c:\ProgramData\Microsoft\Skype para Business Server 2015 \ StorageService). A continuación, el administrador ejecutará esta herramienta de reskit.

Esta herramienta aumentará la carga de la CPU y de e/s en el front-end en el que se ejecuta, así como otros front-end, en la situación en que los datos no son propiedad del servidor front-end en el que se ejecuta la herramienta. Se recomienda ejecutar esta herramienta cuando los servidores front-end no tienen una carga de CPU y de e/s intensa, por ejemplo, fuera de las horas pico. En segundo lugar, esta herramienta puede tener entre 2 y 3 minutos para importar un archivo de datos. Tenga esto en cuenta al estimar cuánto tiempo se ejecutará la herramienta. El archivo de registro detallado generado por la herramienta aparecerá de forma predeterminada en el almacén de archivos. Elimínelo si no se han notificado errores, ya que el archivo de registro puede tener decenas de MB o más.

![Ejemplo de eventos del registro de eventos del servidor de almacenamiento.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Requirements

Instale las herramientas del kit de recursos de Skype empresarial Server 2015. La herramienta se ejecuta en equipos Unidos a un dominio donde están instalados Skype empresarial Server y Skype empresarial Server Management Shell. La herramienta usa un cmdlet desde el shell de administración para identificar todos los servidores front-end del grupo. En segundo lugar, la herramienta debe ejecutarse desde un equipo en el grupo de servidores que tenga instalada la base de datos **RtcLocal** . Esta base de datos la usa la herramienta para recuperar la ubicación del recurso compartido de archivos WebService para el grupo de servidores. Además, antes de usar la herramienta, cada servidor front-end debe habilitar la comunicación remota de Windows PowerShell con **enable-PSRemoting** en cada servidor front-end, así como el equipo desde el que se ejecuta la herramienta. De lo contrario, se producirá un error en los comandos remotos de Windows PowerShell de esta herramienta. La comunicación remota de Windows PowerShell puede desactivarse en todos los servidores front-end del grupo una vez finalizado. Por último, la cuenta o credencial que invoca la herramienta debe tener permiso de lectura y escritura en el recurso compartido de archivos WebService para el grupo en el que está ejecutando esta herramienta. De lo contrario, la herramienta producirá errores de permiso de e/s.

> [!NOTE]
> En Windows Server 2012, la comunicación remota de Windows PowerShell está habilitada de forma predeterminada, pero no en el sistema operativo Windows Server 2008.

### <a name="examples"></a>Ejemplos

```console
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

La herramienta LCSSync ayuda a implementar el software de comunicaciones de Skype empresarial Server 2015 en un entorno de varios bosques. Esta herramienta se usa para sincronizar usuarios y grupos de bosques de usuarios diferentes como un objeto de contacto de servicios de dominio de Active Directory para un bosque central en el que se ha instalado Skype empresarial Server 2015.

### <a name="description"></a>Descripción

 LCSSync usa los objetos de contacto de los servicios de dominio de Active Directory sincronizados en el bosque central para habilitar a los usuarios en Skype empresarial Server. Para proporcionar un inicio de sesión único, la cuenta de usuario principal debe estar asignada al objeto de contacto de servicios de dominio de Active Directory en el bosque central de Skype empresarial Server 2015. Esta herramienta ayuda a realizar esa asignación. Esta herramienta proporciona plantillas para crear agentes de administración en Microsoft Identity Integration Server.

### <a name="summary"></a>Resumen

La herramienta LCSSync ayuda a implementar Skype empresarial Server 2015 en un entorno de varios bosques.

## <a name="lookup-user-console"></a>Consola del usuario de búsqueda
<a name="LUC"> </a>

La herramienta LookupUserConsole muestra información de enrutamiento del servidor de Skype empresarial interno sobre usuarios específicos. Esta información puede ser útil para que Microsoft admita personal en el diagnóstico de problemas de implementación y enrutamiento.

### <a name="description"></a>Descripción

 Al ejecutar LookupUserConsole. exe se abrirá un símbolo del sistema que acepta direcciones SIP e intenta mostrar la información de enrutamiento de Skype empresarial Server interna relacionada. Escriba **Exit** para salir de la herramienta LookupUserConsole.

### <a name="requirements"></a>Requirements

Instale el kit de recursos de Skype empresarial Server 2015. La herramienta se ejecuta en equipos Unidos a un dominio donde está instalado Skype empresarial Server.

### <a name="examples"></a>Ejemplos

C:\Archivos de Files\Skype para Business Server 2015 \ reskit\>LookupUserConsole. exe

```console
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

La herramienta MSTurnPing permite a un administrador del software de comunicaciones de Skype empresarial Server 2015 comprobar el estado de los servidores que ejecutan el servidor perimetral de audio y vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan los servicios de directivas de ancho de banda en la topología.

### <a name="description"></a>Descripción

La herramienta MSTurnPing permite a un administrador del software de comunicaciones de Skype empresarial Server 2015 comprobar el estado de los servidores que ejecutan el servidor perimetral de audio y vídeo y los servicios de autenticación de audio y vídeo, así como los servidores que ejecutan los servicios de directivas de ancho de banda en la topología.

La herramienta permite al administrador realizar las siguientes pruebas:

1. Prueba del servidor perimetral a/V: la herramienta realiza pruebas en todos los servidores perimetrales A/V de la topología mediante el siguiente procedimiento:

   - Comprobar que el servicio de autenticación de audio y vídeo de Skype empresarial Server se ha iniciado y que puede emitir las credenciales correctas.

   - Comprobando que el servicio perimetral de audio y vídeo de Skype empresarial Server se ha iniciado y que puede asignar correctamente los recursos en el servidor perimetral externo.

2. Prueba del servicio de directiva de ancho de banda: la herramienta realiza pruebas en todos los servidores que ejecutan los servicios de directiva de ancho de banda de la topología haciendo lo siguiente:

   - Comprobar que el servicio de directiva de ancho de banda (autenticación) de Skype empresarial Server se ha iniciado y puede emitir las credenciales correctas.

   - Comprobar que el servicio de directiva de ancho de banda (principal) de Skype empresarial Server se ha iniciado y puede realizar correctamente la comprobación del ancho de banda.

Esta herramienta debe ejecutarse desde un equipo que forme parte de la topología y tenga instalado el almacén local.

### <a name="output"></a>Output

La herramienta genera los resultados de cada una de las operaciones.

- Si se realiza la prueba **AudioVideoEdgeServer** , los resultados de la herramienta son los siguientes:

  - Los resultados de la prueba de los equipos que proporcionan el servicio de autenticación de audio y vídeo de Skype empresarial Server 2015 en la topología

  - Los resultados de la prueba de los equipos que proporcionan el servicio perimetral de audio y vídeo de Skype empresarial Server 2015 en la topología

- Si se realiza la prueba **BandwidthPolicyServer** , los resultados de la herramienta son los siguientes:

  - Los resultados de la prueba de los equipos que proporcionan el servicio de directiva de ancho de banda (autenticación) de Skype empresarial Server 2015 en la topología

  - Los resultados de la prueba de los equipos que proporcionan el servicio de directiva de ancho de banda (principal) de Skype empresarial Server 2015 en la topología

### <a name="requirements"></a>Requirements

- Esta herramienta debe ejecutarse desde un equipo que esté en la topología y que tenga el almacén local.

- La herramienta debe ejecutarse como un administrador que tenga acceso al almacén local.

### <a name="examples"></a>Ejemplos

El siguiente es un ejemplo de la entrada de la herramienta.

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Resumen

Esta herramienta puede ser un recurso valioso para los administradores de Skype empresarial Server 2015 que quieran comprobar el estado de los servidores que ejecutan los servicios de directivas de audio y vídeo y de ancho de banda.

## <a name="network-configuration-viewer"></a>Visor de configuración de red
<a name="NCV"> </a>

Los administradores de software de comunicaciones de Skype empresarial Server 2015 pueden usar el visor de configuración de red para ver la topología de red de control de admisión de llamadas (CAC) para una empresa que se aprovisiona para permitir sesiones de comunicación en tiempo real, como llamadas de voz o vídeo basadas en la capacidad de ancho de banda especificada. Los administradores de Skype empresarial Server 2015 definen directivas de CAC, que aplican los servicios de directivas de ancho de banda que se instalan con Skype empresarial Server 2015.

### <a name="description"></a>Descripción

El visor de configuración de red (NetworkConfigurationViewer. exe) permite a los administradores realizar las siguientes tareas:

- Cargar y ver la topología de red de CAC de una implementación de Skype empresarial Server 2015 en formato gráfico.

- Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directivas de ancho de banda en un formato gráfico.

- Guarde y almacene la topología de red de CAC en formato XML en el disco.

- Guarde y almacene el diagrama de topología de red de CAC en formato JPG o BMP.

- Ver los datos de configuración de la topología de red de CAC.

- Ver la topología de red de CAC en un estilo de vista de árbol.

- Defina los conectores personalizados para los vínculos de topología de red de CAC (por ejemplo, vínculos de sitio a región, de región a región y de sitio a sitio).

- Ver información del sitio de la topología de red de CAC, información de región y directivas de ancho de banda aprovisionadas y vínculos de red.

### <a name="purpose"></a>Finalidad

Ver los vínculos de topología de red CAC empresarial en una interfaz gráfica.

### <a name="examples"></a>Ejemplos

 **Cargar y ver la topología de red de CAC de una implementación de Skype empresarial server 2015 en formato gráfico**: los administradores de Skype empresarial Server 2015 pueden cargar y ver la configuración de la topología de red de CAC en cualquier equipo de Skype empresarial Server 2015 mediante la opción de **descarga de configuración de red** , tal como se muestra en la figura siguiente. La herramienta no podrá descargar ni ver dicha configuración cuando se implemente en un equipo que no tiene conectividad con el almacén de configuración de Skype empresarial Server 2015.

![Descargar la configuración de red.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directivas de ancho de banda en formato gráfico:** Los servidores de directivas de ancho de banda de Skype empresarial Server 2015 guardan la topología de red de CAC como parte del mecanismo de registro en la ubicación del recurso compartido de archivos de Skype empresarial Server 2015. Los administradores de Skype empresarial Server 2015 pueden ver este archivo en formato gráfico con la opción **abrir configuración de red** , tal como se muestra a continuación.

![Abrir un archivo de registro de servidor de directivas de ancho de banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Guarde y almacene la topología de red de CAC en formato XML en el disco: Skype empresarial Server 2015 los administradores pueden guardar el archivo de configuración de la topología de red de CAC en formato XML con la opción **guardar una copia de la configuración de red** , tal como se muestra a continuación. El archivo de configuración guardado puede usarse sin conexión para fines de visualización gráfica.

![Guardar la configuración de red como un archivo XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Guarde y almacene el diagrama de topología de red de CAC en formato JPG o BMP: Skype empresarial Server 2015 los administradores pueden guardar la configuración de la topología de red de CAC en formato gráfico (formatos de archivo JPG y BMP) mediante la opción **Guardar diagrama de configuración de red como imagen** , como se muestra a continuación.

![Guardar la configuración de red como una imagen.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Ver los datos de configuración de la topología de red de CAC:</strong> Los administradores de Skype empresarial Server 2015 pueden ver los datos de configuración de red relacionados, como las regiones de red, los sitios de red, los perfiles de ancho de banda y las direcciones IP de subred de sitio en formato de texto mediante la opción ver datos de configuración de red, tal como se muestra a continuación.

![Ver los datos de configuración de la red.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Ver la topología de red de CAC en un estilo de vista de árbol:** Los administradores de Skype empresarial Server 2015 pueden ver los datos de configuración de red relacionados en un estilo de vista de árbol gráfico mediante el panel de control, en el lado izquierdo de la ventana de herramientas, tal como se muestra a continuación.

![Ver los datos de configuración de red en una vista de árbol.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Definir conectores personalizados para los vínculos de topología de red de CAC (como vínculos de sitio a región, de región a región y de sitio a sitio):** Los administradores de Skype empresarial Server 2015 pueden definir conectores gráficos personalizados para los vínculos WAN de configuración de red de CAC mediante la opción configuración, tal como se muestra a continuación. Esto ayuda a diferenciar entre varios tipos de vínculos de red que se aprovisionan en la configuración de red.

![Herramientas](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Ver la información del sitio de la topología de red de CAC, información de región y directivas de ancho de banda aprovisionadas:** Los administradores de Skype empresarial Server 2015 pueden ver la información de la región de red CAC, la información del sitio y la información de aprovisionamiento de ancho de banda de CAC con las opciones que se muestran a continuación. (Por ejemplo, haga clic en **información** en una región de red o un objeto de sitio de red).

![Definir conectores personalizados para la red.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Resumen

Esta herramienta puede ser un recurso valioso para los administradores de Skype empresarial Server 2015 que quieran ver la topología de red de CAC para su implementación en un formato gráfico.

## <a name="response-group-agent-live"></a>Response Group Agent Live
<a name="RGAL"> </a>

La aplicación de grupo de respuesta ofrece a los agentes la capacidad de tener acceso a información útil en tiempo real mediante su servicio Web integrado. Desafortunadamente, no hay ninguna vista gráfica de estos datos disponibles fuera de la aplicación. La herramienta de kit de recursos Live Response Agent Live Report resuelve este problema proporcionando una forma sencilla y gráfica para obtener acceso a esta información, mejorada con información de software de comunicaciones de Skype empresarial en tiempo real, como la presencia de otros agentes.

### <a name="description"></a>Descripción

Response Group Agent Live es una aplicación de Windows que proporciona la funcionalidad de inicio y cierre de sesión, así como información en tiempo real (como la pertenencia a grupos y el número actual de llamadas) a los agentes del grupo de respuesta. Está diseñada para ser una versión mejorada de la página grupos de agentes (accesible desde Skype empresarial).

### <a name="purpose"></a>Finalidad

La aplicación de grupo de respuesta pone en cola las llamadas entrantes y, a continuación, las enruta a los grupos de agentes. Para tomar decisiones informadas sobre las llamadas al servicio, los agentes pueden obtener acceso a información en tiempo real sobre sus grupos de agentes, como qué otros agentes están disponibles y cuántas llamadas están esperando en cada cola. Esta información, inicialmente accesible solo a través del servicio de grupo de respuesta, está disponible de forma intuitiva mediante Response Group Agent Live.

#### <a name="features"></a>Características

La herramienta Response Group Agent Live se basa en el servicio de grupo de respuesta y el SDK de Skype empresarial Server 2015. Proporciona agentes de grupo de respuesta información y capacidades que están disponibles en el servicio de grupo de respuesta (como la pertenencia a grupos, la presencia de otros agentes y el número de llamadas en espera).

La ilustración siguiente muestra la interfaz principal de Response Group Agent Live.

![La herramienta Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Las siguientes tres características principales están disponibles para los agentes en Response Group Agent Live:

- **Iniciar/cerrar sesión:** Al contrario que la página grupos de agentes (accesible desde Skype empresarial Server 2015), el agente de grupo de respuesta Live permite que solo los agentes inicien o salgan de todos los grupos de agentes a la vez. Esta aplicación proporciona tres métodos rápidos para que los agentes inicien o cierren sesión:

  - Haga clic en los botones de inicio y cierre de sesión (verde y rojo) dentro de la aplicación.

  - Haga clic con el botón derecho en el icono de la bandeja del sistema y seleccione iniciar sesión o cerrar sesión.

  - Usar métodos abreviados de teclado configurables.

- **Pertenencia a grupos:** Cuando se selecciona un grupo de agentes, Response Group Agent Live muestra la lista de agentes de este grupo en el panel derecho. Si Skype empresarial Server 2015 se está ejecutando en el mismo equipo que esta aplicación, la información de presencia y la tarjeta de contacto se muestran en el Group Response Agent Live. Los agentes pueden enviar un mensaje instantáneo o llamar a otros agentes directamente desde allí.

- **Estadísticas en tiempo real:** Response Group Agent Live proporciona estadísticas en tiempo real para todos los grupos de agentes. La frecuencia de actualización es un minuto. Cuando un grupo de respuesta responde a una llamada, se agrega un indicador visual junto al nombre del grupo con el número actual de llamadas en cola. Al pausar el puntero sobre un grupo, también se muestra el tiempo de espera más largo.

### <a name="requirements"></a>Requirements

Response Group Agent Live requiere .NET Framework 4,0. Además, para aprovechar las características de presencia y tarjeta de contacto, Skype empresarial debe instalarse de forma local (y estar en ejecución).

#### <a name="configuration"></a>Configuración

Response Group Agent Live puede personalizarse según las preferencias individuales mediante el cuadro de diálogo Opciones de la aplicación. Además, el administrador puede definir la dirección de host predeterminada editando directamente la propiedad defaultHostAddress del archivo RGAgentLive. exe. config.

La ilustración siguiente muestra el cuadro de diálogo Opciones que los agentes pueden usar para configurar las teclas de acceso directo y dirección de host. Para obtener acceso a este cuadro de diálogo, haga clic en el botón Opciones de la parte superior derecha de la interfaz principal.

![El cuadro de diálogo Opciones del agente de respuesta dinámica del grupo de respuesta.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Las siguientes tres opciones de configuración distintas se pueden personalizar en la configuración de agente de grupo de respuesta:

- Dirección de host: suele ser el FQDN del grupo de servidores web que pertenece al grupo principal del agente. La dirección exacta del servicio del grupo de respuesta se deriva automáticamente en segundo plano a partir de esta información (anexando la ruta de acceso correcta después del host).

- Accesos directos: los métodos abreviados exactos para iniciar y cerrar sesión pueden personalizarse. La única limitación es que ambos métodos abreviados deben contener la tecla del logotipo de Windows (además de, al menos, otra tecla).

- Iniciar con Windows: la aplicación se puede configurar para iniciarse automáticamente con Windows.

### <a name="examples"></a>Ejemplos

En la siguiente figura se muestra cómo llamar o enviar un mensaje instantáneo a otro agente haciendo clic con el botón secundario en el contacto en el panel derecho.

![Hacer una llamada o enviar un mensaje instantáneo.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

La ilustración siguiente muestra cómo Response Group Agent Live muestra el número actual de llamadas en la cola y el tiempo de espera más largo entre todas estas llamadas entrantes.

![Ver información de cola.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Resumen

La rapidez en el inicio y el cierre de sesión, la pertenencia a grupos y las estadísticas básicas en tiempo real son características interesantes del agente de grupo de respuesta que solo están disponibles fuera de la aplicación desde el servicio de grupo de respuesta. Con la herramienta del kit de recursos del agente de grupo de respuesta Live, los administradores de Skype empresarial Server 2015 pueden proporcionar a sus agentes una aplicación de Windows que les permita realizar tareas de una manera gráfica y rápida.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (la activación de características de extensión secundaria) es una herramienta de línea de comandos que permite a los administradores de software de comunicaciones de Skype empresarial Server 2015 y a los agentes de asistencia técnica configurar la llamada delegada, el desvío de llamadas, las llamadas simultáneas configuración de llamada de equipo y recogida de llamadas de grupo en nombre de un usuario de Skype empresarial Server 2015. La herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular. La herramienta SEFAUtil permite al administrador habilitar/deshabilitar/modificar el desvío de llamadas o las llamadas simultáneas en nombre del usuario. El administrador puede especificar el destino (en forma de URI de SIP) o usar un destino ya publicado por el usuario. Esta herramienta también permite a los administradores agregar o quitar delegados o miembros del grupo de llamada de equipo en nombre del usuario. Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3,0 y requiere que los administradores creen una aplicación de confianza en el almacén de administración central para SEFAUtil.

SEFAUtil (activación de características de extensión secundaria) permite a los administradores y los agentes del Departamento de soporte técnico de Skype empresarial Server 2015 configurar las llamadas delegadas, el desvío de llamadas, las llamadas simultáneas, la configuración de llamada de equipo y la atención de llamadas grupales en nombre de un cliente de Skype para el usuario de Business Server 2015. Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular.

### <a name="description"></a>Descripción

La versión actual de SEFAUtil es solo una herramienta de línea de comandos; no hay ninguna interfaz gráfica de usuario compatible. Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3,0. Las características de esta herramienta permiten que los administradores y los agentes del Departamento de soporte técnico hagan lo siguiente:

- Ver toda la configuración de enrutamiento de llamadas de un usuario (incluye el desvío de llamadas, la delegación, las llamadas simultáneas, la llamada de equipo y la atención de llamadas de grupo)

- Habilitar/deshabilitar/modificar la configuración de desvío de llamadas (incluye el destino y el temporizador sin respuesta)

- Habilitar/deshabilitar/modificar las configuraciones inmediatas de reenvío de llamadas

- Habilitar/deshabilitar/modificar la configuración de la delegación

- Habilitar/deshabilitar/modificar la configuración de grupo de llamada de equipo

    > [!NOTE]
    > New in Skype for Business Server 2015 SEFAUtil Tool

- Habilitar/deshabilitar/modificar la configuración de llamadas simultáneas (incluye el destino)

    > [!NOTE]
    > New in Skype for Business Server 2015 SEFAUtil Tool

- Habilitar/deshabilitar/modificar la configuración de RECALL de llamadas de grupo

    > [!CAUTION]
    > New in Skype for Business Server 2015 SEFAUtil Tool

Esta herramienta tiene las siguientes limitaciones:

- Compatible solo para usuarios hospedados en un grupo de servidores de Skype empresarial Server

- No se admite la edición en masa de la configuración de enrutamiento de llamadas para varios usuarios

### <a name="output"></a>Output

La versión actual de esta herramienta proporciona resultados sólo en la ventana del símbolo del sistema. Para obtener más información, vea la sección ejemplos más adelante en este documento.

### <a name="purpose"></a>Finalidad

A continuación se muestran algunos de los escenarios clave en los que se puede usar esta herramienta:

- Bob es un ejecutivo y se ha trasladado a la telefonía de Skype empresarial Server. Ha delegado en su sistema PBX existente. Como parte de la migración a Skype empresarial Server 2015, el administrador puede configurar el enrutamiento de Bob para reflejar su configuración de delegación preexistente.

- Alicia está viajando y se da cuenta de que espera una llamada importante de uno de sus clientes. Sin embargo, se encuentra en un hotel y no tiene acceso a un equipo. Llama al Departamento de soporte técnico y solicita que se reenvíen a su número de teléfono móvil todas las llamadas realizadas a su número de trabajo. El personal del Departamento de soporte técnico puede realizar la configuración en su nombre.

- Las llamadas de Joe a su número de trabajo van a su correo de voz móvil siempre que esté en el trabajo; sin embargo, las cosas parecen funcionar correctamente en la mayoría de las demás ubicaciones. El técnico del Departamento de soporte técnico puede ver la configuración de enrutamiento de Joe y detecta que José ha configurado las llamadas simultáneas a su teléfono móvil. El técnico pregunta a Joe sobre la cobertura móvil en su oficina y puede determinar que la regla de timbre simultáneo es lo que está causando que las llamadas se desplazan al correo de voz móvil de Joe cuando su cobertura de red es deficiente.

- Mike es un nuevo empleado de Contoso y se une a un nuevo equipo en el que todos los miembros están configurados para la llamada de equipo, cuando se habilitan para Skype empresarial Server 2015, el administrador puede establecer la configuración del grupo de llamada de equipo para incluir a todos los nuevos miembros del equipo. Además, el administrador agrega Mike como miembro del grupo de llamada de equipo para cada uno de los miembros de su equipo.

- Una práctica de servicio al cliente en el Departamento de recursos humanos de Contoso es proporcionar servicio personal para todos los autores de llamadas desde la primera llamada. Dado que todos los miembros del Departamento se encuentran muy cercanos entre sí, tener todos los teléfonos que suenen al mismo tiempo con la llamada de equipo es muy disruptiva para el equipo. Para proporcionar el mejor servicio sin interrumpir a los miembros del equipo, el administrador de Skype empresarial Server 2015 aprovecha la capacidad de llamada de grupo. El administrador agrega todos los miembros del Departamento a un grupo de recogida y se comunica con el número de grupo de recogida del Departamento. Cuando Samantha no está en su escritorio, Joe detecta su timbre telefónico y continúa respondiendo a la llamada desde su escritorio.

### <a name="requirements"></a>Requirements

La herramienta SEFAUtil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza. UCMA 3,0 debe estar instalado en el equipo. Para ejecutar la herramienta, se debe crear una nueva aplicación de confianza con el identificador de la aplicación SEFAUtil en ese grupo de servidores.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Creación de una nueva aplicación de confianza para la herramienta SEFAUtil

1. La herramienta SEFAUTil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza. Si es necesario, puede Agregar un grupo de servidores como un nuevo grupo de aplicaciones de confianza mediante el shell de administración de Skype empresarial Server con el siguiente cmdlet:

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > UCMA 3,0 debe instalarse en cualquier equipo que se use para ejecutar la herramienta SEFAUtil.

2. Una aplicación de confianza debe definirse en la topología de la herramienta SEFAUtil. Para definir SEFAUtil como una nueva aplicación de confianza, use el shell de administración de Skype empresarial Server y ejecute el siguiente cmdlet:

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > Si es necesario, se puede usar un puerto diferente.
    
    > [!NOTE]
    > FQDN del grupo de servidores: el FQDN del servidor o grupo de servidores que va a hospedar la aplicación de SEFAUtil (normalmente un servidor front-end de Skype empresarial > o grupo de servidores).
    > FQDN del registrador de grupo de servidores: el FQDN del servidor front-end o grupo de servidores front-end de Skype empresarial asociado con este grupo de aplicaciones.
    > Sitio de Grupo: el identificador de sitio del sitio en el que se hospeda este grupo de servidores.

3. Los cambios en la topología deben estar habilitados. La habilitación de los cambios en la topología se puede realizar mediante el shell de administración de Skype empresarial Server ejecutando el siguiente cmdlet:

   ```powershell
   Enable-CsToplogy
   ```

4. Si es necesario, instale las herramientas del kit de recursos de Skype empresarial Server 2015 en el servidor que se usará para ejecutar la herramienta SEFAUtil (el servidor debe formar parte de un grupo de aplicaciones de confianza).

5. Compruebe que la SEFAUtil se está ejecutando correctamente. Para ello, ejecute la herramienta desde un símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación. De forma predeterminada, la herramienta se encontrará en: ". ..\Archivos de Files\Skype para empresas Server 2015 \ reskit". Para mostrar la configuración de desvío de llamadas de un usuario, use el siguiente comando:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    Se debe mostrar la configuración de desvío de llamadas del usuario.

#### <a name="group-call-pickup"></a>Recogida de llamadas grupales

La recogida de llamadas de grupo requiere una configuración adicional en Skype empresarial Server 2015 para que la capacidad esté completamente habilitada. Antes de asignar grupos de recogida a los usuarios, consulte la documentación del producto de recogida de llamadas de grupo para conocer los pasos de planeación e implementación de esta función.

### <a name="examples"></a>Ejemplos

#### <a name="display-current-call-handling-settings"></a>Mostrar la configuración de control de llamadas actual

El siguiente comando muestra el control de llamadas del usuario.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> En este ejemplo, se usa el modificador **/Server** para especificar el servidor de Skype empresarial al que se va a conectar.

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Establecer el destino de desvío de llamadas/sin respuesta

En este ejemplo se establece el destino de desvío de llamadas y de no respuesta y el retraso del timbre. Aquí no se proporciona el modificador/Server; SEFAUtil intenta detectar automáticamente Skype empresarial Server 2015.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>Habilitar el desvío de llamadas inmediatamente

En este ejemplo se habilita inmediatamente el desvío de llamadas a otro usuario.

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>Deshabilitar el desvío de llamadas inmediatamente

En este ejemplo se deshabilita inmediatamente el desvío de llamadas.

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Adición de un usuario como delegado y configuración de llamadas simultáneas de delegados

En este ejemplo se agrega un usuario como delegado y se configura la llamada simultánea de los delegados.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Cambiar la regla de llamadas simultáneas de delegados

En este ejemplo se cambia la regla de llamadas simultáneas que se estableció en el ejemplo anterior por la regla de timbre aplazado.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>Quitar el delegado

En este ejemplo se quita el delegado.

> [!NOTE]
> Cuando se quita el último delegado, se deshabilita automáticamente el timbre de delegación.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Adición de un delegado y configuración de la regla de desvío de llamadas a delegados

En este ejemplo se agrega un delegado y se configura la regla de desvío de llamadas a delegados.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Habilitar llamadas simultáneas y establecer un número de destino

En este ejemplo se habilitan las llamadas simultáneas y se establece un número de destino de llamadas simultáneas.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Para cambiar el número de destino de llamadas simultáneas de un usuario que ya tiene habilitada la llamada simultánea, mantenga el comando con el modificador/enablesimulring; de lo contrario, no se cambiará el número de destino.

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Deshabilitar las llamadas simultáneas

En este ejemplo se deshabilita la característica de llamadas simultáneas.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Agregar un integrante del grupo para la llamada de equipo y configurar las llamadas simultáneas al grupo de miembros de llamada de equipo

En este ejemplo se agrega un integrante del grupo al grupo de llamada de equipo de un usuario y se habilita la característica de llamadas simultáneas al grupo de llamada de equipo.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Al agregar un miembro al grupo de llamada de equipo de un usuario, se cambiará automáticamente el configuración de llamadas simultáneas de los usuarios para situaciones su grupo de llamada de equipo.

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Quitar un miembro del grupo de llamada de equipo

En este ejemplo se quita un miembro del equipo del grupo de llamada de equipo de un usuario.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Si el miembro que se va a quitar es el único miembro del grupo de llamada de equipo, las llamadas simultáneas al grupo de llamada de equipo se deshabilitarán de forma automática.

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Establecer el anillo retrasado en el grupo de llamada de equipo

En este ejemplo se cambia el timbre retrasado a la configuración de hora de grupo de llamada de equipo.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>Habilitar llamada de equipo

En este ejemplo se habilita la llamada de equipo para un usuario determinado.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Si el grupo de llamada de equipo del usuario no tiene miembros, la llamada de equipo no se habilitará.

 **Resultado**

#### <a name="disable-team-call"></a>Deshabilitar llamada de equipo

En este ejemplo se deshabilita la llamada de equipo para un usuario determinado.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Habilitar la atención de llamadas grupales y asignar un grupo de recogida a un usuario

En este ejemplo se asigna un grupo de recogida a un usuario y se habilita la recogida de llamadas grupales.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>Deshabilitar la recogida de llamadas de grupo

En este ejemplo se deshabilita la llamada de llamadas grupales para un usuario determinado.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Cuando se deshabilita la recepción de llamadas de grupo para un usuario, no se conserva el número de grupo que se asignó al usuario. Si, posteriormente, desea volver a habilitar la atención de llamadas grupales para ese usuario, debe volver a asignar el número de grupo con el modificador/enablegrouppickup.

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep. ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Descripción

SYSPrep. PS1 es un script de Windows PowerShell que instalará los siguientes requisitos previos de Skype empresarial Server 2015 en el equipo del sistema operativo Windows Server 2008.

- Microsoft .NET Framework 4,5

- Microsoft SQL Server Express

- Windows PowerShell versión 3,0

- Paquete redistribuible de Visual C++ 2010

- Actualizaciones de Internet Information Server

- Windows Identity Foundation

- Archivos principales de Skype empresarial Server 2015

  Aunque el nombre del script es similar a la herramienta de preparación del sistema para los sistemas operativos de Microsoft Windows, son diferentes. Este script solo instalará los requisitos previos necesarios para Skype empresarial Server 2015. Una vez instalados estos requisitos previos, puede usar la herramienta SYSPrep de Windows para crear una imagen del servidor.

### <a name="requirements"></a>Requirements

Antes de ejecutar el script SYSPrep. ps1, debe copiar los archivos de requisitos previos en una carpeta local del equipo del sistema operativo Windows Server 2008 (por ejemplo **, D:\setup)**. Esta carpeta también debe incluir una copia de los archivos de Skype empresarial Server 2015, concretamente **setup. exe.** Los archivos de requisitos previos se pueden descargar desde las siguientes ubicaciones:


| **Requisitos previos**                                | **Ubicación**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4,5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell versión 3,0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Paquete redistribuible de Visual C++ 2010  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| Actualizaciones de Internet Information Server  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Setup. exe de Skype empresarial Server 2015  <br/> | Copiar desde los medios de Skype empresarial Server 2015  <br/>                   |

### <a name="parameter"></a>Parámetro

El parámetro **-SetupFolder** toma como argumento la ubicación del directorio de los archivos de requisitos previos

### <a name="examples"></a>Ejemplos

Para ejecutar el script SYSPrep. PS1 e instalar los requisitos previos de Skype empresarial Server 2015, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Número de anuncios no asignados a la migración
<a name="UNAM"> </a>

La herramienta de migración de anuncios de números sin asignar permite que un administrador de Skype empresarial Server 2015 mueva la configuración de números sin asignar que recibe el servicio de la aplicación de anuncio de un servidor o grupo de Skype empresarial de origen a un destino de Skype empresarial Server o grupo de servidores.

### <a name="description"></a>Descripción

La herramienta de migración de anuncios de números sin asignar es un script de Windows PowerShell que mueve la configuración de números sin asignar que recibe el servicio de la aplicación de anuncio de un servidor o grupo de origen a otro servidor o grupo de servidores.

Cuando se ejecuta, el script de migración de números sin asignar de anuncios realizará las siguientes operaciones:

1. Mueva todos los archivos de audio usados por los anuncios de números sin asignar de la aplicación de anuncio hospedada en el servidor o grupo de origen al almacén de archivos del servidor o grupo de destino.

    > [!NOTE]
    > Los archivos de audio se quitan del grupo de origen una vez que se copian en el grupo de servidores de destino.

2. Se mueven todos los anuncios de números sin asignar configurados para la aplicación de anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.

3. Reasignar todos los intervalos de números no asignados que reciben servicio de la aplicación de anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.

Después de ejecutar correctamente el script, todos los intervalos de números sin asignar que provienen de la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen se proporcionarán con la misma configuración que el servidor o el grupo de destino.

### <a name="output"></a>Output

El script **Move-CsAnnouncementConfiguration** indica en la ventana del shell de administración de Skype empresarial Server desde donde se ejecuta el éxito o el fracaso de la operación de migración.

Si cualquier error interrumpe la ejecución de la operación, los intervalos de números sin asignar que se movieron correctamente al destino permanecerán en el destino en un formulario operativo y el resto de los intervalos de números sin asignar que se van a migrar permanecerán en el origen también en un formulario operativo. Para migrar por completo el resto de la configuración, vuelva a ejecutar el script después de solucionar el error.

### <a name="purpose"></a>Finalidad

Se puede usar el script de migración de anuncios de números sin asignar en los tres escenarios siguientes:

- **Migrar las opciones de configuración a una nueva versión de Skype empresarial Server:** Contoso está en proceso de migrar a Skype empresarial Server 2015 y, como parte del proceso de migración, el administrador de Skype empresarial Server desea mover la configuración de números no asignados a la que el anuncio ha dado servicio desde la implementación de Lync Server 2013 a la nueva implementación de Skype empresarial Server 2015. Para mover las opciones de configuración, el administrador de Skype empresarial Server usa la herramienta de migración de anuncios de números sin asignar.

- **Revertir una implementación de Skype empresarial Server 2015 a Lync Server 2013:** Debido a los factores inesperados, Contoso tiene que revertir la migración a la nueva implementación de Skype empresarial Server 2015. Para minimizar las interrupciones en el servicio, el administrador de Skype empresarial Server usa la herramienta de migración de anuncios de números sin asignar para revertir la configuración de la implementación de Skype empresarial Server 2015 a la implementación de Lync Server 2013.

- **Movimiento de datos entre implementaciones:** Contoso está en proceso de reemplazar todos los servidores de un grupo por los nuevos servidores. Su estrategia es implementar un nuevo grupo de servidores de Skype empresarial Server 2015, mover todos los datos del antiguo al nuevo y, a continuación, dejar de utilizar el grupo anterior. Una vez que se haya implementado el nuevo grupo de servidores, se usará la herramienta de migración de anuncios de números sin asignar para mover la configuración del grupo anterior al nuevo.

#### <a name="requirements"></a>Requirements

Los siguientes son los requisitos principales necesarios para ejecutar correctamente la herramienta:

1. El script debe ejecutarse desde un equipo que tenga instalado el shell de administración de Skype empresarial Server.

2. La aplicación de anuncio tiene que implementarse correctamente en los servidores o grupos de servidores de Skype empresarial de origen y de destino.

#### <a name="move-csannouncementconfiguration-script"></a>Secuencia de comandos Move-CsAnnouncementConfiguration

El script Move-CsAnnouncementConfiguration requiere los dos parámetros que se describen en la tabla siguiente.

![Parámetros Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Ejemplos

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Lync Server 2013 a un grupo de servidores de Skype empresarial 2015

En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Lync Server 2013) al grupo de destino (Skype empresarial Server 2015).

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Mover la configuración de anuncios de números sin asignar de un grupo de servidores de Skype empresarial Server 2015 a un grupo de servidores de Lync Server 2013

En este ejemplo se mueven los anuncios de números sin asignar del grupo de origen (Skype empresarial Server 2015) al grupo de servidores de destino (Lync Server 2013).

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Datos de conf de Web
<a name="WebConfData"> </a>

La herramienta de datos Web conf permite que un administrador del software de comunicaciones de Skype empresarial Server 2015 tenga más control sobre los datos asociados con las conferencias web del organizador. Los escenarios incluyen la capacidad de eliminar los datos específicos de una reunión de un usuario en función de los criterios de marca de tiempo.

### <a name="description"></a>Descripción

Esta herramienta permite al administrador realizar las siguientes operaciones:

1. Buscar todos los datos de conferencias web asociados con un único usuario.

2. Eliminar todos los datos de conferencias web asociados con un único usuario.

3. Elimine todos los datos de conferencias web asociados con un único usuario que sea anterior a una fecha concreta.

4. Se mueven todos los datos de conferencias web asociados con un usuario único cuando este usuario se mueve de un grupo de servidores a otro.

    > [!NOTE]
    > Las herramientas del kit de recursos para Lync Server 2010 admiten el traslado de todos los datos de conferencias web asociados con un usuario único cuando se mueve a ese usuario de un grupo de servidores a otro. Esa funcionalidad ahora está en desuso de esta herramienta en favor del parámetro **MoveConferenceData** . Para obtener más información sobre este parámetro, consulte el cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .

La herramienta elimina los datos de la reunión solo para las reuniones inactivas. Las reuniones activas (o reuniones en sesiones) no se pueden eliminar.

Esta herramienta debe ejecutarse desde un equipo que esté en el mismo grupo de servidores que el usuario de destino. El usuario cuyos datos de contenido de reunión se administran mediante esta herramienta debe estar hospedado en el mismo grupo de usuarios.

### <a name="output"></a>Output

Esta herramienta genera los resultados de cada una de las operaciones:

- Si se realiza una consulta, la herramienta genera la lista de todas las carpetas de datos de reuniones inactivas que el usuario tiene como organizador.

- Si se realiza una eliminación, la herramienta genera la lista de todas las carpetas de datos de la reunión cuyos datos se eliminarán.

### <a name="requirements"></a>Requirements

La herramienta debe ejecutarse en el mismo grupo de servidores donde está hospedada actualmente el organizador.

La herramienta debe ejecutarse con privilegios de administrador con acceso al almacén de archivos de contenido.

### <a name="examples"></a>Ejemplos

En la tabla siguiente se describen los parámetros, algunos de los cuales se usan en los ejemplos.

![Parámetros de la herramienta de datos Web conf.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

En el ejemplo anterior se muestra el funcionamiento de un comando de consulta. El resultado de un comando de este tipo sería una lista de todas las carpetas de contenido de reuniones que se verían afectadas por esta herramienta.

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

El ejemplo anterior es un ejemplo de un comando DELETE. El comando eliminar quitará todas las carpetas de reuniones inactivas de este usuario.

### <a name="summary"></a>Resumen

Esta herramienta puede ser un recurso útil para los administradores que necesitan un control más preciso sobre los datos de las reuniones de conferencia.


