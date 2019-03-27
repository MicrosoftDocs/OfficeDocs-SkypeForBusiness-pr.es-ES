---
title: Información de configuración de CDR de vista en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Resumen: Obtenga información sobre cómo usar el registro de detalles de llamadas (CDR) de Skype para Business Server.'
ms.openlocfilehash: edf3f719ed3d859ff6d7a6c4fcebbf22356277d5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896731"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Información de configuración de CDR de vista en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo usar el registro de detalles de llamadas (CDR) de Skype para Business Server.
  
El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y su duración.
  
Al instalar Skype para Business Server, una única colección global de opciones de configuración de CDR se crea para usted. Los administradores tienen la opción de crear conjuntos personalizados de configuraciones que se podrán aplicar a sitios individuales. Puede ver las opciones de configuración de CDR en uso en la organización mediante Skype para el Panel de Control de servidor empresarial o el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Para ver la información de configuración de CDR mediante el uso de Skype para el Panel de Control de servidor empresarial

1. Skype para el Panel de Control de Business Server haga clic en **supervisión y archivado**.
    
2. En la pestaña **Registro detallado de llamadas**, se mostrará una lista de todas las opciones de configuración de CDR. En cada colección de opciones verá la colección **Nombre**, con independencia de si se habilitó CDR (la propiedad **CDR**) y el purgado (la propiedad **Purgado de CDR**). Para ver información detallada sobre una colección en concreto, haga doble clic sobre la colección o selecciónela, haga clic en **Editar** y, luego, en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una única colección de opciones de configuración al mismo tiempo.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de configuración de CDR mediante el uso de cmdlets de Windows PowerShell

Puede ver opciones de configuración de CDR mediante Windows PowerShell y el cmdlet Get-CsCdrConfiguration. Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Para ver la información de configuración de CDR

- Para ver información acerca de todas las opciones de configuración de CDR, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
  ```
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

Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

