---
title: Eliminar una colección existente de opciones de configuración de CDR en Skype Empresarial Server
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Summary: Learn how to remove CDR configuration settings in Skype Empresarial Server.'
ms.openlocfilehash: ad23743e6361a0931499c373e337bb9869738fa8e00d5d856ad272e96798655b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276825"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Eliminar una colección existente de opciones de configuración de CDR en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo quitar las opciones de configuración de CDR en Skype Empresarial Server.
  
El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas en conferencia. Estos datos de uso abarcan información sobre quién llamó a quién, cuándo se llamó y la duración de la llamada.
  
Al instalar Skype Empresarial Server, se crea una única colección global de opciones de configuración de CDR. Los administradores también tienen la opción de crear colecciones de opciones de configuración personalizadas que se pueden aplicar a sitios individuales. Por diseño, las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global. Si elimina la configuración con ámbito en el sitio, el CDR se puede administrar en dicho sitio utilizando la configuración global.
  
Tenga en cuenta que también puede "eliminar" la configuración global. Sin embargo, esta no se quitará realmente. En su lugar, todas las propiedades de dicha colección se restablecerán a sus valores predeterminados. Por ejemplo, la purga está habilitada de forma predeterminada en una colección de opciones de configuración de CDR. Supongamos que modifica la colección global y la purga se deshabilita. Si más adelante elimina la configuración global, todas las propiedades se restablecerán a sus valores predeterminados. En este caso, eso significa que la purga volverá a estar habilitada.
  
Puede quitar las opciones de configuración de CDR mediante el Panel de control Skype Empresarial Server o el cmdlet [Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Para quitar las opciones de configuración de CDR con Skype Empresarial Server Panel de control

1. En Skype Empresarial Server Panel de control, haga clic **en Supervisión y archivado.** 
    
2. En la pestaña **Registro detallado de llamadas**, seleccione la colección o colecciones de opciones de CDR que se van a quitar. Para seleccionar varias colecciones, haga clic en la primera colección, mantenga presionada la tecla Ctrl y haga clic en otras colecciones.
    
3. Haga clic en **Editar** y, a continuación, en **Eliminar**.
    
4. En el cuadro Skype Empresarial Server panel de control, haga clic en **Aceptar**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración de CDR mediante Windows PowerShell cmdlets

Puede eliminar las opciones de configuración de registro detallado de llamadas mediante Windows PowerShell y el cmdlet **Remove-CsCdrConfiguration.** Puede ejecutar este cmdlet desde el Shell de administración Skype Empresarial Server desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Para quitar una colección especificada de opciones de configuración de CDR

 Este comando quita las opciones de configuración de CDR que se aplican al sitio Redmond:
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de CDR aplicadas al ámbito del sitio

 Este comando quita todas las opciones de configuración de CDR que se aplican al ámbito del sitio:
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>Consulte también

[Purgar manualmente el registro detallado de llamadas y las bases de datos de calidad de la experiencia en Skype Empresarial Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)