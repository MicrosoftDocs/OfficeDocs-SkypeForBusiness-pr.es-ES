---
title: Eliminar una directiva de PIN en Skype Empresarial Server
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
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Resumen: elimine el PIN de conferencia de acceso telefónico local de un usuario para Skype Empresarial Server.'
ms.openlocfilehash: b85d2bb29f8a1a28279a59f72957d201886d1dc4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096796"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Eliminar una directiva de PIN en Skype Empresarial Server
 
**Resumen:** Elimine el PIN de conferencia de acceso telefónico local de un usuario para Skype Empresarial Server.
  
Siga estos pasos para eliminar una directiva de número de identificación personal (PIN).
  
> [!NOTE]
> No puede eliminar la directiva global de PIN. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para eliminar una directiva de PIN en el Panel de control de Skype Empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, escriba en el campo de búsqueda el nombre completo o parcial de la directiva que desea eliminar.
    
5. En la lista de directivas, seleccione la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.
    
6. Haga clic en **Aceptar**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Quitar directivas de PIN mediante cmdlets Windows PowerShell de datos

Puede eliminar directivas de PIN mediante Windows PowerShell y el cmdlet Remove-CsPinPolicy. Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-remove-a-specific-pin-policy"></a>Para quitar una directiva de PIN específica

- Este comando elimina la Directiva de PIN con la RedmondPinPolicy de identidad:
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Para quitar todas las directivas de PIN aplicadas al ámbito del sitio

- Este comando elimina todas las Directivas de PIN configuradas en el ámbito del sitio:
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Para quitar todas las directivas de PIN que permiten el uso de patrones comunes

- Y este elimina todas las Directivas de PIN que permiten el uso de patrones comunes:G
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsPinPolicy.](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)
