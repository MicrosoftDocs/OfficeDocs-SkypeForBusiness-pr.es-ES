---
title: Documentación de herramientas del kit de recursos de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: En este tema se describen las herramientas del Kit de recursos de Skype Empresarial Server 2015, incluido el propósito de cada herramienta y ejemplos de su uso. El Kit de recursos de Skype Empresarial Server 2015 ayuda a facilitar las tareas rutinarias a los administradores de TI que implementan y administran Skype Empresarial Server 2015. Por ejemplo, la herramienta Web Conf Data se puede usar para controlar fácilmente los datos que cargan los usuarios durante una reunión en línea. La herramienta SEFAUtil se puede usar para configurar el reenvío delegado de llamadas y la respuesta para los usuarios. Animamos a los administradores de TI a usar estas herramientas para administrar Skype Empresarial Server 2015 de forma más eficaz.
ms.openlocfilehash: bf1a1d946c998466b118e0ab2038044a48d90970
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822040"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Documentación de herramientas del kit de recursos de Skype Empresarial Server 2015

En este tema se describen las herramientas del Kit de recursos de Skype Empresarial Server 2015, incluido el propósito de cada herramienta y ejemplos de su uso. El Kit de recursos de Skype Empresarial Server 2015 ayuda a facilitar las tareas rutinarias a los administradores de TI que implementan y administran Skype Empresarial Server 2015. Por ejemplo, la **herramienta Web Conf Data** se puede usar para controlar fácilmente los datos que cargan los usuarios durante una reunión en línea. La **herramienta SEFAUtil** se puede usar para configurar el reenvío delegado de llamadas y la respuesta para los usuarios. Animamos a los administradores de TI a usar estas herramientas para administrar Skype Empresarial Server 2015 de forma más eficaz.

## <a name="installation-of-the-resource-kit-tools"></a>Instalación de las herramientas del kit de recursos

Para instalar el Kit de recursos de Skype Empresarial Server 2015,OCSReskit.msi[ desde ](https://www.microsoft.com/download/details.aspx?id=52631) el Centro de descarga.

Ejecute **OCSResKit.msi** para realizar una instalación sencilla. El archivo .msi instala todas las herramientas en la ruta de acceso siguiente: **%Archivos de programa%\Skype Empresarial Server 2015\ResKit**. Las herramientas que son ejecutables independientes se encuentran en esta carpeta. Las herramientas que también tienen archivos compatibles se encuentran en sus propias subcarpetas.

## <a name="supported-environments"></a>Entornos admitidos

El Kit de recursos de Skype Empresarial Server 2015 debe instalarse en un servidor que cumpla las especificaciones necesarias para Skype Empresarial Server 2015, normalmente uno que se usa para ejecutar Skype Empresarial Server 2015.

## <a name="resource-kit-tools-overview"></a>Introducción a las herramientas del kit de recursos

A continuación se muestra una lista de las herramientas que se proporcionan en el Kit de recursos de Skype Empresarial Server 2015. En las secciones siguientes se incluye una descripción de cada herramienta, incluidos los requisitos y el uso de ejemplo.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Monitor de servicio de directivas de ancho de banda](resource-kit-tools.md#bpsm)

- [Analizador de uso de ancho de banda](resource-kit-tools.md#bua)

- [Call Parkometer](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Importar datos del servicio de almacenamiento](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Consola de usuario de búsqueda](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Visor de configuración de red](resource-kit-tools.md#NCV)

- [Response Group Agent Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [Migración de anuncios de números sin signo](resource-kit-tools.md#UNAM)

- [Web Conf Data](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

La herramienta de configuración del servicio de libreta de direcciones (ABSConfig) es una herramienta administrativa que ayuda a los administradores a personalizar la configuración del servicio de libreta de direcciones en Skype Empresarial Server 2015. Esta herramienta también permite a los administradores de Skype Empresarial Server 2015 restaurar la configuración predeterminada del servicio de libreta de direcciones.

### <a name="description"></a>Descripción

ABSConfig es una aplicación gráfica de interfaz de usuario que permite a los administradores configurar atributos de Servicios de dominio de Active Directory relacionados con el servicio de libreta de direcciones.

Los escenarios principales de la herramienta son los siguientes:

- Para permitir que los administradores asignen atributos de los Servicios de dominio de Active Directory a los atributos de Skype Empresarial Server 2015.

- Para permitir que los administradores especifiquen el atributo servicios de dominio de Active Directory que se incluirá o excluirá en los archivos del servicio de libreta de direcciones.

- Para permitir a los administradores restaurar la configuración predeterminada del servicio de libreta de direcciones.

La herramienta ABSConfig se puede iniciar mediante el ABSConfig.exe archivo. La herramienta se abre en la **pestaña Configurar atributos.** Esta tabla tiene opciones para asignar atributos de Servicios de dominio de Active Directory a los campos de atributo de Skype Empresarial Server 2015 y para especificar qué usuarios incluir o excluir en los archivos del servicio de libreta de direcciones en función de filtros de atributos específicos. También tiene opciones para personalizar el valor del número de teléfono que se incluirá en el archivo de la Libreta de direcciones. La **opción Restaurar valores predeterminados permite** a los administradores restaurar la configuración del servicio de libreta de direcciones a los valores predeterminados.

> [!NOTE]
> La nueva asignación de atributos de AD a diferentes nombres de campo OC solo funcionará para la descarga de archivos de libreta de direcciones y no es compatible con la consulta web de libreta de direcciones.

### <a name="output"></a>Salida

ABSConfig almacena la configuración del servicio de libreta de direcciones en la base de datos.

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Finalidad

ABSConfig proporciona una forma rápida y sencilla de personalizar el servicio de libreta de direcciones de Skype Empresarial Server 2015.

### <a name="requirements"></a>Requirements

#### <a name="computer"></a>Equipo

ABSConfig solo se puede ejecutar desde un equipo unido a un dominio que tenga instalado Skype Empresarial Server 2015. En el caso de Skype Empresarial Server 2015, Enterprise Edition, esta herramienta se puede ejecutar en cualquier servidor front-end que tenga habilitado el servicio de libreta de direcciones durante la instalación.

#### <a name="network"></a>Red

El equipo debe poder conectarse al grupo de servidores front-end y a la base de datos back-end.

#### <a name="software"></a>Software

Los siguientes componentes de software deben instalarse antes de ejecutar la herramienta ABSConfig:

- Skype Empresarial Server 2015

#### <a name="users"></a>Usuarios

Administradores que tienen los permisos necesarios para actualizar la implementación de Skype Empresarial Server 2015.

### <a name="examples"></a>Ejemplos

ABSConfig se puede iniciar **escribiendo** ABSConfig.exeen un símbolo del sistema. A continuación se muestra la interfaz de usuario de la herramienta ABSConfig.

![La ABSConfig.exe de búsqueda.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Resumen

La herramienta ABSConfig proporciona a los administradores una herramienta rápida y fácil de usar para personalizar el servicio de libreta de direcciones de Skype Empresarial Server 2015.

## <a name="bandwidth-policy-service-monitor"></a>Monitor de servicio de directivas de ancho de banda
<a name="bpsm"> </a>

La herramienta Bandwidth Policy Service Monitor está diseñada para permitir a los administradores ver una lista de lo siguiente:

1. Todos los servicios de directiva de ancho de banda de Skype Empresarial Server 2015 configurados (autenticación y núcleo) en la topología

2. Las conexiones que cada servicio realiza a otros servicios de directiva de ancho de banda y a los servidores perimetrales

3. Todos los vínculos configurados en el documento de configuración de red y el uso de ancho de banda en tiempo real según lo notificado por cada uno de los servicios de directiva de ancho de banda

### <a name="description"></a>Descripción

La herramienta Bandwidth Policy Service Monitor se implementa como una aplicación basada en GUI. Los administradores inician la herramienta ejecutando PDPMonUI.exe.

Cuando se inicia la herramienta, intenta detectar la lista de servicios de directiva de ancho de banda en la topología. Una vez realizada la actualización inicial, el panel situado a la izquierda de la ventana se rellena con una lista de servicios agrupados por los clústeres a los que pertenecen.

Cuando los administradores seleccionan un servicio de directiva de ancho de banda determinado, el panel de la derecha muestra la información sobre ese servicio en particular. Ese panel también tiene dos pestañas principales que muestran información.

#### <a name="machine-info-tab"></a>Pestaña Información del equipo

La **pestaña Información del** equipo muestra los detalles del servicio de directivas de ancho de banda seleccionado y la lista y el estado de todas las conexiones que realiza el servicio de directivas de ancho de banda seleccionado con otros servicios.

#### <a name="topology-info-tab"></a>Pestaña Información de topología

La **pestaña Información de** topología muestra una lista de todos los vínculos configurados en las opciones de configuración de red. Para cada vínculo, se muestra la capacidad de ancho de banda de audio y vídeo. Además, se muestra el ancho de banda que se usa actualmente, tanto en Kbps como en un porcentaje de la capacidad. La herramienta usa la codificación de color para resaltar vínculos que tienen un uso cercano a la capacidad, lo que permite a los administradores aislar rápidamente dichos vínculos.

> [!NOTE]
>  Si se produce un error en la herramienta Bandwidth Policy Service Monitor cuando  se conecta  a cualquiera de los servicios de directiva de ancho de banda configurados, la información de las pestañas Información del equipo e Información de topología no se rellenará. Sin embargo, es posible que la herramienta se conecte inicialmente pero, posteriormente, pierda su conexión con el servicio. En estos casos, es posible que los administradores vean información obsoleta. Hay una marca **de tiempo de** última actualización en cada una de las pestañas que puede permitir a los administradores ver cuándo se actualizaron los datos por última vez para un servicio de directivas de ancho de banda determinado.

### <a name="output"></a>Salida

No hay ningún resultado de la línea de comandos; la salida del programa está incluida en la interfaz gráfica de usuario (GUI) principal.

### <a name="purpose"></a>Finalidad

La finalidad de la herramienta Bandwidth Policy Service Monitor es permitir a los administradores ver el estado de cada uno de los servicios de directiva de ancho de banda definidos en la topología. Además, los administradores pueden ver el uso de ancho de banda en tiempo real para todos los vínculos definidos en el documento de configuración de red.

### <a name="requirements"></a>Requirements

La herramienta Bandwidth Policy Service Monitor debe ejecutarse en un equipo que forme parte de la topología de Skype Empresarial Server.

### <a name="summary"></a>Resumen

La herramienta Bandwidth Policy Service Monitor puede ser un recurso valioso para los administradores para que puedan inspeccionar el estado de todos los servicios de directiva de ancho de banda de la topología y, lo que es más importante, pueden obtener el uso de ancho de banda en tiempo real para los vínculos definidos en las opciones de configuración de red.

## <a name="bandwidth-utilization-analyzer"></a>Analizador de uso de ancho de banda
<a name="bua"> </a>

Bandwidth Utilization Analyzer es una herramienta que crea informes sobre diversas vistas de consumo de ancho de banda por parte de los puntos de conexión de UC a través de vínculos WAN en la red empresarial. Estos informes se pueden usar para comprender el patrón de consumo de ancho de banda actual y para ayudar en la planeación de la capacidad de ancho de banda.

### <a name="description"></a>Descripción

Bandwidth Utilization Analyzer se implementa como una aplicación basada en GUI. Esta herramienta genera informes específicamente para el uso de audio en toda la red y ayuda con la planeación de la capacidad. También itera en la capacidad de ancho de banda asignada a varios vínculos.

### <a name="output"></a>Salida

El Analizador de uso de ancho de banda proporciona gráficos al trazados de capacidad de ancho de banda y uso de audio para todos los vínculos WAN configurados en el sistema.

### <a name="purpose"></a>Finalidad

En cualquier implementación de voz y vídeo, es fundamental supervisar y comprender la tendencia del uso de ancho de banda del tráfico multimedia en la red empresarial. La herramienta Bandwidth Utilization Analyzer permite a un administrador lograr esto. Esta herramienta hace lo siguiente:

- Genera informes específicos para el uso de audio en toda la red

- Ayuda a planear e iteraciones de capacidad más eficaces en la capacidad de ancho de banda asignada a varios vínculos

El Analizador de uso de ancho de banda puede generar trazados gráficos de informes de uso y capacidad de ancho de banda; son los siguientes:

- Todos los vínculos WAN de la red empresarial

- Filtrado por vínculos WAN seleccionados que se han elegido

- Filtrado por vínculos WAN que han superado la capacidad de vínculos

- Filtrado por vínculos WAN que han usado poco el ancho de banda aprovisionado

- Filtrar por vínculos WAN que han llegado a niveles críticos (un uso de ancho de banda superior al 90 % de la capacidad de ancho de banda del vínculo WAN)

- Filtrado por tipo de vínculo WAN: vínculos de sitio de red, vínculos entre regiones y vínculos dentro de un sitio

- Filtrado por región de red

#### <a name="applications"></a>Aplicaciones

El Analizador de uso de ancho de banda tiene las siguientes dos aplicaciones (herramientas):

- **WanLinkLogCollector.exe** Esta herramienta permite al usuario introducir la información necesaria.

- **BandwidthUtilizationAnalyzer.xlsm** Un informe de software de hoja de cálculo de Microsoft Excel se inicia automáticamente mediante WanLinkLogCollector.exe. Esta aplicación permite al usuario aplicar filtros al informe, como se muestra más adelante en este artículo.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fases del uso del analizador de uso de ancho de banda

Existen dos fases al usar el Analizador de uso de ancho de banda:

- Recopilar registros, que se realiza mediante WanLinkLogCollector.exe

- Personalización de informes, que se realiza mediante BandwidthUtilizationAnalyzer.xlsm

    > [!IMPORTANT]
    > Se recomienda encarecidamente que BandwidthUtilizationAnalyzer.xlslos usuarios finales no puedan iniciar manualmente el archivo m.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Iniciar el analizador de uso de ancho de banda

Inicia WanLinkLogCollector.exe en el símbolo del sistema o mediante el Explorador de Windows.

 **Uso de WanLinkLogCollector.exe**

Hay tres pasos para usar WanLinkLogCollector.exe:

1. **Registrar la escala de tiempo** Proporcionar la escala de tiempo para la que se debe generar el informe

2. **Especificar los directorios de archivos** Proporcionar información de ubicación de archivos

3. **Recopilar los registros e iniciar el visor de informes** Ejecutar el comando para generar el informe

#### <a name="step-1---log-the-timeline"></a>Paso 1: registrar la escala de tiempo

El registro de la escala de tiempo permite al usuario de la herramienta especificar lo siguiente como se muestra en la ilustración siguiente.

1. **Fecha de inicio** Esta es la fecha de inicio de la escala de tiempo para la que se va a generar el informe; por ejemplo, 1 de agosto de 2010.

2. **Fecha de finalización** Esta es la fecha de finalización de la escala de tiempo para la que se va a generar el informe; por ejemplo, 30 de septiembre de 2010.

     ![Fechas de inicio y finalización en el uso del ancho de banda A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Paso 2: Especificar los directorios de archivos

El usuario puede especificar los siguientes directorios de archivos, como se muestra.

- **Ubicación de los archivos de registro del servidor** Ubicación de la carpeta donde se almacenan los registros del servidor de directivas de ancho de banda. Esto suele estar en \<fileserver\> \\<de FE \> \AppServerFiles\PDP.

- **Ubicación de almacenamiento temporal de archivos** Ubicación del archivo temporal donde se almacenan los archivos intermedios mientras se genera el informe.

    ![Directorios de archivos en el análisis de uso de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > Asegúrese de que el usuario de la herramienta tenga acceso suficiente a los registros del servidor y a la carpeta de almacén de archivos temporal.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Paso 3: recopilar los registros e iniciar el visor de informes

Para recopilar los registros e iniciar el visor de informes, haga clic **en Ejecutar** como se muestra a continuación. En este paso se recopilan los datos necesarios.

![Recopilación de datos en análisis de uso del ancho de banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Cuando la validación de entrada se realiza correctamente, se muestra el mensaje que se muestra a continuación.

![Registros recopilados de notificación en la Utili de ancho de banda](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Haga clic en **Aceptar**. BandwidthUtilizationAnalyzer.xlsm se inicia automáticamente. Siga las instrucciones del cuadro de mensaje. Para obtener más información, **consulte BandwidthUtilizationAnalyzer.xlsm** en la sección siguiente.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Usar BandwidthUtilizationAnalyzer.xlsm

1. Cuando BandwidthUtilizationAnalyzer.xlsm se inicie automáticamente, haga clic **en Actualizar** como se muestra a continuación.

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Cuando se abra una carpeta de archivos, seleccione consolidated.csv la ubicación especificada en el cuadro de mensaje, como se muestra a continuación. También muestra la ubicación como **C:\Temp**.

     ![Abrir una carpeta en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Haga clic en **Importar**.

4. El trazado gráfico se genera automáticamente. Está disponible cuando desaparece el puntero de trabajo en segundo plano.

     ![Aplicar filtros en la vista Informe.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Aplicar filtros a la vista Informe

Los filtros que se pueden aplicar a la vista de informe, como se muestra a continuación, se describen de la siguiente manera:

![Aplicar filtros en la vista Informe.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Nombre** Filtra por vínculos WAN (el filtro está en el lado derecho del gráfico). El prefijo indica los siguientes tipos de vínculos; ver el cuadro vertical (azul):

   - **S Site** El vínculo WAN de un sitio de red a una región de red

   - **IS entre sitios** El vínculo WAN entre dos sitios de red

   - **R entre regiones** El vínculo WAN entre dos regiones de red

2. **Límite superado** Filtrar por vínculos WAN cuyo uso de ancho de banda es superior a la capacidad de ancho de banda

3. **Niveles críticos** Filtrar por vínculos WAN cuyo uso de ancho de banda ha alcanzado el 90 % o más de la capacidad de ancho de banda

4. **Infrautilmente utilizado** Filtrar por vínculos WAN cuyo uso de ancho de banda ha sido inferior al 25 % de la capacidad de ancho de banda

5. **Tipo de vínculo** Filtre por los siguientes tipos de vínculos WAN:

   - **Tipo de sitio de** red

   - **Tipo entre sitios**

   - **Tipo de vínculo entre regiones**

6. **Región** Filtrar por región de red

Las siguientes figuras muestran los filtros descritos anteriormente.

Filtrar por **nombre**. Seleccione la lista de vínculos que deben mostrarse en el gráfico.

![Filtrado por nombre en BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filtrar por **límite superado.** Seleccione **True** para aplicar el filtro.

![Filtrado por límite superado.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtrar por **niveles críticos**. Seleccione **True** para aplicar el filtro.

![Filtrado por niveles críticos.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtrar por **Under utilizado**. Seleccione **True** para aplicar el filtro.

![Filtrado por Infrautilmente utilizado.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtrar por **tipo de vínculo.** Seleccione el tipo o los tipos que deben mostrarse.

![Filtrado por tipo de vínculo.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtrar por **región**. Seleccione una lista de regiones cuyos vínculos deben mostrarse.

![Filtrado por región.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Requirements

- .NET Framework 3.5

- Microsoft Excel 2010 o Excel 2007

### <a name="summary"></a>Resumen

El Analizador de uso de ancho de banda se usa para trazar el uso del ancho de banda de audio para el tráfico de UC a través de la red. Esta herramienta también se puede usar para informar del uso del ancho de banda de vídeo en la red.

## <a name="call-parkometer"></a>Call Parkometer
<a name="callpark"> </a>

Call Parkometer es una aplicación de línea de comandos que proporciona fácil acceso a la base de datos de órbitas de estacionamiento de llamadas.

### <a name="description"></a>Descripción

Call Parkometer es una herramienta para realizar un seguimiento de las llamadas estacionadas actualmente. También recopila estadísticas sobre órbitas y uso del servidor de estacionamiento de llamadas (CPS). Esta herramienta de línea de comandos proporciona acceso de lectura y escritura a la órbita de CPS SQL Server base de datos desde un equipo local o conectado remotamente.

Todas las opciones son mutuamente excluyentes. La sintaxis de la línea de comandos es la siguiente:

- **Parámetro -o:** enumera todos los intervalos de órbitas configurados para este grupo.

- **Parámetro -n:** enumera todas las órbitas usadas actualmente en este grupo de servidores. La información que se muestra es la siguiente:

  - Identificador uniforme de recursos (URI) de SIP del estacionado y el aparcado.

  - Nombre de host del CPS donde está estacionada la llamada.

  - Marca de tiempo de cuándo se estacionó la llamada.

- **Parámetro -f:** enumera el número de órbitas disponibles actualmente en el grupo de servidores.

- **-r \<n\>** enumera las \<n\> últimas llamadas estacionadas. La información que se muestra es la siguiente:

  - URI de SIP de estacionado.

  - URI sip de Sip de Sip de Sip.

  - Nombre de host del CPS donde se estacionó la llamada.

  - Marca de tiempo de cuándo se recuperó o se soltó la llamada.

- **-t \<n\>** : prueba la reserva de una órbita en la base de datos para mostrar la aleatoriedad de los números de órbita asignados.

### <a name="output"></a>Salida

Según los parámetros de entrada especificados en un símbolo del sistema, Call Parkometer muestra la siguiente salida:

- Todos los intervalos de órbitas configurados para este grupo

- Llamadas estacionadas actualmente

- Número de órbitas libres (disponibles)

- Llamadas estacionadas recientemente

- Órbitas reservadas para probar valores de órbita uniformes y aleatorios

### <a name="purpose"></a>Finalidad

El propósito de la herramienta CPS es proporcionar acceso de línea de comandos a la base de datos de CPS. El administrador puede ver el uso de CPS y determinar el número de órbitas asignadas a un grupo de servidores.

### <a name="requirements"></a>Requirements

No hay requisitos si esta herramienta se ejecuta en el mismo equipo que ejecuta CPS. Si esta herramienta se ejecuta en un equipo remoto, la base de datos SQL Server usada por Skype Empresarial Server 2015 debe configurarse para permitir el acceso remoto. Call Parkometer debe configurarse con una SQL Server de conexión de base de datos para conectarse al grupo de servidores SQL Server. Esta SQL Server de conexión de base de datos se define en el archivo de configuración, **parkometer.exe.config**. Debe colocarse en el mismo directorio donde se parkometer.exe ubicación. El siguiente archivo XML es un ejemplo de una parkometer.exe.config. Los parámetros que se deben configurar son el nombre de usuario (por ejemplo, mydomain\Administrator), la contraseña (por ejemplo, mypassword) y el nombre de host (por ejemplo, myserver).

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

Intervalos de órbitas implementados: el parámetro -o enumera todos los intervalos de órbitas configurados para este grupo de servidores, como se muestra

![Intervalos de órbitas en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Llamadas estacionadas actualmente: el parámetro -n enumera todas las órbitas usadas actualmente en este grupo como se muestra

![Llamadas estacionadas actualmente en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Número de órbitas libres: el parámetro -f muestra el número de órbitas disponibles actualmente en el grupo de servidores, como se muestra

![Órbitas libres en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Llamadas estacionadas recientemente: el parámetro -r \<n\> enumera las \<n\> últimas llamadas estacionadas como se muestra

![Llamadas estacionadas recientemente en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Reserva de órbita de prueba: el parámetro -t \<n\> prueba la reserva de una órbita en la base de datos como se muestra

![Prueba reservas de órbitas en Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Resumen

Call Parkometer es una herramienta de línea de comandos que proporciona información detallada sobre el servidor de estacionamiento de llamadas.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Descripción

DBAnalyze es una herramienta de línea de comandos que ayuda a los administradores a recopilar informes de análisis sobre las bases de datos de Skype Empresarial Server 2015. DBAnalyze tiene los siguientes modos: diagnóstico, datos de usuario, conferencia, M MCU y fragmentación de disco:

- **Modo de diagnóstico** Crea un informe que incluye información sobre las tablas (número de registros, fragmentación, tamaño de datos y tamaño del índice), los tamaños de los archivos de registro y datos, el último tiempo de copia de seguridad, la distribución de contactos entre los servidores que ejecutan Microsoft Office Communications Server, el número medio de permisos, contactos, contenedores, suscripciones, publicaciones, puntos de conexión por usuario, cualquier usuario que no esté adecuadamente albergado, usuarios que no se pueden enrutar, el número medio de conferencias organizadas por usuario, conferencias programadas, conferencias activas y la versión de la base de datos.

    > [!NOTE]
    > La ejecución del modo de diagnóstico puede afectar al rendimiento del servidor.

- **Modo de datos de usuario** Informa de los datos de contacto, contenedor, suscripción, publicación, permiso y grupo de contactos de un usuario especificado o de los usuarios que tienen ese usuario en sus listas de contactos y permisos. Este modo también informa de los datos de resumen de las conferencias que un usuario organiza o a las que se invita.

- **Modo de conferencia** Informa de los datos detallados de una conferencia específica, incluidos todos los detalles de la programación de la conferencia, la lista de invitados, la lista de tipos de medios permitidos para la conferencia, las MCU activas (unidades de control multipunto), la lista de participantes activos y el estado de señalización de cada participante.

- **Descodificar id. de reunión** Descodifica un identificador de reunión de la red telefónica conmutada (RTC) especificado por el modificador **/pstnid,** pero que no se conecta al back-end para obtener información detallada.

- **Resolver conferencia** Descodifica un identificador de reunión RTC especificado por el modificador **/pstnid** y muestra información sobre la conferencia indicada por el identificador.

- **Modo M MCUs** Notifica el identificador, el tipo de medio, la dirección URL, el estado del latido, la carga de conferencia y la carga de participantes para cada MCU del grupo.

- **Modo de fragmentación de disco** Muestra el estado de fragmentación de todos los discos.

Esta herramienta se puede usar para diagnosticar diversos problemas o para ayudar a los administradores con la planeación de la capacidad. Por ejemplo, si la mayoría de los usuarios que están en el servidor A eligen los usuarios que están en el servidor B como sus contactos, el administrador puede mover los usuarios del servidor A al servidor B para reducir el tráfico entre servidores.

### <a name="output"></a>Salida

Esta herramienta genera informes predefinidos sobre la base de datos de Skype Empresarial Server 2015. **Ruta** de acceso: %ProgramFiles%\Skype Empresarial Server 2015\Reskit

### <a name="purpose"></a>Finalidad

Para instalar Dbanalyze.exe, cópielo en una carpeta local y, a continuación, ejecute la herramienta. Para usar la herramienta, ejecute el siguiente comando desde la línea de comandos. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` A continuación se muestran las descripciones de las opciones de la línea de comandos.

![Opciones de línea de comandos para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Requirements

 **Equipo** DBAnalyze solo se puede ejecutar desde un equipo unido a un dominio que tenga instalado Skype Empresarial Server 2015.

 **Red** El equipo debe poder conectarse a la base de datos back-end.

 **Software** Los componentes de software de Skype Empresarial Server 2015 deben instalarse antes de ejecutar DBAnalyze.

 **Usuarios** En la tabla siguiente se muestran los administradores que tienen los permisos necesarios para acceder a las bases de datos de Skype Empresarial Server 2015.

![Tabla de permisos para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Se requiere una cuenta de administrador local **para el modo /report:disk.**

### <a name="examples"></a>Ejemplos

A continuación se muestran ejemplos de comandos Dbanalyze.exe válidos:

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Resumen

DBAnalyzer proporciona a los administradores un análisis rápido y fácil de las bases de datos de Skype Empresarial Server 2015.

## <a name="import-storage-service-data"></a>Importar datos del servicio de almacenamiento
<a name="Issd"> </a>

La herramienta del kit de recursos ImportStorageServiceData permite volver a importar los datos de colas y puntos de conexión que se vaciaron del servicio de almacenamiento (LYSS) de nuevo en el servicio de almacenamiento.

### <a name="description"></a>Descripción

Los datos vaciados del servicio de almacenamiento podrían haber sido automáticos (periódicos) según el estado del elemento de cola o el tamaño de la base de datos. Podría haber ocurrido debido a la invocación manual del cmdlet de conmutación por error del grupo de servidores o al cmdlet StorageServiceFullFlush (que invoca el cmdlet de conmutación por error del grupo de servidores). Tenga en cuenta que lo ideal es no volver a importar los datos si el tamaño de la base de datos del servicio de almacenamiento (LYSS) en los front-ends está por encima del nivel normal, ya que es probable que esto haga que se vuelvan a exportar más datos. Además, los problemas que podrían haber contribuido a errores que provocaron el crecimiento de la cola del servicio de almacenamiento primero deben resolverse (por ejemplo, errores de extremo de Exchange, problemas de red u otros problemas).

 **Escenario 1: durante la conmutación** por error del grupo, los archivos pueden vaciarse del servicio de almacenamiento para cada front-end. Una vez completada la conmutación por error, se debe ejecutar la herramienta para volver a importar los datos.

 Escenario **2: los** datos se vacían automáticamente cada día o en respuesta a que la base de datos del servicio de almacenamiento supera ciertos umbrales de tamaño (por ejemplo, 60%, 80%, 90% completo). El administrador debe volver a importar de forma rutinaria estos datos vaciados automáticamente. En la situación anterior, si no se implementa el paquete SCOM de supervisión, hay eventos para el servicio de almacenamiento de Skype Empresarial Server relacionados con los datos que se vacían del servicio de almacenamiento. Los IDs de evento de 32075 (se ha iniciado la operación de vaciado completo), 32076 (se ha completado el vaciado completo), 32082 (vaciado del nivel de mantenimiento iniciado), 32083 (vaciado de nivel de mantenimiento completado), 32089 (se ha vaciado debido a rellenar la base de datos). Ten en cuenta que estos identificadores de evento corresponden a la versión RTM. Cuando un administrador ve estos eventos, significa que hay archivos que se han vaciado. Estos datos deben volver a importarse de forma rutinaria con esta herramienta, por ejemplo, una vez por semana.

Para la versión del servicio en línea, si se implementa el paquete SCOM de seguimiento de estado para Skype Empresarial Server, se pueden generar nuevas alertas que piden al administrador que vuelva a importar los datos vaciados en el servicio de almacenamiento. Habrá un evento correspondiente en el registro de eventos en el servidor front-end que desencadenó la alerta. El evento mostrará una descripción de la ruta de acceso principal en la que se encuentran los archivos de datos vaciados, así como el número de archivos que hay que cumplen los criterios de alerta. El criterio de alerta es que hay X o más archivos en la ruta de acceso principal concreta que tienen al menos días de antigüedad Y (donde X e Y están preestablecidos dentro de StorageService, pero se pueden invalidar cambiando el archivo APPCONFIG). A continuación se muestran dos ejemplos de eventos que pueden desencadenar la alerta de estado, con la diferencia de que su ruta de acceso principal. Una posibilidad está en el recurso compartido de archivos del servicio web, mientras que la otra posibilidad es el directorio de datos de aplicación local de cada front-end. ( por ejemplo c:\ProgramData\Microsoft\Skype Empresarial Server 2015\StorageService ). A continuación, el administrador ejecutará esta herramienta de reskit.

Esta herramienta aumentará la carga de CPU e E/S en el front-end en el que se ejecuta, así como en otros front-end, en la situación de que los datos no son propiedad del front-end en el que se ejecuta la herramienta. Se recomienda ejecutar esta herramienta cuando los front-ends no están bajo una carga intensa de CPU e E/S, por ejemplo fuera de las horas de mayor actividad. En segundo lugar, esta herramienta puede importar entre 2 y 3 minutos para importar un archivo de datos. Ten esto en cuenta al calcular cuánto tiempo se va a ejecutar la herramienta. El archivo de registro detallado generado por la herramienta aparecerá de forma predeterminada en el almacén de archivos. Elimínelo si no se han notificado errores, ya que el archivo de registro puede ser decenas de MB o más.

![Eventos de registro de eventos del servidor de almacenamiento de ejemplo.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Requirements

Instale las herramientas del Kit de recursos de Skype Empresarial Server 2015. La herramienta se ejecuta en equipos unidos a un dominio donde están instalados Skype Empresarial Server y el Shell de administración de Skype Empresarial Server. La herramienta usa un cmdlet del Shell de administración para identificar todos los servidores front-end del grupo. En segundo lugar, la herramienta debe ejecutarse desde una máquina del grupo de servidores que tenga instalada la base de datos **RtcLocal.** Esta base de datos la usa la herramienta para recuperar la ubicación del recurso compartido de archivos WEBSERVICE para el grupo de servidores. Además, antes de usar la herramienta, cada servidor front-end debe habilitar primero la comunicación remota de Windows PowerShell mediante **Enable-PSRemoting** en cada servidor front-end, así como la máquina desde la que se ejecuta la herramienta. De lo contrario, Windows PowerShell comandos remotos de esta herramienta producirán un error. Windows PowerShell la comunicación remota se puede desactivar en todos los servidores front-end del grupo una vez finalizado. Por último, la cuenta o credencial que invoca a la herramienta debe tener permiso de lectura y escritura en el recurso compartido de archivos de servicio web para el grupo en el que se ejecuta esta herramienta. De lo contrario, se producirá un error en la herramienta con errores de permiso de E/S.

> [!NOTE]
> En Windows Server 2012, Windows PowerShell la comunicación remota está habilitada de forma predeterminada, pero no en el sistema operativo Windows Server 2008.

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

La herramienta LCSSync ayuda a implementar el software de comunicaciones de Skype Empresarial Server 2015 en un entorno de varios bosques. Esta herramienta se usa para sincronizar usuarios y grupos de diferentes bosques de usuarios como un objeto de contacto de Servicios de dominio de Active Directory con un bosque central donde está instalado Skype Empresarial Server 2015.

### <a name="description"></a>Descripción

 LCSSync usa los objetos de contacto sincronizados de Servicios de dominio de Active Directory en el bosque central para habilitar a los usuarios para Skype Empresarial Server. Para proporcionar el inicio de sesión único, la cuenta de usuario principal debe asignarse al objeto de contacto de Servicios de dominio de Active Directory en el bosque central de Skype Empresarial Server 2015. Esta herramienta ayuda a realizar esa asignación. Esta herramienta proporciona plantillas para crear agentes de administración en Microsoft Identity Integration Server.

### <a name="summary"></a>Resumen

La herramienta LCSSync ayuda a implementar Skype Empresarial Server 2015 en un entorno de varios bosques.

## <a name="lookup-user-console"></a>Consola de usuario de búsqueda
<a name="LUC"> </a>

La herramienta LookupUserConsole muestra información interna de enrutamiento de Skype Empresarial Server sobre usuarios específicos. Esta información puede ser útil para que el soporte técnico de Microsoft personal pueda diagnosticar problemas de implementación y enrutamiento.

### <a name="description"></a>Descripción

 Al ejecutar LookupUserConsole.exe se abrirá un símbolo del sistema que acepta direcciones SIP e intenta mostrar información de enrutamiento interna de Skype Empresarial Server relacionada con ellas. Escriba **exit** para salir de la herramienta LookupUserConsole.

### <a name="requirements"></a>Requirements

Instale el kit de recursos de Skype Empresarial Server 2015. La herramienta se ejecuta en equipos unidos a un dominio donde está instalado Skype Empresarial Server.

### <a name="examples"></a>Ejemplos

C:\Archivos de programa\Skype Empresarial Server 2015\ResKit \>LookupUserConsole.exe

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

La herramienta MSTurnPing permite a un administrador del software de comunicaciones de Skype Empresarial Server 2015 comprobar el estado de los servidores que ejecutan los servicios de autenticación perimetral y de audio y vídeo, así como los servidores que ejecutan los Servicios de directivas de ancho de banda en la topología.

### <a name="description"></a>Descripción

La herramienta MSTurnPing permite a un administrador del software de comunicaciones de Skype Empresarial Server 2015 comprobar el estado de los servidores que ejecutan los servicios de autenticación perimetral y de audio y vídeo, así como los servidores que ejecutan los Servicios de directivas de ancho de banda en la topología.

La herramienta permite al administrador realizar las siguientes pruebas:

1. Prueba del servidor perimetral A/V: La herramienta realiza pruebas en todos los servidores perimetrales A/V de la topología mediante lo siguiente:

   - Comprobar que el servicio de autenticación de audio y vídeo de Skype Empresarial Server se ha iniciado y puede emitir las credenciales adecuadas.

   - Comprobar que el servicio perimetral de audio y vídeo de Skype Empresarial Server se ha iniciado correctamente y puede asignar correctamente los recursos en el perímetro externo.

2. Prueba del servicio de directivas de ancho de banda: la herramienta realiza pruebas en todos los servidores que ejecutan los servicios de directivas de ancho de banda en la topología mediante lo siguiente:

   - Comprobar que el servicio de directiva de ancho de banda (autenticación) de Skype Empresarial Server se ha iniciado y puede emitir las credenciales adecuadas.

   - Comprobar que el servicio de directiva de ancho de banda (core) de Skype Empresarial Server se ha iniciado y puede realizar la comprobación de ancho de banda correctamente.

Esta herramienta debe ejecutarse desde un equipo que forma parte de la topología y tiene instalado el almacén local.

### <a name="output"></a>Salida

La herramienta genera los resultados de cada una de las operaciones.

- Si se **realiza la prueba AudioVideoEdgeServer,** los resultados de la herramienta son los siguientes:

  - Los resultados de las pruebas de los equipos que proporcionan el servicio de autenticación de audio y vídeo de Skype Empresarial Server 2015 en la topología

  - Los resultados de las pruebas de los equipos que proporcionan el servicio perimetral de audio y vídeo de Skype Empresarial Server 2015 en la topología

- Si se realiza la prueba **BandwidthPolicyServer,** los resultados de la herramienta son los siguientes:

  - Los resultados de las pruebas de los equipos que proporcionan el servicio de directiva de ancho de banda (autenticación) de Skype Empresarial Server 2015 en la topología

  - Los resultados de las pruebas de los equipos que proporcionan el servicio de directiva de ancho de banda (core) de Skype Empresarial Server 2015 en la topología

### <a name="requirements"></a>Requirements

- Esta herramienta debe ejecutarse desde un equipo que se encuentra en la topología y que tiene el almacén local.

- La herramienta debe ejecutarse como administrador que tenga acceso al almacén local.

### <a name="examples"></a>Ejemplos

A continuación se muestra un ejemplo de la entrada de la herramienta.

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Resumen

Esta herramienta puede ser un recurso valioso para los administradores de Skype Empresarial Server 2015 que desean comprobar el estado de los servidores que ejecutan servicios de directiva de audio/vídeo y ancho de banda.

## <a name="network-configuration-viewer"></a>Visor de configuración de red
<a name="NCV"> </a>

Los administradores de software de comunicaciones de Skype Empresarial Server 2015 pueden usar el Visor de configuración de red para ver la topología de red de control de admisión de llamadas (CAC) para una empresa que está aprovisionada para permitir sesiones de comunicación en tiempo real, como llamadas de voz o vídeo en función de la capacidad de ancho de banda especificada. Los administradores de Skype Empresarial Server 2015 definen directivas de CAC, que son aplicadas por los servicios de directiva de ancho de banda que se instalan con Skype Empresarial Server 2015.

### <a name="description"></a>Descripción

El Visor de configuración de red (NetworkConfigurationViewer.exe) permite a los administradores realizar las siguientes tareas:

- Cargar y ver la topología de red de CAC desde una implementación de Skype Empresarial Server 2015 en un formato gráfico.

- Cargue y vea la topología de red de CAC desde un archivo de registro del servidor de directivas de ancho de banda en un formato gráfico.

- Guarde y almacene la topología de red de CAC en un formato XML en el disco.

- Guarde y almacene el diagrama de topología de red de CAC en formato JPG o BMP.

- Ver los datos de configuración de topología de red de CAC.

- Ver la topología de red de CAC en un estilo de vista de árbol.

- Definir conectores personalizados para vínculos de topología de red de CAC (por ejemplo, vínculos de sitio a región, de región a región y de sitio a sitio).

- Ver información del sitio de topología de red de CAC, información de región y directivas de ancho de banda aprovisionado y vínculos de red.

### <a name="purpose"></a>Finalidad

Ver vínculos de topología de red de CAC empresariales en una interfaz gráfica.

### <a name="examples"></a>Ejemplos

 Cargar y ver la topología de red de CAC desde una implementación de Skype Empresarial **Server 2015** en formato gráfico: los administradores de Skype Empresarial Server 2015 pueden cargar y ver la configuración de topología de red de CAC en cualquier equipo de Skype Empresarial Server 2015 mediante la opción Descargar configuración de red, como se muestra en la figura siguiente.  La herramienta no podrá descargar ni ver dicha configuración cuando se implemente en un equipo que no tenga conectividad con el almacén de configuración de Skype Empresarial Server 2015.

![Descargar la configuración de red.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Cargar y ver la topología de red de CAC desde un archivo de** registro del servidor de directivas de ancho de banda en formato gráfico: Los servidores de directivas de ancho de banda de Skype Empresarial Server 2015 guarda la topología de red de CAC como parte del mecanismo de registro en la ubicación del recurso compartido de archivos de Skype Empresarial Server 2015. Los administradores de Skype Empresarial Server 2015 pueden ver  este archivo en un formato gráfico mediante la opción Configuración de red abierta, como se muestra a continuación.

![Abrir un archivo de registro del servidor de directivas de ancho de banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Guarde y almacene la topología de red de CAC en un formato XML en el disco: los administradores de Skype Empresarial Server 2015 pueden guardar el archivo de configuración de topología de red de CAC en formato XML mediante la opción Guardar una copia de configuración de red, como se muestra **a** continuación. A continuación, el archivo de configuración guardado se puede usar sin conexión con fines de visualización gráfica.

![Guardar la configuración de red como un archivo XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Guardar y almacenar el diagrama de topología de red cac en formato JPG o BMP: los administradores de Skype Empresarial Server 2015 pueden guardar la configuración de topología de red de CAC en un formato gráfico (formatos de archivo JPG y BMP) mediante el diagrama Guardar configuración de red como opción de imagen, como se muestra a continuación. 

![Guardar la configuración de red como una imagen.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Ver los datos de configuración de topología de red de CAC:</strong> Los administradores de Skype Empresarial Server 2015 pueden ver los datos de configuración de red relacionados, como regiones de red, sitios de red, perfiles de ancho de banda y direcciones IP de subred de sitio en un formato textual mediante la opción Ver datos de configuración de red, como se muestra a continuación.

![Visualización de datos de configuración de red.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Ver la topología de red de CAC en un estilo de vista de árbol:** Los administradores de Skype Empresarial Server 2015 pueden ver los datos de configuración de red relacionados en un estilo de vista de árbol gráfico mediante el panel de control situado a la izquierda de la ventana de herramientas, como se muestra a continuación.

![Visualización de datos de configuración de red en una vista de árbol.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Definir conectores personalizados para vínculos** de topología de red de CAC (como vínculos de sitio a región, de región a región y de sitio a sitio): Los administradores de Skype Empresarial Server 2015 pueden definir conectores gráficos personalizados para vínculos WAN de configuración de red de CAC mediante la opción Configuración, como se muestra a continuación. Esto ayuda a diferenciar entre varios tipos de vínculos de red que se aprovisionan en la configuración de red.

![Herramientas](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Ver la información del sitio de topología de red de CAC, la información de región y las directivas de ancho de banda aprovisionado:** Los administradores de Skype Empresarial Server 2015 pueden ver información de región de red de CAC relacionada, información del sitio e información de aprovisionamiento de ancho de banda de CAC mediante las opciones que se muestran a continuación. (Por ejemplo, haga clic **en Información** en una región de red o un objeto de sitio de red).

![Definición de conectores personalizados para la red.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Resumen

Esta herramienta puede ser un recurso valioso para los administradores de Skype Empresarial Server 2015 que quieren ver la topología de red de CAC para su implementación en un formato gráfico.

## <a name="response-group-agent-live"></a>Response Group Agent Live
<a name="RGAL"> </a>

La aplicación Grupo de respuesta ofrece a los agentes la capacidad de obtener acceso a información útil en tiempo real mediante su servicio web integrado. Desafortunadamente, no hay ninguna vista gráfica de estos datos disponible fuera de la aplicación. La herramienta Response Group Agent Live Resource Kit soluciona este problema proporcionando una forma gráfica y sencilla de acceder a esta información, mejorada con información de software de comunicaciones de Skype Empresarial en tiempo real, como la presencia de otros agentes.

### <a name="description"></a>Descripción

Response Group Agent Live es una aplicación de Windows que proporciona funciones de inicio y de salida, así como información en tiempo real (como la pertenencia a grupos y el número actual de llamadas) a los agentes de Grupo de respuesta. Está pensado para ser una versión mejorada de la página Grupos de agentes (accesible desde Skype Empresarial.

### <a name="purpose"></a>Finalidad

La aplicación Grupo de respuesta pone en cola las llamadas entrantes y, a continuación, las enruta a grupos de agentes. Para tomar decisiones fundamentadas sobre las llamadas al servicio, los agentes pueden acceder a información en tiempo real sobre sus grupos de agentes, como qué otros agentes están disponibles y cuántas llamadas están esperando en cada cola. Esta información, accesible inicialmente solo a través del servicio de Grupo de respuesta, está disponible de forma intuitiva por el Agente de grupo de respuesta Live.

#### <a name="features"></a>Características

La herramienta Response Group Agent Live se basa en el servicio grupo de respuesta y el SDK de Skype Empresarial Server 2015. Proporciona a los agentes del grupo de respuesta la información y las capacidades que están disponibles desde el servicio de grupo de respuesta (como la pertenencia a grupos, la presencia de otros agentes y el número de llamadas en espera).

En la figura siguiente se muestra la interfaz principal de Response Group Agent Live.

![La herramienta Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Las tres características principales siguientes están disponibles para los agentes en Response Group Agent Live:

- **Inicio y salida:** Al contrario que la página Grupos de agentes (accesible desde Skype Empresarial Server 2015), Response Group Agent Live solo permite a los agentes iniciar o cerrar sesión en todos los grupos de agentes a la vez. Esta aplicación proporciona tres formas rápidas para que los agentes inicien o cerrar sesión:

  - Haga clic en los botones de inicio/salida (verde y rojo) dentro de la aplicación.

  - Haga clic con el botón secundario en el icono de bandeja del sistema y seleccione iniciar o cerrar sesión.

  - Uso de métodos abreviados de teclado configurables.

- **Pertenencia a grupos:** Cuando se selecciona un grupo de agentes, Response Group Agent Live muestra la lista de agentes de este grupo en el panel derecho. Si Skype Empresarial Server 2015 se ejecuta en el mismo equipo que esta aplicación, la información de presencia y la tarjeta de contacto se muestran en Response Group Agent Live. Los agentes pueden enviar una mensajería instantánea o llamar a otros agentes directamente desde allí.

- **Estadísticas en tiempo real:** Response Group Agent Live proporciona estadísticas en tiempo real para todos los grupos de agentes. La frecuencia de actualización es de un minuto. Cuando un grupo de respuesta responde a una llamada, se agrega un indicador visual junto al nombre del grupo con el número actual de llamadas en cola. Pausar el puntero sobre un grupo también muestra el tiempo de espera más largo.

### <a name="requirements"></a>Requirements

Response Group Agent Live requiere .NET Framework 4.0. Además, para aprovechar las características de presencia y tarjeta de contacto, Skype Empresarial debe instalarse localmente (y estar en ejecución).

#### <a name="configuration"></a>Configuración

Response Group Agent Live se puede personalizar según las preferencias individuales mediante el cuadro de diálogo Opciones de la aplicación. Además, el administrador puede definir la dirección de host predeterminada editando directamente la propiedad defaultHostAddress del archivo RGAgentLive.exe.config host.

En la figura siguiente se muestra el cuadro de diálogo Opciones que los agentes pueden usar para configurar la dirección host y las teclas de método abreviado. Para obtener acceso a este cuadro de diálogo, haga clic en el botón Opciones situado en la parte superior derecha de la interfaz principal.

![Cuadro de diálogo Opciones de Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Las siguientes tres configuraciones diferentes se pueden personalizar en la configuración de Response Group Agent Live:

- Dirección de host: suele ser el FQDN del grupo de servidores web que pertenece al grupo de servidores principal del agente. La dirección exacta del servicio grupo de respuesta se deriva automáticamente en segundo plano de esta información (anexando la ruta de acceso correcta después del host).

- Accesos directos: se pueden personalizar los accesos directos exactos para iniciar/cerrar sesión. La única limitación es que ambos accesos directos deben contener la tecla "Logotipo de Windows" (además de al menos otra tecla).

- Empezar con Windows: la aplicación se puede configurar para iniciarse automáticamente con Windows.

### <a name="examples"></a>Ejemplos

En la figura siguiente se muestra cómo llamar o enviar una mensajería instantánea a otro agente haciendo clic con el botón secundario en el contacto en el panel derecho.

![Realizar una llamada o enviar una mensajería instantánea.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

En la figura siguiente se muestra cómo Response Group Agent Live muestra el número actual de llamadas en la cola y el tiempo de espera más largo entre todas estas llamadas entrantes.

![Visualización de la información de la cola.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Resumen

El inicio y cierre de sesión rápidos, la pertenencia a grupos y las estadísticas básicas en tiempo real son características de agente de Grupo de respuesta interesantes que solo están disponibles fuera de la aplicación desde el servicio de grupo de respuesta. Con la herramienta Response Group Agent Live Resource Kit, los administradores de Skype Empresarial Server 2015 pueden proporcionar a sus agentes una aplicación de Windows que les permita realizar tareas de forma más rápida y gráfica.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (activación de características de extensión secundaria) es una herramienta de línea de comandos que permite a los administradores de software de comunicaciones de Skype Empresarial Server 2015 y a los agentes del departamento de soporte técnico configurar llamadas delegadas, desviamiento de llamadas, llamadas simultáneas, configuración de llamadas de equipo y atención de llamadas grupales en nombre de un usuario de Skype Empresarial Server 2015. La herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se publica para un usuario determinado. La herramienta SEFAUtil permite al administrador habilitar, deshabilitar o modificar el reenvío de llamadas o las llamadas simultáneas en nombre del usuario. El administrador puede especificar el destino (en forma de URI de SIP) o usar un destino que el usuario ya haya publicado. Esta herramienta también permite a los administradores agregar o quitar delegados o miembros del grupo de llamada de equipo en nombre del usuario. Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3.0 y requiere que los administradores creen una aplicación de confianza en el almacén de administración central para SEFAUtil.

SEFAUtil (activación de características de extensión secundaria) permite a los administradores y agentes del departamento de soporte técnico de Skype Empresarial Server 2015 configurar las llamadas delegadas, el reenvío de llamadas, las llamadas simultáneas, la configuración de llamadas de equipo y la atención de llamadas grupales en nombre de un usuario de Skype Empresarial Server 2015. Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se publica para un usuario determinado.

### <a name="description"></a>Descripción

La versión actual de SEFAUtil es solo una herramienta de línea de comandos; no hay ninguna interfaz gráfica de usuario compatible. Esta herramienta se basa en la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3.0. Las características de esta herramienta permiten a los administradores y agentes del departamento de soporte técnico hacer lo siguiente:

- Ver todas las opciones de enrutamiento de llamadas de un usuario (incluye el reenvío de llamadas, la delegación, las llamadas simultáneas, la llamada de equipo y la atención de llamadas grupales)

- Habilitar/deshabilitar/modificar la configuración de reenvío de llamadas (incluye el destino y el temporizador sin respuesta)

- Habilitar,deshabilitar/modificar configuraciones inmediatas de reenvío de llamadas

- Habilitar,deshabilitar/modificar la configuración de delegación

- Habilitar,deshabilitar/modificar la configuración del grupo de llamadas de equipo

    > [!NOTE]
    > Nuevo en la herramienta SEFAUtil de Skype Empresarial Server 2015

- Habilitar,deshabilitar/modificar la configuración de las llamadas simultáneas (incluye el destino)

    > [!NOTE]
    > Nuevo en la herramienta SEFAUtil de Skype Empresarial Server 2015

- Habilitar/deshabilitar/modificar la configuración de atención de llamadas grupales

    > [!CAUTION]
    > Nuevo en la herramienta SEFAUtil de Skype Empresarial Server 2015

Esta herramienta tiene las siguientes limitaciones:

- Solo se admite para los usuarios que están en un grupo de servidores de Skype Empresarial Server

- No se admite la edición masiva de la configuración de enrutamiento de llamadas para varios usuarios

### <a name="output"></a>Salida

La versión actual de esta herramienta solo proporciona resultados en la ventana del símbolo del sistema. Para obtener más información, vea la sección Ejemplos más adelante en este documento.

### <a name="purpose"></a>Finalidad

Estos son algunos de los escenarios clave en los que se puede usar esta herramienta:

- Bob es un ejecutivo y se ha movido a la telefonía de Skype Empresarial Server. Tiene delegación en su sistema PBX existente. Como parte del traslado a Skype Empresarial Server 2015, el administrador puede configurar el enrutamiento de Bob para reflejar su configuración de delegación preexistida.

- Alicia está de viaje y se da cuenta de que espera una llamada importante de uno de sus clientes. Sin embargo, se encuentra en un hotel y no tiene acceso a un equipo. Llama al departamento de soporte técnico y solicita que reenvía a su número de teléfono móvil todas las llamadas realizadas a su número de trabajo. El personal del departamento de soporte técnico puede realizar la configuración en su nombre.

- Las llamadas de Joe a su número de trabajo van a su correo de voz móvil siempre que esté en el trabajo; sin embargo, parece que las cosas funcionan correctamente en la mayoría de las demás ubicaciones. El técnico del departamento de soporte técnico puede ver la configuración de enrutamiento de Joe y descubre que Joe tiene llamadas simultáneas configuradas en su teléfono móvil. El técnico pregunta a Joe sobre la cobertura móvil en su oficina y es capaz de determinar que la regla de llamadas simultáneas es lo que hace que las llamadas vayan al correo de voz móvil de Joe cuando su cobertura de red es deficiente.

- Mike es un nuevo empleado de Contoso y se está uniendo a un nuevo equipo en el que todos los miembros están configurados para la llamada de equipo. Cuando se habilita para Skype Empresarial Server 2015, el administrador puede establecer la configuración de su grupo de llamada de equipo para incluir todos los miembros de su nuevo equipo, además, el administrador agrega a Mike como miembro de grupo de llamada de equipo para cada uno de los miembros de su equipo.

- Una práctica de atención al cliente en el departamento de recursos humanos de Contoso es proporcionar un servicio personal a todos los autores de llamadas desde la primera llamada. Dado que todos los miembros del departamento se sientan muy cerca unos de otros, hacer que todos los teléfonos suene al mismo tiempo con la llamada de equipo es muy molesto para el equipo. Para proporcionar el mejor servicio sin interrumpir a los miembros del equipo, el administrador de Skype Empresarial Server 2015 aprovecha la capacidad de atención de llamadas grupales. El administrador agrega todos los miembros del departamento a un grupo de recogida y comunica al departamento el número del grupo de recogida. Cuando María no está en su escritorio, Joe nota sus llamadas telefónicas y continúa a responder la llamada desde su escritorio.

### <a name="requirements"></a>Requirements

La herramienta SEFAUtil solo se puede ejecutar en un equipo que forma parte de un grupo de aplicaciones de confianza. UCMA 3.0 debe estar instalado en ese equipo. Para ejecutar la herramienta, debe crearse una nueva aplicación de confianza con el identificador de aplicación SEFAUtil en ese grupo de servidores.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Creación de una nueva aplicación de confianza para la herramienta SEFAUtil

1. La herramienta SEFAUTil solo se puede ejecutar en un equipo que forma parte de un grupo de aplicaciones de confianza. Si es necesario, puede agregar un grupo de servidores como un nuevo grupo de aplicaciones de confianza a través del Shell de administración de Skype Empresarial Server con el siguiente cmdlet:

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > UCMA 3.0 debe estar instalado en cualquier equipo que se usará para ejecutar la herramienta SEFAUtil.

2. Debe definirse una aplicación de confianza en la topología de la herramienta SEFAUtil. Para definir SEFAUtil como una nueva aplicación de confianza, use el Shell de administración de Skype Empresarial Server y ejecute el siguiente cmdlet:

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > Se puede usar un puerto diferente si es necesario.
    
    > [!NOTE]
    > FQDN del grupo de servidores: el FQDN del servidor o grupo de servidores que hospedará la aplicación SEFAUtil (normalmente un servidor front-end de Skype Empresarial > grupo de servidores).
    > FQDN del registrador de grupo: el FQDN del servidor front-end de Skype Empresarial o del grupo asociado a este grupo de aplicaciones.
    > Sitio del grupo de servidores: el identificador de sitio del sitio en el que se encuentra este grupo de servidores.

3. Es necesario habilitar los cambios en la topología. La habilitación de los cambios en la topología se puede realizar a través del Shell de administración de Skype Empresarial Server ejecutando el siguiente cmdlet:

   ```powershell
   Enable-CsToplogy
   ```

4. Si es necesario, instale las herramientas del kit de recursos de Skype Empresarial Server 2015 en el servidor que se usará para ejecutar la herramienta SEFAUtil (el servidor debe formar parte de un grupo de aplicaciones de confianza).

5. Compruebe que SEFAUtil se está ejecutando correctamente. Para ello, ejecute la herramienta desde un símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de reenvío de llamadas de un usuario en la implementación. De forma predeterminada, la herramienta se encontrará en: "...\Archivos de programa\Skype Empresarial Server 2015\Reskit". Para mostrar la configuración de reenvío de llamadas de un usuario, use el siguiente comando:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    Se debe mostrar la configuración de reenvío de llamadas del usuario.

#### <a name="group-call-pickup"></a>Atender llamada grupal

La atención de llamadas grupales requiere una configuración adicional en Skype Empresarial Server 2015 para que la capacidad esté totalmente habilitada. Antes de asignar grupos de recogida a los usuarios, consulte la documentación del producto de atención de llamadas grupales para ver los pasos de planeación e implementación de esta funcionalidad.

### <a name="examples"></a>Ejemplos

#### <a name="display-current-call-handling-settings"></a>Mostrar la configuración actual de administración de llamadas

El siguiente comando muestra el control de llamadas para el usuario.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> En este ejemplo se usa **el modificador /server** para especificar el Skype Empresarial Server al que conectarse.

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Establecer el destino de reenvío de llamada o sin respuesta

En este ejemplo se establece el destino de la llamada de reenvío/no respuesta y el retraso de la llamada. Aquí no se proporciona el modificador /server; SEFAUtil intenta detectar automáticamente Skype Empresarial Server 2015.

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

#### <a name="enable-call-forwarding-immediately"></a>Habilitar el reenvío de llamadas inmediatamente

En este ejemplo se habilita inmediatamente el reenvío de llamadas a otro usuario.

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

#### <a name="disable-call-forwarding-immediately"></a>Deshabilitar el reenvío de llamadas inmediatamente

En este ejemplo se deshabilita inmediatamente el reenvío de llamadas.

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

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Agregar un usuario como delegado y configurar llamadas simultáneas de delegados

En este ejemplo se agrega un usuario como delegado y se establecen las llamadas simultáneas de los delegados.

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

En este ejemplo se cambia la regla de llamadas simultáneas establecida en el ejemplo anterior a la regla de llamadas retrasadas.

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
> Cuando se quita el último delegado, las anillos delegadas se deshabilitan automáticamente.

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

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Agregar un delegado y configurar la regla Call-Forward a delegados

En este ejemplo se agrega un delegado y se configura la regla de reenvío de llamada a delegados.

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
> Para cambiar el número de destino de las llamadas simultáneas de un usuario que ya tiene habilitadas las llamadas simultáneas, mantenga el comando con el modificador /enablesimulring; de lo contrario, no se cambiará el número de destino.

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Deshabilitar llamadas simultáneas

En este ejemplo se deshabilitan las llamadas simultáneas.

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

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Agregar un miembro del equipo para Team-Call y configurar las llamadas simultáneas al grupo Team-Call miembros

En este ejemplo se agrega un miembro del equipo al grupo de llamadas de equipo de un usuario y se habilitan las llamadas simultáneas al grupo de llamadas de equipo.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Al agregar un miembro al grupo de llamada de equipo de un usuario, se cambiarán automáticamente los grupos de llamadas simultáneas de los usuarios para silenciar su grupo de llamadas de equipo.

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Quitar un miembro del grupo Team-Call grupo

En este ejemplo se quita un integrante del grupo de llamada de equipo de un usuario.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Si el miembro que se quita es el único miembro del grupo de llamada de equipo, las llamadas simultáneas al grupo de llamadas de equipo se deshabilitarán automáticamente.

 **Resultado**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Establecer el anillo con retraso en el Team-Call grupo

En este ejemplo se cambia el anillo con retraso a la configuración de hora del grupo de llamadas de equipo.

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

#### <a name="enable-team-call"></a>Habilitar Team-Call

En este ejemplo se habilita la llamada de equipo para un usuario determinado.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Si el grupo de llamada de equipo del usuario no tiene ningún miembro, no se habilitará la llamada de equipo.

 **Resultado**

#### <a name="disable-team-call"></a>Deshabilitar Team-Call

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

En este ejemplo se asigna un grupo de recogida a un usuario y se habilita la atención de llamadas grupales.

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

#### <a name="disable-group-call-pickup"></a>Deshabilitar la atención de llamadas grupales

En este ejemplo se deshabilita la atención de llamadas grupales para un usuario determinado.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Cuando se deshabilita la atención de llamadas grupales para un usuario, no se conserva el número de grupo asignado al usuario. Si posteriormente desea volver a habilitar la atención de llamadas grupales para ese usuario, debe asignar el número de grupo de nuevo con el modificador /enablegrouppickup.

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Descripción

SYSPrep.ps1 es un script Windows PowerShell que instalará los siguientes requisitos previos de Skype Empresarial Server 2015 en su equipo del sistema operativo Windows Server 2008.

- Microsoft .Net Framework 4.5

- Microsoft SQL Server Express

- Windows Powershell versión 3.0

- Visual C++ 2010 Redistributable

- Actualizaciones de Internet Information Server

- Windows Identity Foundation

- Archivos principales de Skype Empresarial Server 2015

  Aunque el nombre del script es similar a la Herramienta de preparación del sistema para los sistemas operativos Microsoft Windows, son diferentes. Este script solo instalará los requisitos previos necesarios para Skype Empresarial Server 2015. Una vez instalados estos requisitos previos, la herramienta SYSPrep de Windows se puede usar para crear una imagen del servidor.

### <a name="requirements"></a>Requirements

Antes de ejecutar el script SYSPrep.ps1, debe copiar los archivos de requisitos previos en una carpeta local en la máquina del sistema operativo Windows Server 2008 (por **ejemplo, D:\Setup).** Esta carpeta también debe incluir una copia de los archivos de Skype Empresarial Server 2015, específicamente **Setup.exe.** Los archivos de requisitos previos se pueden descargar desde las siguientes ubicaciones:


| **Requisito previo**                                | **Location**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .Net Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows Powershell versión 3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 Redistributable  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| Actualizaciones de Internet Information Server  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype Empresarial Server 2015 Setup.exe  <br/> | Copiar desde medios de Skype Empresarial Server 2015  <br/>                   |

### <a name="parameter"></a>Parámetro

El **parámetro -SetupFolder** toma como argumento la ubicación del directorio de los archivos de requisitos previos

### <a name="examples"></a>Ejemplos

Para ejecutar el script SYSPrep.ps1 e instalar los requisitos previos de Skype Empresarial Server 2015, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Migración de anuncios de números sin signo
<a name="UNAM"> </a>

La herramienta de migración de anuncios de números sin signo permite a un administrador de Skype Empresarial Server 2015 mover la configuración de números sin signo a la que da servicio la aplicación de anuncio desde un Skype Empresarial Server o un grupo de servidores de origen a un skype empresarial server o grupo de servidores de destino.

### <a name="description"></a>Descripción

La herramienta de migración de anuncios de números sin signo es un script de Windows PowerShell que mueve la configuración de números sin signo a la que da servicio la aplicación de anuncio de un servidor o grupo de servidores de origen a otro servidor o grupo de servidores.

Cuando se ejecuta, el script de migración de anuncios de números sin signo realizará las siguientes operaciones:

1. Mueva todos los archivos de audio usados por los anuncios de números sin signo de la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen al almacén de archivos del servidor o grupo de servidores de destino.

    > [!NOTE]
    > Los archivos de audio se quitan del grupo de origen una vez que se copian en el grupo de servidores de destino.

2. Mueva todos los anuncios de números sin signo configurados para la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen al servidor o grupo de servidores de destino.

3. Reasignar todos los intervalos de números sin asignar a los que da servicio la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen al servidor o grupo de servidores de destino.

Después de ejecutar correctamente el script, todos los intervalos de números sinsignar a los que presta servicio la aplicación de anuncio hospedada en el servidor o grupo de servidores de origen serán ahora atendidos con la misma configuración por el servidor o grupo de destino.

### <a name="output"></a>Salida

El script **Move-CsAnnouncementConfiguration** indica en la ventana del Shell de administración de Skype Empresarial Server desde donde se ejecutó correctamente o no la operación de migración.

Si la ejecución de la operación se interrumpe por algún error, los intervalos de números sin signo que se movieron correctamente al destino permanecerán en el destino en un formato operativo y el resto de intervalos de números sin signo que se migrarán permanecerán en el origen, así como en un formato operativo. Para migrar completamente el resto de la configuración, vuelva a ejecutar el script después de solucionar el error.

### <a name="purpose"></a>Finalidad

El script de migración de anuncios de números sin signo se puede usar en los tres escenarios siguientes:

- **Migrar opciones de configuración a una nueva versión de Skype Empresarial Server:** Contoso está en proceso de migración a Skype Empresarial Server 2015 y, como parte del proceso de migración, el administrador de Skype Empresarial Server desea mover la configuración de números sinsignar a la que presta servicio la aplicación de anuncio desde la implementación de Lync Server 2013 a la nueva implementación de Skype Empresarial Server 2015. Para mover las opciones de configuración, el administrador de Skype Empresarial Server usa la herramienta de migración de anuncios de números sin signo.

- **Revertir una implementación de Skype Empresarial Server 2015 a Lync Server 2013:** Debido a factores inesperados, Contoso tiene que revertir la migración a la nueva implementación de Skype Empresarial Server 2015. Para minimizar las interrupciones en el servicio, el administrador de Skype Empresarial Server usa la herramienta de migración de anuncios de números sinsignar para revertir la configuración de la implementación de Skype Empresarial Server 2015 a la implementación de Lync Server 2013.

- **Mover datos entre implementaciones:** Contoso está en proceso de reemplazar todos los servidores de un grupo por servidores más recientes. Su estrategia es implementar un nuevo grupo de Skype Empresarial Server 2015, mover todos los datos del antiguo al nuevo grupo y, a continuación, desuso del grupo antiguo. Una vez implementado el nuevo grupo de servidores, se usa la herramienta de migración de anuncios de números sin signo para mover la configuración del grupo antiguo al nuevo.

#### <a name="requirements"></a>Requirements

Estos son los requisitos principales necesarios para ejecutar correctamente la herramienta:

1. El script debe ejecutarse desde un equipo que tenga instalado el Shell de administración de Skype Empresarial Server.

2. La aplicación de anuncio debe implementarse correctamente en los servidores o grupos de servidores de Skype Empresarial de origen y destino.

#### <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration script

El Move-CsAnnouncementConfiguration script requiere los dos parámetros que se describen en la tabla siguiente.

![Move-CsAnnouncementConfiguration parámetros.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Ejemplos

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Mover la configuración de anuncios de números sin signo de un grupo de Lync Server 2013 a un grupo de Skype Empresarial Server 2015

En este ejemplo se mueven los anuncios de números sin signo del grupo de servidores de origen (Lync Server 2013) al grupo de servidores de destino (Skype Empresarial Server 2015).

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Mover la configuración de anuncios de números sin signo de un grupo de Skype Empresarial Server 2015 a un grupo de Lync Server 2013

En este ejemplo se mueven los anuncios de números sin signo del grupo de servidores de origen (Skype Empresarial Server 2015) al grupo de servidores de destino (Lync Server 2013).

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf Data
<a name="WebConfData"> </a>

La Herramienta de datos Web Conf permite a un administrador del software de comunicaciones de Skype Empresarial Server 2015 tener más control sobre los datos asociados a las conferencias web de un organizador. Los escenarios incluyen la capacidad de eliminar los datos de reuniones de un usuario específico según criterios de marca de tiempo.

### <a name="description"></a>Descripción

Esta herramienta permite al administrador realizar las siguientes operaciones:

1. Busque todos los datos de conferencia web asociados con un solo usuario.

2. Elimine todos los datos de conferencia web asociados con un único usuario.

3. Elimine todos los datos de conferencia web asociados a un único usuario que sea anterior a una fecha determinada.

4. Mueva todos los datos de conferencia web asociados con un único usuario cuando ese usuario se mueve de un grupo a otro.

    > [!NOTE]
    > Las herramientas del kit de recursos para Lync Server 2010 admiten mover todos los datos de conferencia web asociados con un solo usuario cuando se mueve ese usuario de un grupo a otro. Esa funcionalidad ahora está en desuso de esta herramienta en favor del **parámetro MoveConferenceData.** Para obtener más información acerca de este parámetro, consulte el cmdlet [Move-CsUser.](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps)

La herramienta elimina los datos de reunión solo para las reuniones inactivas. Las reuniones activas (o reuniones en sesiones) no se pueden eliminar.

Esta herramienta debe ejecutarse desde un equipo que se encuentra en el mismo grupo que el usuario de destino. El usuario cuyos datos de contenido de reuniones se administran mediante esta herramienta debe estar en el mismo grupo de usuarios.

### <a name="output"></a>Salida

Esta herramienta genera los resultados de cada una de las operaciones:

- Si se realiza una consulta, la herramienta genera la lista de todas las carpetas de datos de reuniones inactivas que tienen a ese usuario como organizador.

- Si se realiza una eliminación, la herramienta genera la lista de todas las carpetas de datos de reunión cuyos datos se eliminarán.

### <a name="requirements"></a>Requirements

La herramienta debe ejecutarse en el mismo grupo de servidores en el que se encuentra actualmente el organizador.

La herramienta debe ejecutarse con privilegios de administrador con acceso al almacén de archivos de contenido.

### <a name="examples"></a>Ejemplos

En la tabla siguiente se describen los parámetros, algunos de los cuales se usan en los ejemplos.

![Parámetros de la herramienta de datos Web Conf.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

En el ejemplo anterior se muestra cómo funcionaría un comando de consulta. El resultado de este comando sería una lista de todas las carpetas de contenido de reuniones que se verían afectadas por esta herramienta.

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

El anterior es un ejemplo de un comando delete. El comando eliminar quitará todas las carpetas de reunión inactivas de este usuario.

### <a name="summary"></a>Resumen

Esta herramienta puede ser un recurso valioso para los administradores que necesitan un control más preciso sobre los datos de reuniones de conferencia.


