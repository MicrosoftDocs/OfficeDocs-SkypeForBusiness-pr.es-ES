---
title: Especificar la retención de datos de CDR en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Resumen: Aprenda a administrar datos de grabación de detalles de llamadas (CDR) para Skype empresarial Server.'
ms.openlocfilehash: 7cb9926ee8ec124b2fc75a69653c43c0150b6446
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817679"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Especificar la retención de datos de CDR en Skype empresarial Server
 
**Resumen:** Aprenda a administrar datos de Records detallar (CDR) de Skype empresarial Server.
  
De forma predeterminada, los datos del registro detallado de llamadas (CDR) se purgan una vez transcurridos 60 días. Puede usar la configuración de la página **Registro detallado de llamadas** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita CDR, los datos que se recopilaron antes de habilitarlo también se someterán a la purga.
  
> [!NOTE]
> Configure CDR y la calidad de la experiencia (QoE) para que conserven los datos durante el mismo número de días. Cada llamada de CDR, que se encuentra disponible en la página web Informes del Servidor de supervisión, incluye la información de QoE y CDR. Si la duración de la purga es diferente para CDR y QoE, es posible que algunas llamadas solo incluyan datos de CDR y otras solo de QoE. 
  
Use los procedimientos siguientes para configurar la purga de los datos de CDR. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Para especificar la retención de los datos de CDR

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.  
    
3. En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.
    
4. En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.
    
5. Para activar la purga, seleccione **Habilitar depuración de registros de detalles de llamadas (CDR)**.
    
6. En **Conservar registros de detalles de llamadas durante un máximo de (días):**, seleccione el número máximo de días que desea retener los registros detallados de llamadas.
    
7. En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.
    
8. Haga clic en **Confirmar**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Especificar la retención de CDR mediante cmdlets de Windows PowerShell

Puede crear la configuración de retención de CDR con Windows PowerShell y el cmdlet Set-CsCdrConfiguration. Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>Para especificar la retención de CDR para una ubicación determinada:

- Este comando habilita la purga de los datos de CDR para el sitio de Redmond y configura el sitio para conservar los datos de CDR y de los registros de errores durante 20 días.
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>Para especificar la retención de CDR para varias ubicaciones:

- Este comando configura la retención de CDR para todos los valores de configuración de CDR que se usan en una organización.
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Vea también

[Grabación de detalles de llamadas (CDR) en Skype empresarial Server](call-detail-recording-cdr.md)
