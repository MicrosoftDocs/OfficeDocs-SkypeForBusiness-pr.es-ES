---
title: Especificar la retención de datos de CDR en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Resumen: Obtenga información sobre cómo administrar los detalles de llamadas (CDR) datos de Skype para Business Server.'
ms.openlocfilehash: 72fbb679a260462086930fc0457b5c748447cc29
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878748"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Especificar la retención de datos de CDR en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo administrar los detalles de llamadas (CDR) datos de Skype para Business Server.
  
De forma predeterminada, los datos del registro detallado de llamadas (CDR) se purgan una vez transcurridos 60 días. Puede usar la configuración de la página **Registro detallado de llamadas** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita CDR, los datos que se recopilaron antes de habilitarlo también se someterán a la purga.
  
> [!NOTE]
> Configure CDR y la calidad de la experiencia (QoE) para que conserven los datos durante el mismo número de días. Cada llamada de CDR, que se encuentra disponible en la página web Informes del Servidor de supervisión, incluye la información de QoE y CDR. Si la duración de la purga es diferente para CDR y QoE, es posible que algunas llamadas solo incluyan datos de CDR y otras solo de QoE. 
  
Use los procedimientos siguientes para configurar la purga de los datos de CDR. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Para especificar la retención de los datos de CDR

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.
    
4. En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.
    
5. Para activar la purga, seleccione **Habilitar depuración de registros de detalles de llamadas (CDR)**.
    
6. En **Conservar registros de detalles de llamadas durante un máximo de (días):**, seleccione el número máximo de días que desea retener los registros detallados de llamadas.
    
7. En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.
    
8. Haga clic en **Confirmar**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Especificación de retención de CDR mediante el uso de cmdlets de Windows PowerShell

Puede crear la configuración de retención de CDR mediante el uso de Windows PowerShell y el cmdlet Set-CsCdrConfiguration. Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>Para especificar la retención de CDR para una ubicación determinada:

- Este comando habilita la purga de los datos de CDR para el sitio de Redmond y configura el sitio para conservar los datos de CDR y de los registros de errores durante 20 días.
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>Para especificar la retención de CDR para varias ubicaciones:

- Este comando configura la retención de CDR para todos los valores de configuración de CDR que se usan en una organización.
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Consulte también

[Detalles de llamadas (CDR) en Skype para Business Server](call-detail-recording-cdr.md)
