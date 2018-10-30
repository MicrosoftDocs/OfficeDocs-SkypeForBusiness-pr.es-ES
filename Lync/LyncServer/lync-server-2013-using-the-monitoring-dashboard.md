﻿---
title: Uso del panel de supervisión en Lync Server 2013
TOCTitle: Uso del panel de supervisión en Lync Server 2013
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49889763
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso del panel de supervisión en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-05_

El panel de supervisión proporciona rápidamente a los administradores información general sobre el estado del sistema Microsoft Lync Server 2013 y su uso. El panel se ha diseñado para que aparezca una vista agregada de las métricas clave del sistema. Para ello, visualiza:

  - Los totales del día en curso. Tenga en cuenta que los valores que aparecen para el día en curso representan los datos registrados desde medianoche hasta la hora en curso (basada en la hora local del servidor de informes). Esto quiere decir que normalmente verá datos de parte de un día y no de un período de 24 horas. Por ejemplo, si para el servidor son las 8 de la mañana, verá datos correspondientes a ocho horas, es decir, los datos del período transcurrido entre medianoche y la hora actual (8 de la mañana).

  - Los totales de la semana y las tendencias de los totales en las últimas seis semanas.

  - Los totales del mes y las tendencias de los totales en los últimos seis meses (solo para el uso del sistema).

Tenga en cuenta que puede usar el cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsReportingConfiguration) para devolver la dirección URL utilizada para acceder a los informes de supervisión de Lync Server 2013:

    Get-CsReportingConfiguration

Normalmente, el panel de supervisión muestra los datos de la semana de las métricas siguientes (y las tendencias de los totales de las seis semanas anteriores):

## Métricas de uso del sistema

**Registro**

  - Inicios de sesión de usuario únicos

**Punto a punto**

  - Total de sesiones

  - Sesiones de mensajería instantánea

  - Sesiones de audio

  - Sesiones de vídeo

  - Uso compartido de aplicaciones

  - Total de minutos de sesiones de audio

  - Media de minutos de sesiones de audio

**Conferencia**

  - Total de conferencias

  - Conferencias de mensajería instantánea

  - Conferencias A/V

  - Conferencias de uso compartido de aplicaciones

  - Conferencias web

  - Total de organizadores

  - Total de minutos de conferencia A/V

  - Media de minutos de conferencia A/V

  - Total de conferencias RTC

  - Total de participantes RTC

  - Total de minutos de participantes RTC

Además de las métricas de uso del sistema, las métricas siguientes muestran el total del día actual y de los seis días anteriores (si selecciona **Vista semanal**) o de la semana actual y de las seis semanas anteriores, si selecciona **Vista mensual**.

## Diagnósticos de llamadas por usuario

**Usuarios con errores de llamadas**

  - Total de usuarios con errores de llamadas

  - Organizadores de conferencias con errores de llamadas

**Usuarios con llamadas de calidad deficiente**

  - Total de usuarios con llamadas de mala calidad

## Diagnósticos de llamadas

Punto a punto

  - Total de errores

  - Porcentaje general de errores

  - Porcentaje de errores de mensajería instantánea

  - Porcentaje de errores de audio

  - Porcentaje de errores de uso compartido de aplicaciones

Conferencia

  - Total de errores

  - Porcentaje general de errores

  - Porcentaje de errores de mensajería instantánea

  - Porcentaje de errores de A/V

  - Porcentaje de errores de uso compartido de aplicaciones

5 servidores principales por sesiones con error

## Diagnósticos de calidad de medios

Punto a punto

  - Total de llamadas de calidad deficiente

  - Porcentaje de llamadas de calidad deficiente

  - Total de llamadas RTC de calidad deficiente

Conferencia

  - Total de llamadas de calidad deficiente

  - Porcentaje de llamadas de calidad deficiente

  - Total de llamadas RTC de calidad deficiente

Los peores servidores por porcentaje de llamadas de calidad deficiente

## Trabajar con el panel de supervisión

Tal como hemos indicado, se muestran los totales predeterminados de la semana en curso y los valores de las tendencias de las seis últimas semanas. Si prefiere ver los totales del mes actual (así como los valores de las tendencias de los últimos seis meses), haga clic en el vínculo **Vista mensual** de la esquina superior derecha del panel. Si decide ver los totales mensuales, el texto del vínculo cambiará a **Vista semanal**. Puede volver a la vista semanal haciendo clic en el vínculo.

> [!TIP]  
> El panel de supervisión le limita la consulta a los totales de la semana en curso (o el mes en curso) y a los valores de las tendencias de las seis últimas semanas (o seis últimos meses). Estas fechas y horas no se pueden cambiar. Por ejemplo, con el panel no se pueden ver los totales de informe de un período que se inició nueve meses antes.



Los valores que aparecen en las columnas **Esta semana**, **Este mes** u **Hoy** le vinculan a información más detallada sobre el elemento. Tenga en cuenta que el nombre de la columna y los valores que aparecen en ella cambiarán a menudo en función de la métrica elegida y en función de si ha seleccionado vista semanal o vista mensual. Por ejemplo, si hace clic en los totales que aparecen en la métrica **Inicios de sesión de usuario únicos**, verá el **Informe de registro de usuario** del período de tiempo especificado. Puede volver al panel de supervisión en cualquier momento, haciendo clic en **Panel**.

> [!TIP]  
> También puede obtener acceso a la página principal de informes del Servidor de supervisión haciendo clic en el vínculo <strong>Informes</strong> de la esquina superior derecha del panel.



La columna **Tendencia** muestra un gráfico de línea sencilla con los totales de las últimas seis semanas (o, en función de la métrica y del intervalo de tiempo, los últimos seis días o seis meses). Estos gráficos de línea sencilla muestran un punto de datos sin etiquetar por cada período de tiempo (por ejemplo, un punto de datos sin etiquetar por cada una de las seis últimas semanas). Ahora bien, puede recuperar los valores reales de estos gráficos manteniendo el puntero del mouse sobre el gráfico. En dicho caso, la información sobre herramientas muestra los valores máximo y mínimo del gráfico.

## Exportar datos desde el panel de supervisión

El panel de supervisión proporciona varias formas de exportar la vista del panel actual. En la barra de herramientas del panel, verá un icono con el aspecto de un disquete con una flecha verde vinculada. Si hace clic en el icono, aparecerá una lista desplegable que le presentará los siguientes formatos de exportación de datos:

  - Archivo XML con datos de informe

  - Archivo CSV (delimitado por comas)

  - PDF

  - Archivo MHTML (archivo web)

  - Excel

  - Archivo TIFF

  - Word

Para exportar la vista de panel actual (y sus valores), haga clic en la opción de exportación deseada. Lync Server 2013 genera un informe en el formato especificado y después le da la opción de abrir el informe o guardarlo. Tenga en cuenta que, normalmente, Lync Server titula el informe **Panel de supervisión** y lo guarda en la carpeta de descargas. Para darle al informe otro nombre o guardarlo en otra carpeta, haga clic en la flecha situada al lado del botón **Guardar** y después haga clic en **Guardar como**. Si le parece bien el nombre **Panel de supervisión** y está de acuerdo en guardar el informe en la carpeta Descargas, solo tiene que hacer clic en el botón **Guardar**.

Es posible que, cuando intente exportar datos del panel, aparezca el cuadro de diálogo **Alerta de seguridad** junto con el mensaje "La configuración actual no permite descargar este archivo". Si ocurre esto, haga lo siguiente:

  - En Internet Explorer, seleccione **Opciones de Internet**.

  - En el cuadro de diálogo **Opciones de Internet**, en la pestaña **Seguridad**, haga clic en **Sitios de confianza** y después en **Sitios**.

  - En el cuadro de diálogo **Sitios de confianza**, haga clic en **Agregar** para agregar el Lync Server 2013 que ejecuta los informes de Lync Server 2013 en las colecciones de sitios web de confianza.

  - Haga clic en **Cerrar** y después en **Aceptar**.

Necesitará actualizar el panel de supervisión antes de que entren en vigor los cambios. Para ello, presione F5 o haga clic en el icono **Actualizar** de la barra de herramientas del panel. (El icono **Actualizar** es un círculo que contiene un par de flechas verdes).

También puede crear una hoja de cálculo de Excel que contenga fuentes de datos activos, lo que incluye vínculos con los últimos datos del panel de supervisión. Para crear un archivo de fuentes de datos activos, haga clic en el icono naranja **Exportar a fuente de datos** de la barra de herramientas.

Si prefiere imprimir el panel actual, haga clic en el icono de la impresora de la barra de herramientas.

