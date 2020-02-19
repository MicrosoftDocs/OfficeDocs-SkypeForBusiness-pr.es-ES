---
title: 'Lync Server 2013: uso del panel de supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b3fb33c8cef77139ec1f2e6ddd13da3847c1ec9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42117313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a>Uso del panel de supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

El panel de supervisión proporciona a los administradores una introducción rápida del uso del sistema y el estado del sistema de Microsoft Lync Server 2013. El panel está diseñado para mostrar una vista agregada de métricas del sistema clave y para hacerlo mostrando:

  - Totales del día actual. Tenga en cuenta que los valores que se muestran para el día actual representan datos que se han registrado desde medianoche hasta la hora actual (en función de la hora local del servidor de informes). Esto significa que normalmente estará viendo los datos de un día parcial y no durante un período de 24 horas. Por ejemplo, si la hora local del servidor es 8:00 A.M., verá ocho horas de datos porque hay ocho horas entre la medianoche y el tiempo actual de 8:00 AM.

  - Los totales de la semana y las tendencias de los totales de las seis últimas semanas.

  - Los totales del mes y los totales de tendencia para los últimos seis meses (solo para el uso del sistema).

Tenga en cuenta que puede usar el cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) para devolver la dirección URL usada para obtener acceso a los informes de supervisión de Lync Server 2013:

    Get-CsReportingConfiguration

De forma predeterminada, el panel de supervisión muestra los datos de las siguientes métricas para la semana actual (y los totales de tendencia de las seis semanas anteriores):

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

**Conversación**

  - Total de conferencias

  - Conferencias de mensajería instantánea

  - Conferencias A/V

  - Conferencias de uso compartido de aplicaciones

  - Conferencias web

  - Total de organizadores

  - Total de minutos de conferencia A/V

  - Lecturas. Minutos de conferencia A/V

  - Total de conferencias RTC

  - Total de participantes RTC

  - Total de minutos de participantes RTC

Además de las métricas de uso del sistema, las métricas siguientes muestran el total del día actual y los seis días anteriores (si selecciona la **vista semanal**) o para la semana actual y las seis últimas semanas si selecciona la **vista mensual**.

</div>

<div>

## <a name="per-user-call-diagnostics"></a>Diagnósticos de llamadas por usuario

**Usuarios con errores de llamadas**

  - Total de usuarios con errores de llamadas

  - Organizadores de conferencias con errores de llamadas

**Usuarios con llamadas de calidad deficiente**

  - Total de usuarios con llamadas de calidad deficiente

</div>

<div>

## <a name="call-diagnostics"></a>Diagnósticos de llamadas

Punto a punto

  - Total de errores

  - Porcentaje de errores generales

  - Porcentaje de errores de mensajería instantánea

  - Porcentaje de errores de audio

  - Tasa de errores de uso compartido de aplicaciones

Conversación

  - Total de errores

  - Porcentaje de errores generales

  - Porcentaje de errores de mensajería instantánea

  - Porcentaje de errores de A/V

  - Tasa de errores de uso compartido de aplicaciones

Cinco servidores principales por sesiones con error

</div>

<div>

## <a name="media-quality-diagnostics"></a>Diagnósticos de calidad de medios

Punto a punto

  - Total de llamadas de calidad deficiente

  - Porcentaje de llamadas de calidad deficiente

  - Llamadas RTC con mala calidad

Conversación

  - Total de llamadas de calidad deficiente

  - Porcentaje de llamadas de calidad deficiente

  - Llamadas RTC con mala calidad

Principales servidores con un porcentaje de llamadas de mala calidad

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a>Trabajar con el panel de supervisión

Como se indicó, de forma predeterminada, se muestran los totales de la semana actual y se muestran los valores de tendencia de las seis últimas semanas. Si prefiere ver los totales del mes actual (así como los valores de tendencia de los últimos seis meses), haga clic en el vínculo **vista mensual** en la esquina superior derecha del panel. Si decide ver los totales mensuales, el texto del vínculo cambiará a la **vista semanal**. Puede volver a la vista semanal haciendo clic en ese vínculo.

<div>


> [!TIP]  
> El panel de supervisión le limita a mirar los totales de la semana en curso (o mes) y los valores de tendencia de las seis últimas semanas (o meses). No puede cambiar estas fechas y horas. Por ejemplo, no puede usar el panel para ver totales de informes para el período de tiempo que comienza nueve meses.



</div>

Los valores que se muestran en las columnas **esta semana**, **este mes**o **hoy** le vinculan a información más detallada sobre el elemento. Tenga en cuenta que el nombre de columna y los valores que se muestran en la columna con frecuencia serán distintos en función de la métrica elegida y dependiendo de si ha seleccionado la vista semanal o mensual. Por ejemplo, si hace clic en los totales que se muestran para la métrica de **inicios de sesión de usuario únicos** , verá el **Informe de registro de usuario** para el período de tiempo especificado. Puede volver al panel de supervisión en cualquier momento haciendo clic en **Panel**.

<div>


> [!TIP]  
> También puede acceder a la Página principal de informes del servidor de supervisión haciendo clic en el vínculo <STRONG>informes</STRONG> de la esquina superior derecha del panel.



</div>

La columna **tendencia** muestra un gráfico de líneas simple que muestra los totales de las seis últimas semanas (o en función de la métrica y el intervalo de tiempo, los últimos seis días o los últimos seis meses). Estos gráficos de líneas simples muestran un punto de datos sin etiquetar para cada período de tiempo (por ejemplo, un punto de datos sin etiquetar para cada una de las seis últimas semanas). Sin embargo, puede recuperar los valores reales de estos gráficos manteniendo el puntero del mouse sobre el gráfico. En ese caso, una información sobre herramientas muestra los valores máximos y mínimos en el gráfico.

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a>Exportar datos desde el panel de supervisión

El panel de supervisión ofrece varias formas de exportar la vista del panel actual. En la barra de herramientas del panel, verá un icono similar a un disquete con una flecha verde adjunta. Si hace clic en este icono, aparecerá una lista desplegable que proporciona los siguientes formatos de exportación de datos:

  - Archivo XML con datos de informe

  - Archivo CSV (delimitado por comas)

  - PDF

  - Archivo MHTML (archivo web)

  - Excel

  - Archivo TIFF

  - Word

Para exportar la vista del panel actual (y sus valores), haga clic en la opción de exportación que desee. Lync Server 2013 genera un informe en el formato especificado y, a continuación, ofrece la opción de abrir el informe o guardarlo. Tenga en cuenta que, de forma predeterminada, Lync Server títulos el **Panel de supervisión** de informes y lo guarda en la carpeta descargas. Para dar al informe un nombre diferente o para almacenarlo en una carpeta diferente, haga clic en la flecha situada junto al botón **Guardar** y, a continuación, haga clic en **Guardar como**. Si está bien con el **Panel de supervisión** de nombres y si tiene el informe guardado en la carpeta descargas, solo tiene que hacer clic en el botón **Guardar** .

Es posible que, al intentar exportar datos de panel, aparezca un cuadro de diálogo de **alerta de seguridad** junto con el mensaje "la configuración actual no permite la descarga de este archivo". Si esto ocurre, haga lo siguiente:

  - En Internet Explorer, seleccione **Opciones de Internet**.

  - En el cuadro de diálogo **Opciones de Internet** , en la ficha **seguridad** , haga clic en **sitios de confianza** y, a continuación, en **sitios**.

  - En el cuadro de diálogo **sitios de confianza** , haga clic en **Agregar** para agregar los informes de Lync Server 2013 que ejecutan Lync Server 2013 a las colecciones de sitios web de confianza.

  - Haga clic en **cerrar** y, a continuación, en **Aceptar**.

Tendrá que actualizar el panel de supervisión antes de que los cambios surtan efecto. Para ello, presione F5 o haga clic en el icono **Actualizar** de la barra de herramientas del panel. (El icono de **actualización** es un círculo con un par de flechas verdes en él.)

También puede crear una hoja de cálculo de Excel que incluya fuentes de datos activos, que incluye vínculos a los últimos datos del panel de supervisión. Para crear un archivo de fuente de datos activo, haga clic en el icono naranja **exportar a la fuente de datos** de la barra de herramientas.

Si prefiere imprimir el panel actual, haga clic en el icono de la impresora en la barra de herramientas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

