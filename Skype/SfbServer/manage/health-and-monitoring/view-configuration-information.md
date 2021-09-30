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
ms.localizationpriority: medium
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Summary: Learn how to use Call Detail Recording (CDR) in Skype for Business Server.'
ms.openlocfilehash: f115c41215f4a559957cae3d85a7276501a96710
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011964"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Ver información de configuración de CDR en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo usar la grabación de detalles de llamadas (CDR) en Skype Empresarial Server.
  
El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas en conferencia. Estos datos de uso abarcan información sobre quién llamó a quién, cuándo se llamó y la duración de la llamada.
  
Al instalar Skype Empresarial Server, se crea una única colección global de opciones de configuración de CDR. Los administradores también tienen la opción de crear colecciones de opciones de configuración personalizadas que se pueden aplicar a sitios individuales. Puede ver las opciones de configuración de CDR que se usan en su organización mediante el Panel de control de Skype Empresarial Server o el cmdlet [Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Para ver la información de configuración de CDR mediante el Panel de control de Skype Empresarial Server

1. En el Panel de control de Skype Empresarial Server, haga clic **en Supervisión y archivado.**
    
2. En la pestaña **Registro detallado de llamadas**, se mostrará una lista de todas las opciones de configuración de CDR. En cada colección de opciones verá la colección **Nombre**, con independencia de si se habilitó CDR (la propiedad **CDR**) y el purgado (la propiedad **Purgado de CDR**). Para ver información detallada sobre una colección en concreto, haga doble clic sobre la colección o selecciónela, haga clic en **Editar** y, luego, en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una única colección de opciones de configuración al mismo tiempo.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de configuración de CDR mediante Windows PowerShell cmdlets

Puede ver las opciones de configuración de CDR mediante Windows PowerShell y el cmdlet Get-CsCdrConfiguration cdr. Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso Windows PowerShell para conectarse a Skype Empresarial Server, vea [Administración remota de PowerShell de Microsoft Lync.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) El proceso es el mismo en Skype Empresarial Server.
  
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
