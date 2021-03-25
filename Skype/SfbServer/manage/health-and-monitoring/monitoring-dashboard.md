---
title: Uso del Panel de supervisión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Resumen: obtenga información sobre el Panel de supervisión en Skype Empresarial Server.'
ms.openlocfilehash: 83a04a60e63deb39666ee4d042f74973b7d16d0b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118609"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a>Uso del Panel de supervisión en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el Panel de supervisión en Skype Empresarial Server.
  
El Panel de supervisión proporciona a los administradores una introducción rápida del estado del sistema de Skype Empresarial Server y el uso del sistema. El panel está diseñado para mostrar una vista agregada de las métricas clave del sistema y para ello se muestran las siguientes:
  
- Totales del día actual. Tenga en cuenta que los valores mostrados para el día actual representan datos que se han registrado desde la medianoche hasta la hora actual (en función de la hora local del servidor de informes). Esto significa que normalmente verá datos durante un día parcial y no durante un período de 24 horas. Por ejemplo, si la hora local del servidor es las 8:00 a.m., verá ocho horas de datos porque hay ocho horas entre la medianoche y la hora actual de las 8:00 a.m.
    
- Totales de la semana y totales de tendencia de las últimas seis semanas.
    
- Totales del mes y totales de tendencia de los últimos seis meses (solo para uso del sistema).
    
Tenga en cuenta que puede usar el cmdlet [Get-CsReportingConfiguration](/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) para devolver la dirección URL usada para obtener acceso a los informes de supervisión de Skype Empresarial Server:
  
```PowerShell
Get-CsReportingConfiguration
```

De forma predeterminada, el Panel de supervisión muestra los datos de las siguientes métricas de la semana actual (y los totales de tendencia de las seis semanas anteriores):
  
## <a name="system-usage-metrics"></a>Métricas de uso del sistema

 **Registro**
  
- Inicios de sesión de usuario únicos
    
  **Punto a punto**
  
- Total de sesiones
    
- Sesiones de mensajería instantánea
    
- Sesiones de audio
    
- Sesiones de vídeo
    
- Uso compartido de aplicaciones
    
- Total de minutos de sesión de audio
    
- Promedio de minutos de sesión de audio
    
  **Conferencia**
  
- Total de conferencias
    
- Conferencias de mensajería instantánea
    
- Conferencias A/V
    
- Conferencias de uso compartido de aplicaciones
    
- Conferencias web
    
- Organizadores totales
    
- Total de minutos de conferencia A/V
    
- Promedio. Minutos de conferencia A/V
    
- Total de conferencias RTC
    
- Total de participantes RTC
    
- Total de minutos de participantes RTC
    
Además de las métricas de uso del sistema, las siguientes métricas muestran el total del día actual y los seis días anteriores (si selecciona Vista **semanal)** o para la semana actual y las últimas seis semanas si selecciona Vista **mensual**.
  
## <a name="per-user-call-diagnostics"></a>Per-User diagnóstico de llamadas

 **Usuarios con errores de llamada**
  
- Total de usuarios con errores de llamada
    
- Organizadores de conferencias con errores de llamada
    
  **Usuarios con llamadas de mala calidad**
  
- Total de usuarios con llamadas de mala calidad
    
## <a name="call-diagnostics"></a>Diagnóstico de llamadas

Punto a punto
  
- Errores totales
    
- Tasa de errores general
    
- Tasa de errores de MI
    
- Velocidad de errores de audio
    
- Tasa de errores de uso compartido de aplicaciones
    
Conferencia
  
- Errores totales
    
- Tasa de errores general
    
- Tasa de errores de MI
    
- Tasa de errores A/V
    
- Tasa de errores de uso compartido de aplicaciones
    
Principales cinco servidores por sesiones con errores
  
## <a name="media-quality-diagnostics"></a>Diagnósticos de calidad de medios

Punto a punto
  
- Llamadas totales de mala calidad
    
- Porcentaje de llamadas de mala calidad
    
- Llamadas RTC con mala calidad
    
Conferencia
  
- Llamadas totales de mala calidad
    
- Porcentaje de llamadas de mala calidad
    
- Llamadas RTC con mala calidad
    
Principales servidores peores por porcentaje de llamadas de mala calidad
  
## <a name="working-with-the-monitoring-dashboard"></a>Trabajar con el Panel de supervisión

Como se ha indicado, los totales predeterminados se muestran para la semana actual y los valores de tendencia se muestran durante las últimas seis semanas. Si prefiere ver los totales del mes actual (así como los valores  de tendencia de los últimos seis meses), haga clic en el vínculo Vista mensual en la esquina superior derecha del panel. Si decide ver totales mensuales, el texto del vínculo cambiará a **Vista semanal**. Puede volver a la vista semanal haciendo clic en ese vínculo.
  
> [!TIP]
> El Panel de supervisión le restringe a ver los totales de la semana actual (o mes) y los valores de tendencia de las últimas seis semanas (o meses). No puede cambiar estas fechas y horas. Por ejemplo, no puede usar el Panel para ver los totales de informes del período de tiempo que comenzó hace nueve meses. 
  
Los valores que se muestran en **las columnas This week**, This **month** o **Today** le vinculan a información más detallada sobre el elemento. Tenga en cuenta que el nombre de columna y los valores que se muestran en esa columna a menudo variarán según la métrica elegida y en función de si ha seleccionado una vista semanal o una vista mensual. Por ejemplo, si hace clic en los totales que se muestran para la métrica Inicios de sesión de usuario **únicos,** verá el **Informe** de registro de usuarios para el período de tiempo especificado. Puede volver al Panel de supervisión en cualquier momento haciendo clic en **Panel**.
  
> [!TIP]
> También puede obtener acceso a la página  principal informes del servidor de supervisión haciendo clic en el vínculo Informes de la esquina superior derecha del panel.
  
La **columna Tendencia** muestra un gráfico de línea simple que muestra totales de las últimas seis semanas (o, según la métrica y el intervalo de tiempo, los últimos seis días o los últimos seis meses). Estos gráficos de línea simples muestran un punto de datos sin etiquetar para cada período de tiempo (por ejemplo, un punto de datos sin etiquetar para cada una de las últimas seis semanas). Sin embargo, puede recuperar los valores reales de estos gráficos manteniendo el puntero del mouse sobre el gráfico. En ese caso, una sugerencia de herramienta muestra los valores máximos y mínimos en el gráfico.
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a>Exportación de datos desde el panel de supervisión

El Panel de supervisión proporciona varias formas de exportar la vista del panel actual. En la barra de herramientas Panel, verá un icono que parece un disquete con una flecha verde adjunta. Si hace clic en este icono, aparecerá una lista desplegable que le dará los siguientes formatos de exportación de datos:
  
- Archivo XML con datos de informe
    
- Archivo CSV (delimitado por comas)
    
- PDF
    
- Archivo MHTML (archivo web)
    
- Excel
    
- Archivo TIFF
    
- Word
    
Para exportar la vista de panel actual (y sus valores), haga clic en la opción de exportación deseada. Skype Empresarial Server genera un informe en el formato especificado y, a continuación, le ofrece la opción de abrir ese informe o guardarlo. Tenga en cuenta que, de forma predeterminada, Skype Empresarial Server título el panel de supervisión del informe y lo guarda en la carpeta descargas.  Para dar al informe un nombre diferente o para almacenarlo en  una carpeta diferente, haga clic en la flecha situada junto al botón Guardar y, a continuación, haga clic **en Guardar como**. Si está bien con el nombre **Panel de supervisión** y con el informe guardado en la carpeta Descargas, puede hacer clic en el **botón** Guardar.
  
Es posible que, al intentar exportar datos  del panel, aparezca un cuadro de diálogo Alerta de seguridad junto con el mensaje "La configuración actual no permite descargar este archivo". Si esto ocurre, haga lo siguiente:
  
- En Internet Explorer, seleccione **Opciones de Internet**.
    
- En el cuadro **de diálogo Opciones de Internet,** en la **pestaña** Seguridad, haga clic en **Sitios** de confianza y, a continuación, haga clic **en Sitios**.
    
- En el **cuadro de**  diálogo Sitios de confianza, haga clic en Agregar para agregar el Skype Empresarial Server que ejecuta informes de Skype Empresarial Server a las colecciones de sitios web de confianza.
    
- Haga clic **en Cerrar** y, a continuación, en **Aceptar**.
    
A continuación, deberá actualizar el Panel de supervisión antes de que los cambios sumen efecto. Para ello, presione F5 o haga clic en el icono **Actualizar** de la barra de herramientas Panel. (El **icono Actualizar** es un círculo con un par de flechas verdes en él).
  
También puede crear una hoja de cálculo de Excel que incluya fuentes de datos en directo, que incluya vínculos a los últimos datos del Panel de supervisión. Para crear un archivo de fuente de datos en directo, haga clic en el icono naranja **Exportar** a fuente de datos de la barra de herramientas.
  
Si prefiere imprimir el panel actual, haga clic en el icono de impresora de la barra de herramientas.
