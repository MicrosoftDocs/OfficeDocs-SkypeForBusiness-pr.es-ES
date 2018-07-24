---
title: Uso de informes de supervisión en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: 'Resumen: Obtenga información sobre la supervisión de informes en Skype para Business Server.'
ms.openlocfilehash: 68fcf3a738d2cf849bd51959a86f2d61e53db603
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003796"
---
# <a name="using-monitoring-reports-in-skype-for-business-server"></a>Uso de informes de supervisión en Skype para Business Server 
 
**Resumen:** Obtenga información acerca de la supervisión de informes en Skype para Business Server.
  
Skype para Business Server incluye un conjunto de informes estándar que se publican por Microsoft SQL Server Reporting Services. En estos informes, accesibles a través de un explorador web, encontrará información sobre el uso, el diagnóstico de llamadas y la calidad de medios, todo ello basado en el registro detallado de llamadas (CDR) y en los registros de calidad de la experiencia (QoE) que se almacenan en las bases de datos de CDR y QoE.
  
Para usar estos informes, debe instalar los informes de supervisión en un equipo que ejecuta una instancia de SQL Server.
  
## <a name="in-this-section"></a>En esta sección

- [Uso del panel de supervisión en Skype para Business Server](monitoring-dashboard.md) Proporciona a los administradores con una introducción rápida a su estado del sistema y el uso del sistema.
    
- [Informes de uso del sistema en Skype para Business Server](system-usage-reports.md) Proporciona información sobre el uso del sistema en función de los datos de CDR recopilados por Skype para Business Server.
    
- [Llamar a informes de diagnóstico (por usuario) en Skype para Business Server](call-diagnostic-reports-per-user.md) Proporciona información por usuario acerca de las sesiones de punto a punto y conferencias con errores.
    
- [Llamar a los informes de diagnóstico en Skype para Business Server](call-diagnostic-reports.md) Proporciona información de resumen y datos de diagnóstico sobre las sesiones de conferencia y punto a punto con errores.
    
- [Informes de diagnósticos de calidad de medios en Skype para Business Server](media-quality-diagnostic-reports.md) Proporciona información acerca de la calidad de las llamadas, así como información de diagnóstico y solución de problemas para las llamadas con errores.
    
## <a name="locating-records"></a>Localización de registros

Los informes de supervisión muestran únicamente un número limitado de registros en pantalla de cada vez. El número de registros que aparece en una pantalla varía en función del informe. Para ver los registros que no se muestran actualmente en la pantalla puede usar hacia delante y hacia atrás control estándar (que se encuentra en la barra de herramientas de cada informe) que se permiten en una página a través de los datos. También se puede ir rápidamente a la primera o a la última página del conjunto de datos.
  
Además de estos controles, también se puede ir a cualquier página del conjunto de datos escribiendo el número de página en el cuadro **Página actual** y presionando la tecla ENTRAR.
  
Además de poder avanzar por los datos de página en página, todos los informes incluyen también la capacidad limitada de buscar registros. Para buscar registros según un valor determinado, escriba dicho valor en el cuadro **Buscar** y haga clic en **Buscar**. El informe empieza a buscar en los datos y se detiene la primera vez que aparezca el valor escrito en **Buscar**. Para buscar el siguiente registro que cumpla los criterios de búsqueda, haga clic en **Siguiente**.
  
Tal y como se ha mencionado, los informes de supervisión ofrecen únicamente las funciones de búsqueda más básicas; así, por ejemplo, no se puede especificar el campo en el que buscar el valor, sino que se buscan automáticamente los valores coincidentes en todos los campos de todos los registros. Tampoco se pueden usar caracteres comodín en las búsquedas y en todos los casos se buscarán valores parciales. Esto quiere decir que, si se busca 111, la búsqueda detectará no solo el valor 111, sino también los valores 11100, 811, 3112, 611A5B y cualquier otro campo que incluya el valor 111.
  
Cada informe está configurado para mostrar un conjunto de registros predeterminado. Por ejemplo, de forma predeterminada el informe de registro de usuario muestra las actividades de registro de usuario para la semana pasada. En algunos casos, esto puede dar lugar en un informe que no devuelve ningún registro. En este caso, significa que no hay registros de usuario han tenido lugar en la semana pasada. Si ve el mensaje "no hay resultados coinciden con los filtros del informe", pruebe a cambiar los valores de filtro (por ejemplo, cambiar el período de tiempo del mes pasado, en lugar de la semana pasada) y vuelva a ejecutar la consulta. Para obtener información detallada, vea la sección "Filtrado de datos" más adelante en este tema.
  
## <a name="filtering-data"></a>Filtrado de datos

Probablemente en alguna ocasión quiera buscar en un subconjunto de registros únicamente (por ejemplo, solo las sesiones punto a punto frente a las sesiones punto a punto y las sesiones de conferencia juntas). De igual forma, otras veces necesitará reducir el número de registros que la búsqueda devuelve. Un informe solo puede mostrar 1.000 registros en un conjunto de datos de manera predeterminada. Para abordar esta situación, la mayoría de los informes incluye una serie de opciones de filtrado. Por ejemplo, si quiere ver únicamente los registros correspondientes al período de tiempo comprendido entre el 1 y el 15 de enero de 2011, puede especificar la fecha 1 de enero de 2011 en el cuadro **Desde** y la fecha 15 de enero de 2011 en el cuadro **Hasta**. Si después hace clic en **Ver informe**, los datos obtenidos se limitarán a las actividades que ocurrieron entre el 1 y el 15 de enero de 2011.
  
Los filtros de que disponga variarán en función del informe que esté viendo. Para obtener información detallada sobre un informe en particular, consulte el tema de ayuda correspondiente.
  
## <a name="exporting-data"></a>Exportación de datos

Los informes de supervisión ofrecen al menos dos modos distintos de exportar los datos de un informe. Puede usar la opción **Exportar** de la barra de herramientas que aparece en la parte superior de cada informe. Para usar esta opción, seleccione el formato de exportación que desee de la lista desplegable **Seleccionar un formato**, en la que verá los siguientes formatos:
  
- Archivo XML con datos de informe
    
- Archivo CSV (delimitado por comas)
    
- Archivo de Acrobat (PDF)
    
- Archivo MHTML (archivo web)
    
- Archivo de Excel
    
- Archivo TIFF
    
- Archivo de Word
    
Una vez seleccionado el formato, haga clic en **Exportar**. Cuando se abra el cuadro de diálogo **Descarga de archivos**, haga clic en **Guardar**. En el cuadro de diálogo **Guardar como**, seleccione una carpeta de destino, escriba un nombre de archivo y haga clic en **Guardar**.
  
Si tiene Microsoft OneNote instalado, también puede optar por copiar los datos del informe a OneNote. Para ello, haga clic con el botón secundario en el botón **Ver informe** en la barra de tareas. En el cuadro de diálogo **Seleccionar la ubicación en OneNote**, seleccione la sección de OneNote en la que quiera copiar los datos y, luego, haga clic en **Aceptar**.
  

