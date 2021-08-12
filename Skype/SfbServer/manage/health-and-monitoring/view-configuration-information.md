---
title: Ver información de configuración de CDR en Skype Empresarial Server
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
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Resumen: obtenga información sobre cómo usar la grabación detallada de llamadas (CDR) en Skype Empresarial Server.'
ms.openlocfilehash: 058a6538c8486c52fd47354fe4116e339c83a8b9479ec2da214c4f39d8558308
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341885"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Ver información de configuración de CDR en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo usar la grabación de detalles de llamadas (CDR) en Skype Empresarial Server.
  
El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas en conferencia. Estos datos de uso abarcan información sobre quién llamó a quién, cuándo se llamó y la duración de la llamada.
  
Al instalar Skype Empresarial Server, se crea una única colección global de opciones de configuración de CDR. Los administradores también tienen la opción de crear colecciones de opciones de configuración personalizadas que se pueden aplicar a sitios individuales. Puede ver las opciones de configuración de CDR que se usan en su organización mediante Skype Empresarial Server Panel de control o el cmdlet [Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Para ver la información de configuración de CDR mediante Skype Empresarial Server Panel de control

1. En Skype Empresarial Server Panel de control, haga clic **en Supervisión y archivado.**
    
2. En la pestaña **Registro detallado de llamadas**, se mostrará una lista de todas las opciones de configuración de CDR. En cada colección de opciones verá la colección **Nombre**, con independencia de si se habilitó CDR (la propiedad **CDR**) y el purgado (la propiedad **Purgado de CDR**). Para ver información detallada sobre una colección en concreto, haga doble clic sobre la colección o selecciónela, haga clic en **Editar** y, luego, en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una única colección de opciones de configuración al mismo tiempo.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de configuración de CDR mediante Windows PowerShell cmdlets

Puede ver las opciones de configuración de CDR mediante Windows PowerShell y el cmdlet Get-CsCdrConfiguration cdr. Puede ejecutar este cmdlet desde el Shell de administración Skype Empresarial Server desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-view-cdr-configuration-information"></a>Para ver la información de configuración de CDR

- Para ver información sobre todas las opciones de configuración de CDR, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    Devolverá información similar a la siguiente:
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Para obtener más información, vea el tema de ayuda del cmdlet [Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
