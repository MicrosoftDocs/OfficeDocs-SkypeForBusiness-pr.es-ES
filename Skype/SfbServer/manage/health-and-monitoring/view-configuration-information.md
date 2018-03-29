---
title: Visualizar la información de configuración de CDR en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Resumen: Conozca cómo usar grabación de detalle llamar (CDR) en Skype para Business Server 2015.'
ms.openlocfilehash: 6eacc6c300cfc1faae843a1dc610b17b45ae9c88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a>Visualizar la información de configuración de CDR en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a usar grabación de detalle llamar (CDR) en Skype para Business Server 2015.
  
El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y su duración.
  
Al instalar Skype para Business Server 2015, una única colección global CDR de opciones de configuración se crea para usted. Los administradores también tienen la opción de crear colecciones de configuración personalizadas que se pueden aplicar a sitios individuales. Puede ver las opciones de configuración de CDR en uso en la organización mediante Skype para Panel de Control de servidor de negocios o el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Para ver información de configuración de CDR mediante Skype para Panel de Control de servidor empresarial

1. En Skype para Business Server Control Panel, haga clic en **supervisión y archivado**.
    
2. En la pestaña **Registro detallado de llamadas**, se mostrará una lista de todas las opciones de configuración de CDR. En cada colección de opciones verá la colección **Nombre**, con independencia de si se habilitó CDR (la propiedad **CDR**) y el purgado (la propiedad **Purgado de CDR**). Para ver información detallada sobre una colección en concreto, haga doble clic sobre la colección o selecciónela, haga clic en **Editar** y, luego, en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una única colección de opciones de configuración al mismo tiempo.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Ver la información de configuración de CDR mediante cmdlets de Windows PowerShell

Puede ver los valores de configuración de CDR mediante Windows PowerShell y el cmdlet Get-CsCdrConfiguration. Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Para ver la información de configuración de CDR

- Para ver información acerca de la configuración de configuración de CDR, escriba el comando siguiente en el Skype para negocios de Shell de administración de servidor y, a continuación, presione ENTRAR:
    
  ```
  Get-CsCdrConfiguration
  ```

    Devolverá información similar a la siguiente:
    
  ```
  Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2

  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

