---
title: Documentación de las herramientas del kit de recursos de Lync Server 2013
TOCTitle: Documentación de las herramientas del kit de recursos de Lync Server 2013
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945604(v=OCS.15)
ms:contentKeyID: 52061999
ms.date: 08/03/2014
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Documentación de las herramientas del kit de recursos de Lync Server 2013

 

_**Última modificación del tema:** 2014-01-09_

En este tema se describen las herramientas que forman parte del Kit de recursos de Lync Server 2013, incluido el objetivo de cada herramienta y ejemplos de uso. Microsoft Lync Server 2013, herramientas del kit de recursos ayuda a que las tareas rutinarias sean más fáciles para los administradores de TI que implementan y administran Lync Server 2013. Por ejemplo, la herramienta **Web Conf Data** se puede usar para controlar fácilmente los datos que suben los usuarios durante una conferencia en línea. La herramienta **SEFAUtil** se puede usar para delegar el desvío de llamadas y respuesta para los usuarios. Se recomienda que los administradores de TI usen estas herramientas para administrar de manera eficaz Lync Server 2013.

## Instalación de las herramientas del kit de recursos

Para instalar el Microsoft Lync Server 2013, herramientas del kit de recursos, descargue **OCSReskit.msi**. Puede descargar el instalador de las Herramientas del kit de recursos del Centro de descarga en [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429).

Ejecute **OCSResKit.msi** para hacer una instalación sencilla. El archivo .msi instala todas las herramientas en la ruta de acceso siguiente: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**. Las herramientas que son ejecutables independientes se encuentran en esta carpeta. Las herramientas que también tienen archivos están en sus propias subcarpetas.

## Entornos compatibles

Para un rendimiento óptimo, Microsoft Lync Server 2013, herramientas del kit de recursos debe instalarse en el mismo entorno y con las mismas especificaciones necesarias para Lync Server 2013.

## Información general sobre las herramientas del kit de recursos

En la lista siguiente se describen las herramientas proporcionadas en el kit de recursos de Lync Server 2013. En la sección siguiente se incluye una descripción de cada herramienta, además de los requisitos y ejemplos de uso.

  - ABSConfig

  - Monitor de servicio de directiva de ancho de banda

  - Analizador de uso de ancho de banda

  - Call Parkometer

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

  - Unassigned Number Announcements Migration

  - Web Conf Data

## ABSConfig

La herramienta Configuración del servicio de libreta de direcciones (ABSConfig) es una herramienta administrativa que ayuda a los administradores a personalizar la configuración del Servicio de libreta de direcciones en Lync Server 2013. Además, esta herramienta permite a los administradores de Lync Server 2013 restaurar la configuración predeterminada del Servicio de libreta de direcciones.

## Descripción

ABSConfig es una aplicación de interfaz gráfica de usuario que permite a los administradores configurar los atributos de Servicios de dominio de Active Directory que están relacionados con el Servicio de libreta de direcciones.

Los escenarios principales para la herramienta son los siguientes:

  - Permitir a los administradores asignar atributos en Servicios de dominio de Active Directory a los atributos de Lync Server 2013.

  - Permitir a los administradores especificar el atributo de Servicios de dominio de Active Directory que se incluirá o excluirá en los archivos del Servicio de libreta de direcciones.

  - Permitir a los administradores restaurar la configuración predeterminada del Servicio de libreta de direcciones.

La herramienta ABSConfig puede iniciarse mediante el archivo absConfig.exe. La herramienta se abre en la ficha **Configurar atributos**. Esta tabla contiene opciones para asignar atributos de Servicios de dominio de Active Directory a los campos de atributos de Lync Server 2013 y especificar qué usuarios se incluirán o excluirán en los archivos del Servicio de libreta de direcciones según filtros de atributos específicos. También tiene opciones para personalizar el valor del número de teléfono que se incluirá en el archivo de la libreta de direcciones. La opción **Restaurar valores predeterminados** permite a los administradores restaurar la configuración del servicio de libreta de direcciones a los valores predeterminados.

## Cambios en comparación con Lync Server 2010

En la herramienta de configuración de ABS de Lync Server 2013 pueden eliminarse los atributos (filas) si se desactiva la casilla "habilitar" del atributo. Esto tiene el mismo efecto que si se eliminara la fila en Lync Server 2010.


> [!NOTE]
> La casilla "habilitar" se encuentra en la primera columna de la derecha; puede que tenga que desplazarse hacia la derecha para verla



## Salida

ABSConfig guarda la configuración del servicio de libreta de direcciones en la base de datos.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

## Finalidad

ABSConfig proporciona una forma rápida y sencilla para personalizar el servicio de libreta de direcciones de Lync Server 2013.

## Requisitos

## Equipo

ABSConfig solo puede ejecutarse en un equipo unido al dominio que tenga instalado Lync Server 2013. En caso de Lync Server 2013, Enterprise Edition, esta herramienta puede ejecutarse en cualquier servidor front-end que tenga habilitado el servicio de libreta de direcciones durante la instalación.

## Red

El equipo debe ser capaz de conectarse al grupo de servidores front-end y a la base de datos back-end.

## Software

Antes de ejecutar la herramienta ABSConfig es necesario instalar los siguientes componentes de software:

  - Microsoft Lync Server 2013

## Usuarios

Los administradores que tengan los permisos necesarios para actualizar la implementación de Lync Server 2013.

## Ejemplos

Para iniciar ABSConfig, escriba **ABSConfig.exe** en un símbolo del sistema. A continuación se muestra la interfaz de usuario de la herramienta ABSConfig.

![La herramienta ABSConfig.exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "La herramienta ABSConfig.exe.")

## Resumen

La herramienta ABSConfig proporciona a los administradores una herramienta rápida y sencilla para personalizar el servicio de libreta de direcciones de Lync Server 2013.

## Monitor del servicio de directiva de ancho de banda

La herramienta Monitor del servicio de directiva de ancho de banda permite a los administradores ver una lista de lo siguiente:

1.  Todos los servicios de directiva de ancho de banda de Lync Server 2013 (autenticación y central) en la topología

2.  Las conexiones que realiza cada servicio a otros servicios de directiva de ancho de banda y a los servidores perimetrales

3.  Todos los vínculos configurados en el documento de configuración de red y el uso de ancho de banda en tiempo real informado por los servicios de directiva de ancho de banda

## Descripción

La herramienta Monitor de servicio de directiva de ancho de banda se implementa como una aplicación basada en GUI. Los administradores pueden ejecutar la aplicación mediante PDPMonUI.exe.

Al iniciar la aplicación, esta intenta detectar la lista de servicios de directiva de ancho de banda en la topología. Después de completar la actualización inicial, en el panel de la izquierda de la ventana se muestra una lista de servicios agrupados por los clústeres a los que pertenecen.

Cuando los administradores seleccionan un servicio de directiva de ancho de banda concreto, en el panel de la derecha se muestra información sobre dicho servicio. Además, el panel también contiene dos pestañas principales con información.

## Pestaña Información de equipo

La pestaña **Información de equipo** contiene información detallada sobre el servicio de directiva de ancho de banda seleccionado, además de la lista y el estado de todas las conexiones realizadas por dicho servicio de directiva de ancho de banda seleccionado a otros servicios.

## Pestaña Información de topología

En la pestaña **Información de topología** se muestra una lista de todos los vínculos configurados en las opciones de red. Por cada vínculo se muestra la capacidad de ancho de banda de audio y de vídeo. Además, también se muestra el ancho de banda utilizado actualmente, tanto en kbps como en porcentaje de la capacidad. La herramienta utiliza códigos de color para resaltar vínculos cuyo uso está próximo al límite de capacidad, lo que permite a los administradores aislarlos rápidamente.


> [!NOTE]
> Si la herramienta Monitor de servicio de directiva de ancho de banda genera errores al conectarse a alguno de los servicios de Directiva de ancho de banda, no se rellenará la información en las pestañas <STRONG>Información de equipo</STRONG> e <STRONG>Información de topología</STRONG>. Sin embargo, es posible que la herramienta pueda conectarse de forma inicial, pero que posteriormente pierda la conexión al servicio. En estos casos, los administradores pueden ver información no actualizada. En las pestañas hay una marca de tiempo <STRONG>Última actualización</STRONG> que puede permitir a los administradores ver cuándo se actualizó por última vez un servicio de directiva de ancho de banda concreto.



## Salida

No hay salida de línea de comandos; la salida del programa está contenida en la interfaz gráfica de usuario (GUI) principal.

## Finalidad

El objetivo de la herramienta Monitor de servicio de directiva de ancho de banda es permitir a los administradores ver el estado de los servicios de directiva de ancho de banda definidos en la topología. Además, los administradores pueden ver el uso de ancho de banda en tiempo real de todos los vínculos definidos en el documento Configuración de red.

## Requisitos

La herramienta Monitor de servicio de directiva de ancho de banda necesita ejecutarse en un equipo que pertenezca a la topología de Lync Server.

## Resumen

La herramienta Monitor de servicio de directiva de ancho de banda puede ser un recurso útil para los administradores, ya que permite inspeccionar el estado de todos los servicios de directiva de ancho de banda en la topología y, lo que es aún más importante, les permite conocer el uso de ancho de banda en tiempo real de los vínculos definidos en las opciones de configuración de red.

## Analizador de uso de ancho de banda

El analizador de uso de ancho de banda es una herramienta que genera informes sobre diferentes vistas de consumo de ancho de banda por los extremos de comunicaciones unificadas en vínculos WAN en la red empresarial. Estos informes pueden utilizarse para conocer el patrón de consumo de ancho de banda y ayudar a planificar la capacidad de ancho de banda.

## Descripción

El analizador de uso de ancho de banda se implementa como una aplicación basada en GUI. Esta herramienta genera informes específicos para el uso de audio en la red y ayuda a planificar la capacidad. Además, también itera en la capacidad de ancho de banda asignada a diferentes vínculos.

## Salida

El analizador de uso de ancho de banda proporciona representaciones gráficas de la capacidad de ancho de banda y el consumo de audio para todos los vínculos WAN configurados en el sistema.

## Finalidad

En cualquier implementación de voz y vídeo es muy importante supervisar y comprender la tendencia de uso de ancho de banda del tráfico multimedia en la red empresarial. La herramienta Analizador de uso de ancho de banda permite a los administradores conseguir justo eso. Esta herramienta hace lo siguiente:

  - Genera informes específicos para el uso de audio en la red

  - Mejora la eficacia de planificación de capacidad y la iteración en la capacidad de ancho de banda asignada a diferentes vínculos

El analizador de uso de ancho de banda puede generar las siguientes representaciones gráficas de capacidad de ancho de banda e informes de uso:

  - Todos los vínculos WAN en la red empresarial

  - Filtrados por los vínculos WAN seleccionados

  - Filtrados por los vínculos WAN que han superado la capacidad de vínculos

  - Filtrados por vínculos WAN que no han utilizado toda la capacidad de ancho de banda proporcionada

  - Filtrados por vínculos WAN que han alcanzado niveles críticos (un uso de ancho de banda superior al 90 % de capacidad de ancho de banda del vínculo WAN)

  - Filtrados por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregionales y vínculos dentro de un sitio

  - Filtrados por región de red

## Aplicaciones

El analizador de uso de ancho de banda incluye las siguientes dos aplicaciones (herramientas):

  - **WanLinkLogCollector.exe**   Esta herramienta permite al usuario proporcionar la información necesaria.

  - **BandwidthUtilizationAnalyzer.xlsm**  WanLinkLogCollector.exe inicia automáticamente un informe de software de hoja de cálculo de Microsoft Excel. Esta aplicación permite al usuario aplicar filtros al informe, como se muestra posteriormente en este artículo.

## Fases de uso del Analizador de uso de ancho de banda

Existen dos fases al usar el Analizador de uso de ancho de banda:

  - Recopilar registros, que es realizado automáticamente mediante WanLinkLogCollector.exe

  - Personalizar informes, que es realizado mediante BandwidthUtilizationAnalyzer.xlsm

> [!IMPORTANT]  
> No se recomienda que los usuarios finales inicien BandwidthUtilizationAnalyzer.xlsm de forma manual.


## Inicio del Analizador de uso de ancho de banda

Inicie WanLinkLogCollector.exe en el símbolo del sistema o mediante el Explorador de Windows.

**Uso de WanLinkLogCollector.exe**

Hay tres pasos para usar WanLinkLogCollector.exe:

1.  **Registro de la escala de tiempo**   Proporciona la escala de tiempo necesaria para generar el informe

2.  **Especificar los directorios de archivos**   Proporciona información sobre la ubicación de los archivos

3.  **Recopilar los registros e iniciar el visor de informes**  Ejecuta el comando para generar el informe

## Paso 1: registro de la escala de tiempo

Registrar la escala de tiempo permite al usuario de la herramienta especificar lo siguiente como se muestra en la ilustración siguiente.

1.  **Fecha de inicio** Esta es la fecha de inicio de la escala de tiempo para la que se genera el informe; por ejemplo, 1 de agosto de 2010.

2.  **Fecha de finalización** Esta es la fecha de finalización de la escala de tiempo para la que se genera el informe; por ejemplo, 30 de septiembre de 2010.
    
    ![Fecha de inicio y fin en el análisis de utilización de ancho de banda](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Fecha de inicio y fin en el análisis de utilización de ancho de banda")  

## Paso 2: especificar los directorios de archivos

Los directorios de archivos siguientes se pueden especificar por el usuario.

  - **Ubicación de archivos de registro del servidor** La ubicación de la carpeta donde se almacenan los registros del servidor de la directiva de ancho de banda, que suele ser \<servidor de archivos\>\\\<opción de FE\>\\AppServerFiles\\PDP.

  - **Ubicación de almacenamiento de archivos temporales** La ubicación de archivos temporales donde se almacenan los archivos intermedios mientras se genera el informe.

![Directorios de archivos en análisis de utilización de ancho de banda](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Directorios de archivos en análisis de utilización de ancho de banda")


> [!NOTE]
> Compruebe que el usuario de la herramienta posee acceso a los archivos de los registros del servidor y a la carpeta donde se almacenan los archivos temporales.



## Paso 3: recopilar los registros e iniciar el visor de informes

Para recopilar los registros e iniciar el visor de informes, haga clic en **Ejecutar** como se indica a continuación. Este paso recopila todos los datos necesarios.

![Recopilación de datos en el análisis de utilización de ancho de banda](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Recopilación de datos en el análisis de utilización de ancho de banda")

Cuando la validación de entrada es correcta, se muestra el mensaje que aparece a continuación.

![Notificación de registros recopilados en la utilidad de ancho de banda](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Notificación de registros recopilados en la utilidad de ancho de banda")

Haga clic en **Aceptar**. BandwidthUtilizationAnalyzer.xlsm se iniciará automáticamente. Siga las instrucciones en el cuadro de mensaje. Para obtener más información, consulte **Uso de BandwidthUtilizationAnalyzer.xlsm** en la sección siguiente.


**Uso de BandwidthUtilizationAnalyzer.xlsm**

1.  Cuando BandwidthUtilizationAnalyzer.xlsm se inicie automáticamente, haga clic en **Actualizar** como se muestra a continuación.
    
    ![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")

2.  Al abrir un archivo, seleccione consolidated.csv de la ubicación especificada en el cuadro de mensaje, como se muestra a continuación. Además, también muestra la ubicación como **C:\\Temp**.
    
    ![Abrir una carpeta en BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Abrir una carpeta en BandwidthUtilizationAnalyzer.")

3.  Haga clic en **Importar**.

4.  Se generará automáticamente la representación gráfica. Está disponible cuando desaparece el puntero que indica un proceso en segundo plano.
    
    ![Aplicación de filtros en la vista de informes.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicación de filtros en la vista de informes.")

## Aplicar filtros a la vista de informes

Los filtros que se pueden aplicar a la vista de informes son los siguientes:

![Aplicación de filtros en la vista de informes.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicación de filtros en la vista de informes.")

1.  **Nombre** Filtra por vínculos WAN (el filtro se encuentra en la parte derecha del gráfico). El prefijo indica los siguientes tipos de vínculos; consulte el cuadro vertical (azul):
    
      - **Sitio S** El vínculo WAN de un sitio de red a una región de red
    
      - **ES entre sitios** El vínculo WAN entre dos sitios de red
    
      - **Interregional R** El vínculo WAN entre dos regiones de red

2.  **Límite superado** Filtra por vínculos WAN cuyo uso de ancho de banda supera la capacidad de ancho de banda

3.  **Niveles críticos** Filtra por vínculos WAN cuyo uso de ancho de banda ha alcanzado el 90 % o más de la capacidad de ancho de banda

4.  **No aprovechados** Filtra por vínculos WAN cuyo uso de ancho de banda ha sido inferior al 25 % de la capacidad de ancho de banda

5.  **Tipo de vínculo** Filtra por los siguientes tipos de vínculos WAN:
    
      - Tipo de **sitio de red**
    
      - Tipo de **vínculo entre sitios**
    
      - Tipo de **vínculo interregional**

6.  **Región** Filtrar por región de red

En las ilustraciones siguientes se muestran los filtros descritos anteriormente.

Filtrar por **Nombre**. Seleccione la lista de vínculos que han de mostrarse en el gráfico.

![Filtrado por Nombre en BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtrado por Nombre en BandwidthUtilizationAnalyzer.")

Filtrar por **Límite superado**. Seleccione **Verdadero** para aplicar el filtro.

![Filtrado por Límite superado.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtrado por Límite superado.")

Filtrar por **Niveles críticos**. Seleccione **Verdadero** para aplicar el filtro.

![Filtrado por Niveles críticos.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtrado por Niveles críticos.")

Filtrar por **Sin aprovechar**. Seleccione **Verdadero** para aplicar el filtro.

![Filtrado por Sin aprovechar.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtrado por Sin aprovechar.")

Filtrar por **Tipo de vínculo**. Seleccione el tipo o tipos que desee mostrar.

![Filtrado por Tipo de vínculo.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtrado por Tipo de vínculo.")

Filtrar por **Región**. Seleccione una lista de regiones cuyos vínculos desee mostrar.

![Filtrado por Región.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtrado por Región.")

## Requisitos

  - The .NET Framework 3.5

  - Microsoft Excel 2010 o Excel 2007

## Resumen

El analizador de uso de ancho de banda se utiliza para representar el uso de ancho de banda para tráfico de comunicaciones unificadas en la red. Esta herramienta también se puede utilizar para informar sobre el uso de ancho de banda de vídeo en la red.

## Call Parkometer

Call Parkometer es una aplicación de línea de comandos que proporciona acceso rápido a la base de datos de órbitas de estacionamiento de llamadas.

## Descripción

Call Parkometer es una herramienta para realizar un seguimiento de las llamadas estacionadas actualmente. También recopila estadísticas sobre el uso de órbitas y el servidor de estacionamiento de llamadas (CPS). Esta herramienta de línea de comandos proporciona acceso de lectura y escritura a la base de datos de SQL Server de órbitas de CPS desde un equipo local o remoto.

Todas las opciones se excluyen mutuamente. La sintaxis de línea de comandos es la siguiente:

  - Parámetro **–o:** genera una lista de todos los intervalos de órbitas configurados para este grupo de servidores.

  - Parámetro **–n:** genera una lista de las órbitas utilizadas actualmente en este grupo de servidores. La información mostrada es la siguiente:
    
      - Identificador uniforme de recursos (URI) de SIP del estacionado y el estacionador.
    
      - Nombre de host del CPS donde se ha estacionado la llamada.
    
      - Marca de tiempo correspondiente al momento en que se estacionó la llamada.

  - Parámetro **–f:** genera una lista del número de órbitas libres actualmente en el grupo de servidores.

  - Parámetro **–r \<n\>:** genera una lista de las últimas llamadas estacionadas \<n\>. La información mostrada es la siguiente:
    
      - URI de SIP del estacionado.
    
      - URI de SIP del estacionador.
    
      - Nombre de host del CPS donde se estacionó la llamada.
    
      - Marca de tiempo correspondiente al momento en que se recuperó o finalizó la llamada.

  - Parámetro **-t\<n\>:** comprueba la reserva de una órbita en la base de datos para mostrar la aleatoriedad de los números de órbita asignados.

## Salida

Según los parámetros de entrada especificados en el símbolo del sistema, Call Parkometer muestra la salida siguiente:

  - Todos los intervalos de órbitas configurados para este grupo de servidores

  - Llamadas estacionadas actualmente

  - Número de órbitas libres (disponibles)

  - Llamadas estacionadas recientemente

  - Órbitas reservadas para comprobar valores de órbitas uniformes y aleatorias

## Finalidad

El objetivo de la herramienta CPS es proporcionar acceso mediante línea de comandos a la base de datos de CPS. El administrador puede ver el uso de CPS y determinar el número de órbitas asignadas a un grupo de servidores.

## Requisitos

No existen requisitos si esta herramienta se ejecuta en el mismo equipo donde se ejecuta CPS. Si la herramienta se ejecuta en un equipo remoto, la base de datos de SQL Server utilizada por Lync Server 2013 debe configurarse para permitir acceso remoto. Call Parkometer debe configurarse con una cadena de conexión de base de datos de SQL Server para conectarse al SQL Server del grupo de servidores. Esta cadena de conexión de base de datos de SQL Server se define en el archivo de configuración, **parkometer.exe.config**, y debe copiarse en el mismo directorio donde se encuentra parkometer.exe. El archivo XML siguiente es un ejemplo de parkometer.exe.config. Los parámetros que deben configurarse son el nombre de usuario (por ejemplo, miDominio\\Administrador), la contraseña (por ejemplo, miContraseña) y el nombre de host (por ejemplo, miServidor).

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

## Ejemplos

Intervalos de órbitas implementadas: el parámetro –o genera una lista de todos los intervalos de órbitas configurados para este grupo de servidores

![Órbita de estacionamiento en Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Órbita de estacionamiento en Call Parkometer.")

Llamadas estacionadas actualmente: el parámetro –n genera una lista de todas las órbitas utilizadas actualmente en este grupo de servidores

![Llamadas actualmente estacionadas en Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Llamadas actualmente estacionadas en Call Parkometer.")

Número de órbitas libres: el parámetro –f genera una lista de todas las órbitas libres actualmente en el grupo de servidores

![Órbitas libres en Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Órbitas libres en Call Parkometer.")

Llamadas estacionadas recientemente: el parámetro –r \<n\> genera una lista de las últimas llamadas estacionadas de \<n\>

![Llamadas recién estacionadas en Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Llamadas recién estacionadas en Call Parkometer.")

Prueba de reserva de órbita: el parámetro –t \<n\> reserva una órbita en la base de datos como prueba

![Reservas de órbitas de prueba en Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Reservas de órbitas de prueba en Call Parkometer.")

## Resumen

Call Parkometer es una herramienta de línea de comandos que proporciona información detallada sobre el servidor de estacionamiento de llamadas.

## CleanupStorageServiceData

La herramienta de kit de recursos CleanupStorageServiceData permite eliminar datos huérfanos de la base de datos utilizados por el servicio de almacenamiento de Lync Server (LYSS). Una de las funciones del servicio de almacenamiento es almacenar en búfer la comunicación entre Lync Server y varios extremos de almacenamiento de datos back-end, como SQL Server y Exchange.

## Descripción

Para admitir la alta disponibilidad, LYSS acepta y guarda copias de los datos en varios servidores front-end del grupo de forma temporal y elimina los datos después de haber sido entregados en la ubicación de almacenamiento de larga duración final. Existen situaciones poco frecuentes que pueden producirse durante un funcionamiento que no sea normal (por ejemplo, cuando un servidor se bloquea o experimenta errores de procesamiento); además, es posible que algunos datos no se eliminen correctamente. Estos datos son inofensivos, pero consumen recursos de procesamiento limitados. Una gran parte del mantenimiento de datos normal necesario es automatizado, pero esta herramienta permite la identificación y eliminación segura de estos datos huérfanos cuando no es posible ejecutar una eliminación automatizada. El uso de esta herramienta aparece indicado cuando se genera una alerta de seguimiento de estado de System Center Operations Manager (SCOM) que solicita al administrador que elimine los datos innecesarios de las bases de datos locales de LYSS en el grupo de servidores. Se generará un evento correspondiente en el registro de eventos del front-end donde se active la alerta. Los detalles del evento contendrán información sobre los datos huérfanos contenidos en el front-end y se activará cuando los datos superen ciertos umbrales predeterminados.

## Requisitos

Instale Microsoft Lync Server 2013, herramientas del kit de recursos. La herramienta se ejecuta en equipos unidos a un dominio donde estén instalados Lync Server y Shell de administración de Lync Server 2013. La herramienta utiliza un cmdlet desde el shell de administración para identificar todos los servidores front-end del grupo. En segundo lugar, la herramienta debe ejecutarse desde un equipo del grupo que tenga instalada la base de datos **RtcLocal**. Esta base de datos es utilizada por la herramienta CleanupStorageServiceData para obtener los detalles de conexión necesarios para comunicarse con el servicio de enrutamiento de Lync Server. Finalmente, la cuenta o credencial que invoque la herramienta debe tener permiso de lectura y escritura en el archivo compartido donde escribir el registro de salida. Además, esta herramienta depende de que el estado del grupo sea estable. En definitiva, esto quiere decir que se espera que todos los servidores front-end funcionen correctamente, que la instancia LYNCLOCAL de SQL Server y la base de datos de LYSS puedan conectarse entre ellas, y que cada grupo de enrutamiento tenga un conjunto completo de 1 servidor front-end primario y 2 servidores front-end secundarios.

## Ejemplos

C:\\Archivos de programa\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe

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

## DBAnalyze

## Descripción

DBAnalyze es una herramienta de línea de comandos que ayuda a los administradores a recopilar informes de análisis sobre las bases de datos de Lync Server 2013. DBAnalyze tiene los modos siguientes: diagnóstico, datos de usuario, conferencia, MCU y fragmentación de disco:

  - **Modo de diagnóstico**   Crea un informe con información sobre tablas (número de registros, fragmentación, tamaño de los datos y tamaño del índice), tamaños de datos y archivos de registro, día y hora de la última copia de seguridad, distribución de contactos entre servidores que ejecutan Microsoft Office Communications Server, el promedio de permisos, contactos, contenedores, suscripciones, publicaciones, extremos por usuario, usuarios hospedados de manera incorrecta, usuarios que no pueden redirigirse, el promedio de conferencias organizadas por usuario, conferencias programadas, conferencias activas y la versión de la base de datos.
    

    > [!NOTE]
    > La ejecución en modo de diagnóstico puede afectar al rendimiento del servidor.



  - **Modo de datos de usuario**  Contacto de informes, contenedor, suscripción, publicación, permiso y datos de grupo de contactos de un usuario específico o usuarios que tengan a dicho usuario en sus listas de contactos y permisos. Este modo también proporciona datos de resumen para conferencias que un usuario organice o a las que esté invitado.

  - **Modo de conferencia**   Proporciona datos detallados para una conferencia específica, incluidos todos los detalles de programaciones de la conferencia, la lista de invitados, la lista de tipos de medios permitidos en la conferencia, las unidades de control multipunto (MCU) activas, la lista de participantes activos y el estado de señalización de los participantes.

  - **Descodificar id. de reunión**  Descodifica un id. de reunión de red de telefonía pública conmutada (PSTN) que haya sido especificada por el modificador **/pstnid** pero que no se conecte al back-end para obtener información detallada.

  - **Resolver conferencia**   Descodifica un id. de reunión de PSTN que haya sido especificado por el modificador **/pstnid** y muestra información sobre la conferencia indicada por el identificador.

  - **Modo de MCU**  Proporciona el id., el tipo de medio, la dirección URL, el estado del latido, la carga de la conferencia y la carga de participantes de todas las MCU del grupo de servidores.

  - **Modo de fragmentación de disco**  Muestra el estado de fragmentación de todos los discos.

Esta herramienta puede utilizarse para diagnosticar diferentes problemas o para ayudar a los administradores con la planificación de capacidad. Por ejemplo, si la mayoría de los usuarios hospedados en el servidor A eligen a usuarios hospedados en el servidor B como sus contactos, el administrador puede mover los usuarios del servidor A al servidor B para reducir el tráfico entre servidores.

## Salida

Esta herramienta genera informes predefinidos sobre la base de datos de Lync Server 2013. **Ruta de acceso:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit

## Finalidad

Para instalar Dbanalyze.exe, copie el archivo en una carpeta local y, a continuación, ejecute la herramienta. Para ejecutar la herramienta, ejecute el comando siguiente desde la línea de comandos.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` A continuación encontrará las descripciones de las opciones de la línea de comandos.

![Opciones de la línea de comandos para Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Opciones de la línea de comandos para Dbanalyze.exe.")

## Requisitos

**Equipo** DBAnalyze solo puede ejecutarse desde un equipo unido al dominio que tenga instalado Lync Server 2013.

**Red** El equipo debe ser capaz de conectarse a la base de datos back-end.

**Software** Es necesario instalar los componentes del software de Lync Server 2013 antes de ejecutar DBAnalyze.

**Usuarios**En la tabla siguiente se muestran los administradores que tienen los permisos necesarios para acceder a las bases de datos de Lync Server 2013.

![Tabla de permisos para Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tabla de permisos para Dbanalyze.exe.")


> [!NOTE]
> Para el modo <STRONG>/report:disk</STRONG> se necesita una cuenta de administrador local.



## Ejemplos

A continuación se muestran varios ejemplos de comandos de Dbanalyze.exe válidos:

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

## Resumen

DBAnalyzer proporciona a los administradores una forma rápida y sencilla de analizar bases de datos de Lync Server 2013.

## ImportStorageServiceData

La herramienta de kit de recursos ImportStorageServiceData permite reimportar datos de colas y extremos que hayan sido vaciados del servicio de almacenamiento (LYSS) de nuevo en el servicio de almacenamiento.

## Descripción

Los datos del servicio de almacenamiento pueden haber sido vaciados de forma automática (periódica) según el estado del elemento de cola o en el tamaño de la base de datos. Puede haber ocurrido debido a la invocación manual del cmdlet de la conmutación por error de grupo o por el cmdlet StorageServiceFullFlush (invocado por el cmdlet de conmutación por error de grupo). Se recomienda reimportar los datos si el tamaño de la base de datos del servicio de almacenamiento (LYSS ) de alguno de los front-end supera el nivel normal, ya que esto puede causar que se exporten más datos. Además, en primer lugar deben solucionarse los problemas que puedan haber contribuido a errores que causaron que la cola del servicio de almacenamiento creciera (por ejemplo, errores de extremos de Exchange , problemas de red u otros problemas).

**Escenario 1:** durante la conmutación por error del grupo de servidores, los archivos pueden vaciarse del servicio de almacenamiento para cada front-end. Después de completar la conmutación por error, debe ejecutarse la herramienta para volver a importar los datos.

**Escenario 2:** los datos se vacían automáticamente todos los días o como respuesta cuando el tamaño de la base de datos del servicio de almacenamiento supera determinados umbrales (por ejemplo, 60 %, 80 %, 90 %). El administrador debe volver a importar de forma periódica los datos que hayan sido vaciados de forma automática. En la situación anterior, si el paquete SCOM no se implementa, existen eventos para el servicio de almacenamiento de Lync Server relacionados con el vaciado de datos del servicio de almacenamiento. Los eventos id. 32075 (se ha iniciado una operación de vaciado completo), id. 32076 (se ha completado el vaciado completo), id. 32082 (se ha iniciado el vaciado de nivel de mantenimiento), id. 32083 (se ha completado el vaciado de nivel de mantenimiento), id. 32089 (se ha producido un vaciado porque se ha llenado la base de datos). Estos identificadores de eventos se corresponden con la versión RTM. Cuando un administrador ve estos eventos, quiere decir que se han vaciado archivos. Estos datos deben volverse a importar de forma periódica mediante esta herramienta (por ejemplo, una vez por semana).

Para la versión del servicio en línea, si se implementa el paquete SCOM de seguimiento de estado para Lync Server existen nuevas alertas que pueden activarse que solicitan al administrador que vuelva a importar los datos vaciados en el servicio de almacenamiento. Existirá un evento correspondiente en el registro de eventos del servidor front-end que habrá activado la alerta. El evento ofrecerá una descripción de la ruta de acceso primaria donde se encuentran los archivos de los datos vaciados, así como el número de archivos que cumplen con los criterios de alerta. Los criterios de alerta es que haya X o más archivos en la ruta de acceso primaria con un mínimo de Y días (donde X e Y están predefinidos en el servicio de almacenamiento, pero pueden reemplazarse si se cambia el archivo APPCONFIG). A continuación se muestran dos ejemplos de eventos que pueden activar la alerta de estado, cuya diferencia es la ruta de acceso primaria. Una posibilidad se encuentra en el recurso compartido de archivos del servicio web, mientras que la otra es el directorio de datos de aplicación local de cada servidor front-end (por ejemplo, c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ). A continuación, el administrador ejecutará esta herramienta de kit de recursos.

Esta herramienta aumentará la carga de CPU y de E/S en el front-end donde se ejecute, así como otros front-end, si los datos no son propiedad del front-end donde se ejecuta la herramienta. Se recomienda ejecutar esta herramienta cuando los front-end no estén sometidos a cargas elevadas de CPU y de E/S (por ejemplo, en horas de poca actividad). En segundo lugar, esta herramienta puede tardar entre 2 y 3 minutos para importar un archivo de datos. Esto debe tenerse en cuenta al calcular el tiempo de ejecución de la aplicación. El archivo de registro detallado generado por la herramienta aparecerá de forma predeterminada en el almacén de archivos. Elimínelo si no se detectan errores, ya que el tamaño del archivo de registro puede ser de varias decenas de MB o más.

![Eventos de ejemplo del registro de eventos del servidor de almacenamiento.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Eventos de ejemplo del registro de eventos del servidor de almacenamiento.")

## Requisitos

Instale Microsoft Lync Server 2013, herramientas del kit de recursos. La herramienta se ejecuta en equipos unidos a un dominio donde se haya instalado Lync Server y Shell de administración de Lync Server. La herramienta utiliza un cmdlet del shell de administración para identificar todos los servidores front-end del grupo. En segundo lugar, la herramienta debe ejecutarse desde un equipo del grupo que tenga instalada la base de datos **RtcLocal**. Esta base de datos es utilizada por la herramienta para recuperar la ubicación del recurso compartido de archivos WEBSERVICE para el grupo de servidores. Además, antes de usar la herramienta cada servidor front-end debe primero habilitar la comunicación remota de Windows PowerShell mediante **Enable-PSRemoting** en cada servidor front-end, así como en el equipo donde se ejecute la herramienta. En caso contrario, los comandos de Windows PowerShell remoto desde esta herramienta producirán errores. La comunicación remota de Windows PowerShell se puede desactivar en todos los servidores front-end del grupo después de completar la operación. Finalmente, la cuenta o credencial que invoque la herramienta debe poseer permisos de lectura y escritura en el recurso compartido de archivos del servicio web para el grupo donde se ejecute esta herramienta. En caso contrario, la herramienta producirá errores por permisos de E/S.


> [!NOTE]
> En Windows Server 2012, la comunicación remota de Windows PowerShell está habilitada de forma predeterminada, pero no en Sistema operativo Windows Server 2008.



## Ejemplos

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

## LCSSync

La herramienta LCSSync ayuda a implementar el software de comunicaciones de Lync Server 2013 en un entorno de varios bosques. Esta herramienta se utiliza para sincronizar usuarios y grupos de diferentes bosques de usuarios como un objeto contacto de Servicios de dominio de Active Directory a un bosque central donde está instalado Lync Server 2013.

## Descripción

LCSSync utiliza los objetos contacto de Servicios de dominio de Active Directory del bosque central para habilitar a usuarios para Lync Server. Para proporcionar el inicio de sesión único, la cuenta de usuario principal debe asignarse al objeto contacto de Servicios de dominio de Active Directory en el bosque central para Lync Server 2013. Esta herramienta ayuda a realizar dicha asignación. Esta herramienta proporciona plantillas para crear agentes de administración en Microsoft Identity Integration Server.

## Resumen

La herramienta LCSSync ayuda a implementar Lync Server en un entorno de varios bosques.

## LookupUserConsole

La herramienta LookupUserConsole muestra información interna de enrutamiento de Lync Server acerca de usuarios específicos. Esta información puede ser útil para personal de soporte de Microsoft para el diagnóstico de problemas de implementación y enrutamiento.

## Descripción

Al ejecutar LookupUserConsole.exe se abrirá una ventana de símbolo del sistema que acepta direcciones SIP e intenta mostrar información interna de enrutamiento de Lync Server relacionada con estas. Escriba **exit** para salir de la herramienta LookupUserConsole.

## Requisitos

Instale Microsoft Lync Server 2013, herramientas del kit de recursos. La herramienta se ejecuta en equipos unidos a un dominio donde esté instalado Lync Server

## Ejemplos

C:\\Archivos de programa\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe

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

## MsTurnPing

La herramienta MSTurnPing permite a los administradores de software de comunicaciones de Microsoft Lync Server 2013 comprobar el estado de los servidores que ejecuten los servicios perimetrales de audio y vídeo, y los servicios de autenticación de audio y vídeo que ejecuten servicios de directiva de ancho de banda en la topología.

## Descripción

La herramienta MSTurnPing permite a los administradores de software de comunicaciones de Lync Server 2013 comprobar el estado de los servidores que ejecuten los servicios perimetrales de audio y vídeo, y los servicios de autenticación de audio y vídeo que ejecuten servicios de directiva de ancho de banda en la topología.

La herramienta permite a los administradores realizar las pruebas siguientes:

1.  Prueba de servidor perimetral de A/V: la herramienta realiza las siguientes pruebas contra todos los servidores perimetrales de A/V en la topología:
    
      - Comprueba que el servicio de autenticación de audio y vídeo de Lync Server se ha iniciado y que puede emitir los credenciales correctos.
    
      - Comprueba que el servicio perimetral de audio y vídeo de Lync Server se ha iniciado y que puede asignar los recursos en el perímetro externo correctamente.

2.  Prueba del servicio de directiva de ancho de banda: la herramienta realiza las pruebas siguientes contra todos los servidores que ejecutan los servicios de directiva de ancho de banda en la topología:
    
      - Comprueba que el servicio de directiva de ancho de banda (autenticación) de Lync Server se ha iniciado y que puede emitir los credenciales correctos.
    
      - Comprueba que el servicio de directiva de ancho de banda (central) de Lync Server se ha iniciado y que puede comprobar el ancho de banda correctamente.

Esta herramienta debe ejecutarse en un equipo que forme parte de la topología y que tenga instalado el almacén local.

## Salida

La herramienta genera los resultados de todas las operaciones.

  - Si se ejecuta la prueba **AudioVideoEdgeServer**, los resultados de la herramienta son los siguientes:
    
      - Los resultados de la prueba de los equipos que proporcionen el servicio de autenticación de audio y vídeo de Lync Server en la topología
    
      - Los resultados de la prueba de los equipos que proporcionen el servicio perimetral de audio y vídeo de Lync Server en la topología

  - Si se ejecuta la prueba **BandwidthPolicyServer**, los resultados de la herramienta son los siguientes:
    
      - Los resultados de la prueba de los equipos que proporcionen el servicio de directiva de ancho de banda (autenticación) de Lync Server en la topología
    
      - (autenticación) de Lync Server en la topología Los resultados de la prueba de los equipos que proporcionen el servicio de directiva de ancho de banda (central) de Lync Server en la topología

## Requisitos

  - Esta herramienta debe ejecutarse en un equipo que se encuentre en la topología y que tenga el almacén local.

  - La herramienta debe ejecutarse como un administrador con acceso al almacén local.

## Ejemplos

A continuación se muestra un ejemplo de la entrada de la herramienta.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

## Resumen

Esta herramienta puede ser un recurso útil para los administradores de Lync Server 2013 que deseen comprobar el estado de los servidores que ejecuten servicios de directiva de audio y de vídeo, y de ancho de banda.

## Visor de configuración de red

Los administradores de software de comunicaciones de Microsoft Lync Server 2013 pueden utilizar el visor de configuración de red para ver la topología de red del servicio de control de admisión de llamadas (CAC) de una empresa que permita sesiones de comunicación en tiempo real, como llamadas de voz o videollamadas basadas en una capacidad de ancho de banda específica. Los administradores de Lync Server 2013 definen directivas de CAC, que son aplicadas por los servicios de directiva de ancho de banda que se instalan con Lync Server 2013.

## Descripción

El visor de configuración de red (NetworkConfigurationViewer.exe) permite a los administradores realizar las tareas siguientes:

  - Cargar y ver la topología de red de CAC de una implementación de Lync Server 2013 en un formato gráfico.

  - Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directiva de ancho de banda en un formato gráfico.

  - Guardar y almacenar la topología de red de CAC en formato XML en el disco.

  - Guardar y almacenar el diagrama de topología de red de CAC en formato JP o BMP.

  - Ver los datos de configuración de la topología de red de CAC.

  - Ver la topología de red de CAC en estilo de vista de árbol.

  - Definir conectores personalizados para vínculos de topología de red de CAC (por ejemplo, vínculos de sitio a región, de región a región y de sitio a sitio).

  - Ver información de sitio de topología de red de CAC, información de región y directivas de ancho de banda y vínculos de red proporcionados.

## Finalidad

Ver vínculos de topología de red de CAC de empresa en una interfaz gráfica.

## Ejemplos

**Cargar y ver la topología de red de CAC de una implementación de Lync Server 2013 en un formato gráfico:** los administradores de Lync Server 2013 pueden cargar y ver la configuración de la topología de red de CAC en cualquier equipo Lync Server 2013 mediante la opción **Descargar configuración de red**, como se muestra en la imagen siguiente. La herramienta no podrá descargar o ver dicha configuración al implementarse en un equipo que no pueda conectarse al almacén de configuración de Lync.

![Descargar la configuración de red.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Descargar la configuración de red.")

**Cargar y ver la topología de red de CAC de un archivo de registro de servidor de directiva de ancho de banda en un formato gráfico:** los servidores de directivas de ancho de banda de Lync Server 2013 guardan la topología de red de CAC como parte del mecanismo de registro en la ubicación de recurso compartido de archivos de Lync Server 2013. Los administradores de Lync Server pueden ver dicho archivo en formato gráfico mediante la opción **Abrir configuración de red**, como se muestra a continuación.

![Abrir un archivo de registro de servidor de directiva de ancho de banda.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Abrir un archivo de registro de servidor de directiva de ancho de banda.")

Guardar y almacenar la topología de red de CAC en formato XML en el disco: los administradores de Lync Server 2013 pueden guardar el archivo de configuración de la topología de red de CAC en formato XML mediante la opción **Guardar una copia de configuración de red**, como se muestra a continuación. El archivo de configuración guardado puede utilizarse para ver una representación gráfica en un entorno sin conexión.

![Guardar la configuración de red como archivo XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Guardar la configuración de red como archivo XML.")

Guardar y almacenar el diagrama de la topología de red de CAC en formato JPG o BMP: los administradores de Lync Server 2013 pueden guardar la configuración de la topología de red de CAC en un formato gráfico (formatos de archivo JPG y BMP) mediante la opción **Guardar diagrama de configuración de red como imagen**, como se muestra a continuación.

![Guardar la configuración de red como imagen.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Guardar la configuración de red como imagen.")

**Ver datos de configuración de topología de red de CAC: los administradores de**Lync Server 2013 pueden ver datos relacionados de configuración de red como regiones de red, sitios de red, perfiles de ancho de banda y direcciones IP de subred de sitio en formato de texto mediante la opción de datos Ver configuración de red, como se muestra a continuación.

![Ver los datos de configuración de red.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Ver los datos de configuración de red.")

**Ver topología de red de CAC en estilo de vista de árbol:** los administradores de Lync Server 2013 pueden ver datos relacionados de configuración de red en estilo de vista de árbol gráfico mediante el panel de control en la parte izquierda de la ventana de la herramienta, como se muestra a continuación.

![Ver los datos de configuración de red en vista de árbol.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Ver los datos de configuración de red en vista de árbol.")

**Definir conectores personalizados para vínculos de topología de red de CAC (como vínculos de sitio a región, de región a región y de sitio a sitio):** los administradores de Lync Server 2013 pueden definir conectores gráficos personalizados para vínculos WAN de configuración de red mediante las opciones de configuración, como se muestra a continuación. Esto ayuda a diferenciar entre diferentes tipos de vínculos de red proporcionados en la configuración de red.

![b20bea67-c8e1-453e-b1dd-e2aa17b62566](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "b20bea67-c8e1-453e-b1dd-e2aa17b62566")

**Ver información de sitio, información de región y directivas de ancho de banda proporcionadas de topología de red de CAC:** los administradores de Lync Server 2013 pueden ver información relacionada de región de red de CAC, información de sitio e información de suministro de ancho de banda de CAC mediante las opciones que se muestran a continuación (por ejemplo, haga clic en **Información** en un objeto de región de red o de sitio de red).

![Definir los conectores personalizados para su red.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definir los conectores personalizados para su red.")

## Resumen

Esta herramienta puede ser un recurso útil para los administradores de Lync Server 2013 que quieran ver la topología de red de CAC de su implementación en un formato gráfico.

## Response Group Agent Live

La aplicación de grupo de respuesta permite a los agentes acceder en tiempo real a información útil mediante el servicio web integrado. Desafortunadamente, no hay disponible una vista gráfica de estos datos fuera de la aplicación. La herramienta del kit de recursos Response Group Agent Live soluciona este problema al proporcionar una forma gráfica y sencilla de acceder a esta información, mejorada con información en tiempo real del software de comunicaciones de Microsoft Lync 2013, como la presencia de otros agentes.

## Descripción

Response Group Agent Live es una aplicación para Windows que proporciona funciones de inicio y cierre de sesión, así como determinada información en tiempo real (como pertenencia a grupo y número actual de llamadas) a los agentes de grupo de respuesta. El objetivo de esta herramienta es ser una versión mejorada de la página Grupos de agentes (a la que se puede acceder desde Lync 2013.

## Finalidad

La aplicación de grupo de respuesta envía las llamadas entrantes a una cola y, a continuación, las redirige a grupos de agentes. Para poder tomar decisiones fundamentadas sobre las llamadas que deben atenderse, los agentes pueden acceder a información en tiempo real sobre sus grupos de agentes, como los agentes disponibles y el número de llamadas que espera en cada cola. Esta información, inicialmente accesible solo mediante el servicio de grupo de respuesta, es facilitada de forma intuitiva por la herramienta Response Group Agent Live.

## Características

La herramienta Response Group Agent Live está basada en el servicio de grupo de respuesta y el SDK de Microsoft Lync 2013. Proporciona a los agentes de grupo de respuesta la información y las funciones disponibles del servicio de grupo de respuesta (como pertenencia a grupo, presencia de otros agentes y número de llamadas en espera).

En la ilustración siguiente se muestra la interfaz principal de la herramienta Response Group Agent Live.

![La herramienta Response Group Agent Live.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "La herramienta Response Group Agent Live.")

Las tres características principales que aparecen a continuación están disponibles para los agentes en Response Group Agent Live:

  - **Inicio/cierre de sesión:** al contrario que la página Grupos de agentes (a la que puede accederse desde Lync 2013), Response Group Agent Live solo permite a los agentes iniciar o cerrar la sesión de todos los grupos de agentes a la vez. Esta aplicación proporciona tres formas rápidas para que los agentes puedan iniciar y cerrar la sesión:
    
      - Haga clic en los botones de inicio y cierre de sesión (verde y rojo) en la aplicación.
    
      - Haga clic en el icono de la bandeja del sistema y seleccione iniciar sesión o cerrar sesión.
    
      - Uso de métodos abreviados de teclado configurables.

  - **Pertenencia a grupos:** cuando se selecciona un grupo de agentes, Response Group Agent Live muestra la lista de agentes del grupo en el panel derecho. Si Lync 2013 se ejecuta en el mismo equipo que esta aplicación, la información de presencia y la tarjeta de contacto se mostrarán en la herramienta Response Group Agent Live. Los agentes pueden enviar un mensaje instantáneo o llamar a otros agentes directamente desde allí.

  - **Estadísticas en tiempo real:** Response Group Agent Live proporciona estadísticas en tiempo real para todos los grupos de agentes. La frecuencia de actualización es de un minuto. Cuando un grupo de respuesta responde a una llamada, se añade un indicador visual junto al nombre del grupo con el número actual de llamadas en cola. Al detener el puntero sobre un grupo, también se muestra el tiempo de espera más largo.

## Requisitos

Response Group Agent Live requiere .NET Framework 4.0. Además, para aprovechar las características de presencia y tarjeta de contacto debe instalarse (y ejecutarse) Lync 2013 de forma local.

## Configuración

Response Group Agent Live puede personalizarse según preferencias individuales mediante el cuadro de diálogo de opciones de la aplicación. Además, el administrador puede definir la dirección de host predeterminada al editar directamente la propiedad defaultHostAddress del archivo RGAgentLive.exe.config.

En la ilustración siguiente se muestra el cuadro de diálogo de opciones que los agentes pueden usar para configurar la dirección de host y las teclas de método abreviado. Para acceder a este cuadro de diálogo, haga clic en el botón Opciones de la parte superior derecha de la interfaz principal.

![El cuadro de diálogo de las opciones de Response Group Agent Live.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "El cuadro de diálogo de las opciones de Response Group Agent Live.")

Las tres opciones siguientes pueden personalizarse en la configuración de Response Group Agent Live:

  - Dirección de host: suele ser el FQDN del grupo web que pertenece al grupo de servidores principales del agente. La dirección exacta del servicio de grupo de respuesta se obtiene automáticamente en segundo plano a partir de esta información (al añadir la ruta de acceso correcta después del host).

  - Métodos abreviados de teclado: los métodos abreviados de teclado exactos para iniciar/cerrar sesión se pueden personalizar. La única limitación es que ambos deben contener la tecla del logotipo de Windows (además de al menos otra tecla).

  - Iniciar con Windows: la aplicación puede configurarse para iniciarse automáticamente con Windows.

## Ejemplos

En la ilustración siguiente se muestra cómo llamar o enviar un mensaje instantáneo a otro agente; para ello es necesario hacer clic con el botón secundario en el contacto del panel derecho.

![Hacer una llamada o enviar un mensaje instantáneo.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Hacer una llamada o enviar un mensaje instantáneo.")

En la ilustración siguiente aparece cómo Response Group Agent Live muestra el número de llamadas en la cola y el tiempo de espera más largo de todas las llamadas entrantes.

![Ver información de cola.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Ver información de cola.")

## Resumen

Inicio y cierre de sesión rápidos, pertenencia a grupos y estadísticas en tiempo real básicas son algunas de las características interesantes del agente del grupo de respuesta que solo están disponibles fuera de la aplicación del servicio de grupo de respuesta. Con la herramienta de kit de recursos Response Group Agent Live, los administradores de Lync pueden proporcionar a sus agentes una aplicación para Windows que les permita completar tareas de forma gráfica y con mayor rapidez.

## SEFAUtil

SEFAUtil (activación de característica de extensión secundaria) es una herramienta de línea de comandos que permite a los administradores de software de comunicaciones de Microsoft Lync Server 2013 y a los agentes del departamento de soporte técnico configurar las llamadas delegadas, el desvío de llamadas, las llamadas simultáneas, la configuración de llamadas de equipo y la respuesta de llamadas de grupo en nombre de un usuario de Lync Server 2013. Además, la herramienta también permite a los administradores consultar la configuración del enrutamiento de llamadas que se haya publicado para un usuario concreto. La herramienta SEFAUtil permite a los administradores habilitar/deshabilitar/modificar el desvío de llamadas o las llamadas simultáneas en nombre del usuario. El administrador puede especificar el destino (en forma de una URI de SIP) o usar un destino que ya haya sido publicado por el usuario. Esta herramienta también permite a los administradores agregar o quitar delegados o miembros de un grupo de llamada de grupo en nombre del usuario. Esta herramienta está basada en Microsoft Unified Communications Managed API (UCMA) 3.0 y requiere que los administradores creen una aplicación de confianza en el almacén de administración central para SEFAUtil.

SEFAUtil (activación de característica de extensión secundaria) permite a los administradores de Lync Server 2013 y a los agentes del departamento de soporte técnico configurar llamadas delegadas, desvío de llamadas, llamadas simultáneas, configuración de llamadas de equipo y respuesta de llamada de grupo en nombre de un usuario de Lync Server 2013. Esta herramienta también permite a los administradores consultar la configuración de desvío de llamadas que se haya publicado para un usuario concreto.

## Descripción

La versión actual de SEFAUtil es tan solo una herramienta de línea de comandos; no dispone de una interfaz gráfica de usuario. Esta herramienta está basada en Microsoft Unified Communications Managed API (UCMA) 3.0. Las características de esta herramienta permiten a los administradores y agentes del departamento de soporte técnico realizar las acciones siguientes:

  - Ver todas las opciones de configuración de enrutamiento de llamadas para un usuario (incluidos el desvío de llamadas, la delegación, llamadas simultáneas, llamadas de equipo y respuestas de llamada de grupo)

  - Habilitar/deshabilitar/modificar la configuración del desvío de llamadas (incluidos el destino y el temporizador de llamadas sin respuesta)

  - Habilitar/deshabilitar/modificar las configuraciones inmediatas de desvío de llamadas

  - Habilitar/deshabilitar/modificar la configuración de delegación

  - Habilitar/deshabilitar/modificar la configuración de grupo de llamada de equipo
    

    > [!NOTE]
    > Novedades en la herramienta SEFAUtil de Lync Server 2013



  - Habilitar/deshabilitar/modificar la configuración de llamadas simultáneas (incluido el destino)
    

    > [!NOTE]
    > Novedades en la herramienta SEFAUtil de Lync Server 2013



  - Habilitar/deshabilitar/modificar la configuración de respuesta a llamada grupal
    
    > [!NOTE]  
    > Novedades en la herramienta SEFAUtil de Lync Server 2013


Esta herramienta tiene las limitaciones siguientes:

  - Solo admite usuarios hospedados en un grupo de Lync Server

  - No admite la edición en masa de las opciones de configuración de enrutamiento de llamadas para varios usuarios

## Salida

La versión actual de esta herramienta solo ofrece resultados en la ventana del símbolo del sistema. Para obtener más información, consulte la sección Ejemplos más adelante en este documento.

## Finalidad

A continuación se describen algunos de los escenarios donde puede utilizarse esta herramienta:

  - Roberto es un ejecutivo que ha comenzado a utilizar la telefonía de Lync Server. Ha configurado la delegación en su sistema PBX existente. Como parte del traslado a Lync, el administrador puede configurar el enrutamiento de Roberto para reflejar su configuración de delegación preexistente.

  - Alicia está de viaje y se da cuenta de que está esperando una llamada importante de uno de sus clientes. Sin embargo, está en un hotel y no tiene acceso a un PC. Entonces, llama al departamento de soporte técnico y solicita que se desvíen a su número de teléfono móvil todas las llamadas realizadas a su número de trabajo. El personal de soporte técnico puede realizar la configuración en su nombre.

  - Las llamadas de Jorge a su número de trabajo están desviadas a su correo de voz del teléfono móvil cuando está en el trabajo; sin embargo, en el resto de ubicaciones todo parece funcionar correctamente. El agente de soporte técnico puede ver la configuración de enrutamiento de Jorge y descubre que ha configurado las llamadas simultáneas a su teléfono móvil. El técnico pregunta a Jorge acerca de la cobertura móvil en su oficina y determina que la regla de llamadas simultáneas es lo que está causando que las llamadas vayan al correo de voz del teléfono móvil de Jorge cuando la cobertura de la red es insuficiente.

  - Miguel es un nuevo empleado en Contoso y se ha unido a un equipo nuevo donde todos los miembros están configurados para llamadas de equipo; al realizar la configuración para Microsoft Lync, el administrador puede definir la configuración de grupo de llamada de equipo para incluir todos los nuevos miembros del equipo y, además, el administrador agrega a Miguel como un miembro de grupo de llamada de equipo por cada uno de los miembros de su equipo.

  - Uno de los procedimientos de atención al cliente en el departamento de recursos humanos de Contoso es proporcionar personal de servicio para todos los autores de llamadas desde la primera llamada. Debido a que todos los miembros del departamento se sientan muy cerca unos de otros, tener todos los teléfonos sonando de forma simultánea con llamadas de equipo es muy molesto para el equipo. Para poder proporcionar el mejor servicio sin molestar a los miembros del equipo, el administrador de Lync aprovecha la función de respuesta de llamadas grupales. El administrador agrega todos los miembros del departamento al número de respuesta. Cuando Sandra no está en su escritorio, Jorge se da cuenta de que suena el teléfono de Sandra y responde a la llamada desde su escritorio.

## Requisitos

La herramienta SEFAUtil solo puede ejecutarse desde un equipo que forme parte de un grupo de aplicaciones de confianza. UCMA 3.0 debe instalarse en dicho equipo. Para ejecutar la herramienta es necesario crear un id. de aplicación de SEFAUtil en el grupo.

**Crear una nueva aplicación de confianza para la herramienta SEFAUtil**

1.  La herramienta SEFAUTil solo puede ejecutarse en un equipo que pertenezca a un grupo de aplicaciones de confianza. Si fuera necesario, puede agregar un grupo como un nuevo grupo de aplicaciones de confianza mediante el shell de administración de Lync Server con el siguiente cmdlet:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    

    > [!NOTE]
    > UCMA 3.0 debe estar instalado en todos los equipos que se utilicen para ejecutar la herramienta SEFAUtil.



2.  Es necesario definir una aplicación de confianza en la topología para la herramienta SEFAUtil. Para definir SEFAUtil como una nueva aplicación de confianza, use el shell de administración de Lync Server y ejecute el siguiente cmdlet:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    

    > [!NOTE]
    > Si fuera necesario, puede utilizarse un puerto distinto.



3.  Es necesario habilitar los cambios de topología. Para ello, ejecute el siguiente cmdlet mediante el shell de administración de Lync Server:
    
        Enable-CsToplogy

4.  Si fuera necesario, instale las herramientas del kit de recursos de Lync Server 2013 en el servidor que se utilizará para ejecutar la herramienta SEFAUtil (el servidor debe pertenecer a un grupo de aplicaciones de confianza).

5.  Compruebe que SEFAUtil se ejecuta correctamente. Para ello, ejecute la herramienta desde un símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación. De forma predeterminada, la herramienta se encuentra en: “…\\Archivos de programa\\Microsoft Lync Server 2013\\Reskit”. Para mostrar la configuración de desvío de llamadas de un usuario, utilice el comando siguiente:
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    Se mostrará la configuración de desvío de llamadas del usuario.

## Respuesta de llamadas grupales

Para poder habilitar la función de respuesta de llamadas grupales es necesario realizar una configuración adicional en Lync Server. Antes de asignar grupos de respuesta a los usuarios, consulte los pasos de planificación e implementación de esta función en la documentación del producto de respuesta de llamadas grupales.

## Ejemplos

## Mostrar la configuración administración de llamadas actual

El comando siguiente muestra la administración de llamadas para el usuario. `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`


> [!NOTE]
> En este ejemplo se utiliza el modificador <STRONG>/server</STRONG> para especificar el Lync Server al que conectarse.



**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

## Establecer el desvío de llamadas/destino sin respuesta

En este ejemplo se establece el desvío de llamadas/destino sin respuesta y la demora de timbre. En este caso no se ha incluido el modificador /server; SEFAUtil intentará detectar automáticamente el Lync Server.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

## Habilitar desvío de llamadas inmediatamente

En este ejemplo se habilita el desvío de llamadas inmediatamente a otro usuario.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

## Deshabilitar desvío de llamadas inmediatamente

En este ejemplo se deshabilita automáticamente el desvío de llamadas.

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Agregar un usuario como delegado y configurar las llamadas simultáneas de delegados

En este ejemplo se agrega un usuario como delegado y se configuran las llamadas simultáneas de delegados.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

## Cambiar la regla de llamadas simultáneas de delegados

En este ejemplo se cambia la regla de llamadas simultáneas configurada en el ejemplo anterior a la regla de demora de timbre.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

## Quitar al delegado

En este ejemplo se quita el delegado.


> [!NOTE]
> Al quitar el último delegado, se deshabilita automáticamente la llamada a delegados.



    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Agregar un delegado y configurar la regla de desvío de llamadas a delegados

En este ejemplo se agrega un delegado y se configura la regla de desvío de llamadas a delegados.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

## Habilitar las llamadas simultáneas y establecer un número de destino

En este ejemplo se habilitan las llamadas simultáneas y se establece un número de destino de llamadas simultáneas.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring


> [!NOTE]
> Para cambiar el número de destino de las llamadas simultáneas de un usuario que ya tenga habilitadas las llamadas simultáneas, mantenga el comando con el modificador /enablesimulring, ya que en caso contrario no se cambiaría el número de destino.



**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

## Deshabilitar llamadas simultáneas

En este ejemplo se deshabilitan las llamadas simultáneas.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Agregar un miembro para llamada de equipo y configurar las llamadas simultáneas en el grupo de miembros de llamada de equipo

En este ejemplo se agrega un miembro de equipo al grupo de llamada de equipo de un usuario y se habilitan las llamadas simultáneas al grupo de llamada de equipo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam


> [!NOTE]
> Al agregar a un miembro a un grupo de llamada de equipo de un usuario se cambiará automáticamente a la configuración de llamadas simultáneas de los usuarios para llamar simultáneamente a su grupo de llamada de equipo.



**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

## Quitar a un miembro del grupo de llamada de equipo

En este ejemplo se quita a un miembro del equipo del grupo de llamada de equipo de un usuario.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com


> [!NOTE]
> Si el miembro que va a quitarse es el único miembro del grupo de llamada de equipo, se deshabilitarán automáticamente las llamadas simultáneas al grupo de llamada de equipo.



**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Establecer la demora de timbre al grupo de llamada de equipo

En este ejemplo se cambia la configuración de hora de demora de timbre al grupo de llamada de equipo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

## Habilitar llamada de equipo

En este ejemplo se habilita la llamada de equipo para un usuario concreto.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam


> [!NOTE]
> Si el grupo de llamada de equipo del usuario no tiene ningún miembro, no se habilitará la llamada de equipo.



**Salida**

## Deshabilitar la llamada de equipo

En este ejemplo se deshabilita la llamada de equipo para un usuario concreto.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Habilitar la respuesta de llamadas grupales y asignar un grupo de respuesta a un usuario

En este ejemplo se asigna un grupo de respuesta a un usuario y se habilita la respuesta de llamadas grupales.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**Salida**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

## Deshabilitar la respuesta de llamadas grupales

En este ejemplo se deshabilita la respuesta de llamadas grupales para un usuario concreto.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup


> [!NOTE]
> Cuando se deshabilita la respuesta de llamadas grupales para un usuario, no se conserva el número de grupo que se asignó al usuario. Si posteriormente quiere volver a habilitar la respuesta de llamadas grupales para ese usuario, deberá volver a asignar el número de grupo con el modificador /enablegrouppickup.



    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

## SYSPrep.ps1

## Descripción

SYSPrep.ps1 es un script de Windows PowerShell que instalará los siguientes requisitos previos de Lync Server 2013 en el equipo de Sistema operativo Windows Server 2008.

  - Microsoft .Net Framework 4.5

  - Microsoft SQL Server Express

  - Windows Powershell version 3.0

  - Paquete redistribuible de Visual C++ 2010

  - Actualizaciones de Internet Information Server

  - Windows Identity Foundation

  - Archivos principales de Lync Server 2013

Aunque el nombre del script es parecido a la herramienta de preparación del sistema de los sistemas operativos Microsoft Windows, en realidad son distintos. Este script solo instalará los requisitos previos para Lync Server 2013. Después de instalar estos requisitos previos, puede utilizarse la herramienta SYSPrep de Windows para crear una imagen del servidor.

## Requisitos

Antes de ejecutar el script SYSPrep.ps1 debe copiar los archivos de los requisitos previos en una carpeta local del equipo de Sistema operativo Windows Server 2008 (por ejemplo, **D:\\Setup)**. Esta carpeta también debe contener una copia de los archivos de Lync Server 2013, en concreto **Setup.exe.** Los archivos de requisitos previos pueden descargarse desde las ubicaciones siguientes:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .Net Framework 4.5</p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows Powershell versión 3.0</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Paquete redistribuible de Visual C++ 2010</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Actualizaciones de Internet Information Server</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup.exe</p></td>
<td><p>Copiar desde medios de Lync Server 2013</p></td>
</tr>
</tbody>
</table>


## Parámetro

El parámetro **–SetupFolder** toma como argumento la ubicación del directorio de los archivos de requisitos previos

## Ejemplos

Para ejecutar el script SYSPrep.ps1 e instalar los requisitos previos de Lync Server 2013, ejecute el comando siguiente en un símbolo del sistema con privilegios elevados:

    ./SysPrep.PS1 -SetupFolder D:\Setup

## Unassigned Number Announcements Migration

La herramienta Unassigned Number Announcements Migration permite a los administradores de Lync mover la configuración de los números sin asignar de la aplicación del anuncio desde un Lync Server o grupo de origen a un Lync Server o grupo de destino.

## Descripción

La herramienta Unassigned Number Announcements Migration es un script de Windows PowerShell script que mueve la configuración de los números sin asignar de la aplicación del anuncio desde un servidor o grupo de origen a un servidor o grupo distinto.

Al ejecutar el script Unassigned Number Announcements Migration realizará las operaciones siguientes:

1.  Mueve todos los archivos de audio utilizados en los anuncios de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen al almacén de archivos del servidor o grupo de destino.
    

    > [!NOTE]
    > Los archivos de audio se eliminan del grupo de origen después de haber sido copiados en el grupo de destino.



2.  Mueve todos los anuncios de números sin asignar configurados para la aplicación del anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.

3.  Reasigna todos los intervalos de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen al servidor o grupo de destino.

Después de ejecutar correctamente el script, todos los intervalos de números sin asignar de la aplicación del anuncio hospedada en el servidor o grupo de origen serán atendidos por la misma configuración por el destino o grupo de destino.

## Salida

El script **Move-CsAnnouncementConfiguration** indica en la ventana del shell de administración de Lync desde donde se ejecuta si la operación de migración se ha completado correctamente o si se han producido errores.

Si la ejecución de la operación es interrumpida por algún error, los intervalos de números sin asignar que se hayan movido correctamente al destino permanecerán en este de forma operativa, mientras que el resto de intervalos de números sin asignar que aún no hayan sido migrados permanecerán en el origen también de forma operativa. Para completar la migración del resto de la configuración, vuelva a ejecutar el script después de corregir el error.

## Finalidad

El script Unassigned Number Announcements Migration puede utilizarse en los tres casos siguientes:

  - **Para migrar la configuración a una nueva versión de Lync Server:** Contoso está en el proceso de migrar a Lync Server 2013 y, como parte del proceso de migración, el administrador de Lync Server desea mover la configuración de los números sin asignar atendidos por la aplicación del anuncio de la implementación de Lync Server 2010 a la nueva implementación de Lync Server 2013. Para mover la configuración, el administrador de Lync Server utiliza la herramienta Unassigned Number Announcements Migration.

  - **Para revertir una implementación de Lync Server 2013 a Lync Server 2010:** ebido a factores inesperados, Contoso debe revertir la migración a la nueva implementación de Lync Server 2013. Para minimizar las interrupciones del servicio, el administrador de Lync Server utiliza la herramienta Unassigned Number Announcements Migration para revertir la configuración de la implementación de Lync Server 2013 a la implementación de Lync Server 2010.

  - **Para mover datos entre implementaciones de Lync:** Contoso está en el proceso de sustituir todos los servidores de un grupo con servidores nuevos. Su estrategia es implementar un nuevo grupo de servidores Lync Server 2013, mover todos los datos del grupo anterior al nuevo y, a continuación, dejar de utilizar el grupo anterior. Después de implementar el nuevo grupo, la herramienta Unassigned Number Announcements Migration se utiliza para mover la configuración del grupo anterior al nuevo.

## Requisitos

Estos son los requisitos principales para ejecutar correctamente la herramienta:

1.  El script debe ejecutarse desde un equipo donde esté instalado Shell de administración de Lync Server 2013.

2.  La aplicación del anuncio ha de estar implementada correctamente en los servidores o grupos de servidores Lync de origen y de destino.

## Script Move-CsAnnouncementConfiguration

El script Move-CsAnnouncementConfiguration requiere los dos parámetros descritos en la tabla siguiente.

![Parámetros Move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Parámetros Move-CsAnnouncementConfiguration.")

## Ejemplos

## Mover la configuración de anuncios de números sin asignar de un grupo de servidores Lync Server 2010 a un grupo de servidores Lync Server 2013

En este ejemplo se mueven los anuncios de números sin asignar desde el grupo de origen (Lync Server 2010) al grupo de destino (Lync Server 2013).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

## Mover la configuración de anuncios de números sin asignar de un grupo de servidores Lync Server 2013 a un grupo de servidores Lync Server 2010

En este ejemplo se mueven los anuncios de números sin asignar desde el grupo de origen (Lync Server 2013) al grupo de destino (Lync Server 2010).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

## Web Conf Data

La herramienta Web Conf Data permite a los administradores del software de comunicaciones Lync Server 2013 tener más control sobre los datos asociados con las conferencias web del organizador. En algunos casos se pueden eliminar los datos de reuniones de un usuario concreto según criterios de marca de tiempo.

## Descripción

Esta herramienta permite al administrador realizar las tareas siguientes:

1.  Buscar todos los datos de conferencias web asociados con un usuario concreto.

2.  Eliminar todos los datos de conferencias web asociados con un usuario concreto.

3.  Eliminar todos los datos de conferencias web asociados con un usuario concreto anteriores a una fecha concreta

4.  Mover todos los datos de conferencias web asociados con un usuario concreto al mover a dicho usuario desde un grupo a otro.


> [!NOTE]
> El Herramientas del kit de recursos para Lync Server 2010 permitía mover todos los datos de conferencias web asociados con un usuario concreto al mover dicho usuario desde un grupo a otro. Dicha funcionalidad de esta herramienta ya no se utiliza en favor del parámetro <STRONG>MoveConferenceData</STRONG>. Para obtener más información sobre este parámetro, consulte el cmdlet <A href="https://technet.microsoft.com/es-es/library/gg398528(v=ocs.15)">Move-CsUser</A>.



Esta herramienta elimina únicamente los datos de las reuniones inactivas. Las reuniones activas (o reuniones en sesiones) no se pueden eliminar.

Esta herramienta debe ejecutarse desde un equipo que se encuentre en el mismo grupo que el usuario de destino. El usuario cuyos datos de contenidos de reuniones vayan a ser administrados por esta herramienta ha de ser hospedado en el mismo grupo de usuarios.

## Salida

Esta herramienta informa de los resultados de todas las operaciones:

  - Si se realiza una consulta, la herramienta genera una lista de todas las carpetas de datos de reuniones inactivas que tengan al usuario como organizador.

  - Si se eliminan datos, la herramienta genera una lista de todas las carpetas de datos de reuniones cuyos datos se eliminarán.

## Requisitos

La herramienta ha de ejecutarse en el mismo grupo donde esté hospedado actualmente el organizador.

La herramienta debe ejecutarse con privilegios de administrador con acceso al almacén de archivos de contenido.

## Ejemplos

En la tabla siguiente se describen los parámetros, algunos de los cuales se han utilizado en los ejemplos.

![Parámetros de herramientas de datos de configuración web.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parámetros de herramientas de datos de configuración web.")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

En el ejemplo anterior se mostraba el funcionamiento de un comando de consulta. La salida de dicho comando sería una lista de todas las carpetas de contenido de reuniones que serían afectadas por esta herramienta.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

En el ejemplo anterior se muestra el comando eliminar. Este comando elimina todas las carpetas de reuniones inactivas de este usuario.

## Resumen

Esta herramienta puede ser un recurso útil para administradores que necesiten un control más preciso en los datos de reuniones de conferencias.

