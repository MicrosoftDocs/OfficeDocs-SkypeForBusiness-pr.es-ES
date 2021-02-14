---
title: Especificar la retención de datos de CDR en Skype Empresarial Server
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Resumen: obtenga información sobre cómo administrar los datos del registro detallado de llamadas (CDR) para Skype Empresarial Server.'
ms.openlocfilehash: 01b4765a9fa98a898255c1374115e17c4966e797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814220"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Especificar la retención de datos de CDR en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar los datos del registro detallado de llamadas (CDR) para Skype Empresarial Server.
  
De forma predeterminada, los datos del registro detallado de llamadas (CDR) se purgan una vez transcurridos 60 días. Puede usar la configuración de la página **Registro detallado de llamadas** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita CDR, los datos que se recopilaron antes de habilitarlo también se someterán a la purga.
  
> [!NOTE]
> Configure CDR y la calidad de la experiencia (QoE) para que conserven los datos durante el mismo número de días. Cada llamada de CDR, que se encuentra disponible en la página web Informes del Servidor de supervisión, incluye la información de QoE y CDR. Si la duración de la purga es diferente para CDR y QoE, es posible que algunas llamadas solo incluyan datos de CDR y otras solo de QoE. 
  
Use los procedimientos siguientes para configurar la purga de los datos de CDR. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Para especificar la retención de los datos de CDR:

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.
    
4. En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.
    
5. Para activar la purga, seleccione **Habilitar depuración de registros de detalles de llamadas (CDR)**.
    
6. En **Conservar registros de detalles de llamadas durante un máximo de (días):**, seleccione el número máximo de días que desea retener los registros detallados de llamadas.
    
7. En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.
    
8. Haga clic en **Confirmar**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Especificación de la retención de CDR mediante Windows PowerShell cmdlets

Puede definir la configuración de retención de CDR con Windows PowerShell y el cmdlet Set-CsCdrConfiguration. Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre el uso de Windows PowerShell remoto para conectarse a Skype Empresarial Server, consulte el artículo del blog "Inicio rápido: administración de [Microsoft Lync Server 2010 con PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
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

Para obtener más información, consulte el tema de ayuda del cmdlet [Set-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>Vea también

[Registro detallado de llamadas (CDR) en Skype Empresarial Server](call-detail-recording-cdr.md)
