---
title: Eliminar una directiva de PIN en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Resumen: Eliminar de acceso telefónico conferencias de un usuario de PIN de Skype para Business Server 2015.'
ms.openlocfilehash: b64a4509105214358549f320cf8885d6386986f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="delete-a-pin-policy-in-skype-for-business-server-2015"></a>Eliminar una directiva de PIN en Skype Empresarial Server 2015
 
**Resumen:** Eliminar de acceso telefónico conferencias de un usuario de PIN de Skype para Business Server 2015.
  
Siga estos pasos para eliminar una directiva de número de identificación personal (PIN).
  
> [!NOTE]
> No puede eliminar la directiva global de PIN. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para eliminar una directiva de NIP en Skype para Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, escriba en el campo de búsqueda el nombre completo o parcial de la directiva que desea eliminar.
    
5. En la lista de directivas, haga clic en la directiva que desea, en **Editar** y en **Eliminar**.
    
6. Haga clic en **Aceptar**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Quitar directivas de NIP mediante Cmdlets de Windows PowerShell

Puede eliminar directivas de NIP mediante Windows PowerShell y el cmdlet Remove-CsPinPolicy. Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-remove-a-specific-pin-policy"></a>Quitar una directiva de PIN específica

- Este comando quita la Directiva de PIN con la RedmondPinPolicy de identidad:
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Quitar todas las directivas de PIN que se aplican al ámbito del sitio

- Este comando quita todas las directivas de PIN configuradas en el ámbito del sitio:
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Quitar todas las directivas de PIN que permiten el uso de patrones comunes

- Y este elimina todas las Directivas de PIN que permiten el uso de patrones comunes:G
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .
  

