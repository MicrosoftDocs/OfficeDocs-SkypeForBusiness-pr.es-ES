---
title: 'Lync Server 2013: usar el panel de supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50c5a435baf9ef6b2ef24e235270326507b68789
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a>Usar el panel de supervisión de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

El panel de supervisión proporciona a los administradores una breve descripción general del uso del sistema y el estado del sistema de Microsoft Lync Server 2013. El panel está diseñado para mostrar una vista agregada de métricas del sistema clave y para hacerlo mostrando:

  - Los totales del día en curso. Tenga en cuenta que los valores que aparecen para el día en curso representan los datos registrados desde medianoche hasta la hora en curso (basada en la hora local del servidor de informes). Esto quiere decir que normalmente verá datos de parte de un día y no de un período de 24 horas. Por ejemplo, si para el servidor son las 8 de la mañana, verá datos correspondientes a ocho horas, es decir, los datos del período transcurrido entre medianoche y la hora actual (8 de la mañana).

  - Los totales de la semana y las tendencias de los totales en las últimas seis semanas.

  - Los totales del mes y las tendencias de los totales en los últimos seis meses (solo para el uso del sistema).

Tenga en cuenta que puede usar el cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) para devolver la dirección URL que se usa para acceder a los informes de supervisión de Lync Server 2013:

    Get-CsReportingConfiguration

Normalmente, el panel de supervisión muestra los datos de la semana de las métricas siguientes (y las tendencias de los totales de las seis semanas anteriores):

<div>

## <a name="system-usage-metrics"></a>Métricas de uso del sistema

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

**Una conferencia**

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

</div>

<div>

## <a name="per-user-call-diagnostics"></a>Diagnósticos de llamadas por usuario

**Usuarios con errores de llamadas**

  - Total de usuarios con errores de llamadas

  - Organizadores de conferencias con errores de llamadas

**Usuarios con llamadas de calidad deficiente**

  - Total de usuarios con llamadas de mala calidad

</div>

<div>

## <a name="call-diagnostics"></a>Diagnósticos de llamadas

Punto a punto

  - Total de errores

  - Porcentaje general de errores

  - Porcentaje de errores de mensajería instantánea

  - Porcentaje de errores de audio

  - Porcentaje de errores de uso compartido de aplicaciones

Una conferencia

  - Total de errores

  - Porcentaje general de errores

  - Porcentaje de errores de mensajería instantánea

  - Porcentaje de errores de A/V

  - Porcentaje de errores de uso compartido de aplicaciones

5 servidores principales por sesiones con error

</div>

<div>

## <a name="media-quality-diagnostics"></a>Diagnósticos de calidad de medios

Punto a punto

  - Total de llamadas de calidad deficiente

  - Porcentaje de llamadas de calidad deficiente

  - Total de llamadas RTC de calidad deficiente

Una conferencia

  - Total de llamadas de calidad deficiente

  - Porcentaje de llamadas de calidad deficiente

  - Total de llamadas RTC de calidad deficiente

Los peores servidores por porcentaje de llamadas de calidad deficiente

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a>Trabajar con el panel de supervisión

Tal como hemos indicado, se muestran los totales predeterminados de la semana en curso y los valores de las tendencias de las seis últimas semanas. Si prefiere ver los totales del mes actual (así como los valores de las tendencias de los últimos seis meses), haga clic en el vínculo **Vista mensual** de la esquina superior derecha del panel. Si decide ver los totales mensuales, el texto del vínculo cambiará a **Vista semanal**. Puede volver a la vista semanal haciendo clic en el vínculo.

<div>


> [!TIP]  
> El panel de supervisión le limita la consulta a los totales de la semana en curso (o el mes en curso) y a los valores de las tendencias de las seis últimas semanas (o seis últimos meses). Estas fechas y horas no se pueden cambiar. Por ejemplo, con el panel no se pueden ver los totales de informe de un período que se inició nueve meses antes.



</div>

Los valores que aparecen en las columnas **Esta semana**, **Este mes** u **Hoy** le vinculan a información más detallada sobre el elemento. Tenga en cuenta que el nombre de la columna y los valores que aparecen en ella cambiarán a menudo en función de la métrica elegida y en función de si ha seleccionado vista semanal o vista mensual. Por ejemplo, si hace clic en los totales que aparecen en la métrica **Inicios de sesión de usuario únicos**, verá el **Informe de registro de usuario** del período de tiempo especificado. Puede volver al panel de supervisión en cualquier momento, haciendo clic en **Panel**.

<div>


> [!TIP]  
> También puede acceder a la Página principal de informes del servidor de supervisión haciendo clic en el vínculo <STRONG>informes</STRONG> , en la esquina superior derecha del panel.



</div>

La columna **Tendencia** muestra un gráfico de línea sencilla con los totales de las últimas seis semanas (o, en función de la métrica y del intervalo de tiempo, los últimos seis días o seis meses). Estos gráficos de línea sencilla muestran un punto de datos sin etiquetar por cada período de tiempo (por ejemplo, un punto de datos sin etiquetar por cada una de las seis últimas semanas). Ahora bien, puede recuperar los valores reales de estos gráficos manteniendo el puntero del mouse sobre el gráfico. En ese caso, la información sobre herramientas muestra los valores máximos y mínimos en el gráfico.

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a>Exportar datos desde el panel de supervisión

El panel de supervisión proporciona varias formas de exportar la vista del panel actual. En la barra de herramientas del panel, verá un icono con el aspecto de un disquete con una flecha verde vinculada. Si hace clic en el icono, aparecerá una lista desplegable que le presentará los siguientes formatos de exportación de datos:

  - Archivo XML con datos de informe

  - Archivo CSV (delimitado por comas)

  - PDF

  - Archivo MHTML (archivo web)

  - Archivo de Excel

  - Archivo TIFF

  - Archivo de Word

Para exportar la vista de panel actual (y sus valores), haga clic en la opción de exportación deseada. Lync Server 2013 genera un informe en el formato especificado y, a continuación, le ofrece la opción de abrir ese informe o guardarlo. Tenga en cuenta que, de forma predeterminada, Lync Server títulos el **Panel de supervisión** de informes y lo guarda en la carpeta descargas. Para darle al informe otro nombre o guardarlo en otra carpeta, haga clic en la flecha situada al lado del botón **Guardar** y después haga clic en **Guardar como**. Si le parece bien el nombre **Panel de supervisión** y está de acuerdo en guardar el informe en la carpeta Descargas, solo tiene que hacer clic en el botón **Guardar**.

Es posible que, cuando intente exportar datos del panel, aparezca el cuadro de diálogo **Alerta de seguridad** junto con el mensaje "La configuración actual no permite descargar este archivo". Si ocurre esto, haga lo siguiente:

  - En Internet Explorer, seleccione **Opciones de Internet**.

  - En el cuadro de diálogo **Opciones de Internet**, en la pestaña **Seguridad**, haga clic en **Sitios de confianza** y después en **Sitios**.

  - En el cuadro de diálogo **sitios de confianza** , haga clic en **Agregar** para agregar el Lync Server 2013 que ejecuta los informes de Lync Server 2013 a las colecciones de sitios web de confianza.

  - Haga clic en **Cerrar** y, luego, en **Aceptar**.

Necesitará actualizar el panel de supervisión antes de que entren en vigor los cambios. Para ello, presione F5 o haga clic en el icono **Actualizar** de la barra de herramientas del panel (el icono **Actualizar** es un círculo que contiene un par de flechas verdes).

También puede crear una hoja de cálculo de Excel que contenga fuentes de datos activos, lo que incluye vínculos con los últimos datos del panel de supervisión. Para crear un archivo de fuentes de datos activos, haga clic en el icono naranja **Exportar a fuente de datos** de la barra de herramientas.

Si prefiere imprimir el panel actual, haga clic en el icono de la impresora de la barra de herramientas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

