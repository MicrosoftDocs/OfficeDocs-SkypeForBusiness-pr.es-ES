---
title: Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Puede eliminar cualquier sitio o directiva de usuario que aparezca en el Panel de control Skype Empresarial Server en la página Directiva de acceso externo.
ms.openlocfilehash: 2c8d3e73d0bccc0ea7ea25bdfed0b871a51e9a82
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388178"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos

Si ha creado o configurado directivas de acceso de usuarios externos que ya no desea usar, puede realizar el siguiente método:

  - Elimine cualquier directiva de usuario o sitio que haya creado.

  - Restablezca la configuración predeterminada de la directiva global. La configuración global predeterminada deniega cualquier tipo de acceso de usuarios externos. La directiva global no puede eliminarse.


Puede eliminar cualquier sitio o directiva de usuario que aparezca en el Panel de control de Skype Empresarial Server en la **página Directiva de acceso** externo. La eliminación de la directiva global no la elimina realmente, pero solo la restablece a la configuración predeterminada, que no incluye compatibilidad con ninguna opción de acceso de usuario externo. Para obtener más información acerca del restablecimiento de la directiva global, consulte [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Para eliminar una directiva de sitio o usuario para el acceso de usuarios externos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  Haga clic en **Acceso de usuarios externos** y seleccione **Directiva de acceso externo**.

4.  En la ficha **Directiva de acceso externo**, haga clic en la directiva de sitio o usuario que desea eliminar, seleccione **Editar** y, a continuación, haga clic en **Eliminar**.

5.  Cuando se le solicite que confirme la eliminación, haga clic en **Aceptar**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Eliminación de directivas de PIN mediante cmdlets Windows PowerShell datos

Las directivas de acceso externo se pueden eliminar mediante Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde el Shell Skype Empresarial Server administración o desde una sesión remota de Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Para quitar una directiva de acceso externo específica

  - Con este comando se quita la directiva de acceso externo aplicada al sitio de Redmond:<br/><br/>Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Para quitar todas las directivas de acceso externo aplicadas al ámbito por usuario

  - Con este comando se quitan todas las directivas de acceso externo configuradas en el ámbito por usuario:<br/><br/>Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Para quitar todas las directivas de acceso externo donde está deshabilitado el acceso de usuarios externos

  - Con este comando se quitan todas las directivas de acceso externo cuando el acceso de usuarios externos se ha deshabilitado:<br/><br/>Get-CsExternalAccessPolicy | Where-Object {$_. EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Para obtener más información, vea el tema de ayuda del cmdlet [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) .
