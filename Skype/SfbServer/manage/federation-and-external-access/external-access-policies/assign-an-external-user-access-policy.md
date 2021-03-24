---
title: Asignar una directiva de acceso de usuario externo
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si un usuario se ha habilitado para Skype Empresarial Server, puede configurar la federación SIP, el acceso remoto de usuarios y la conectividad de mensajería instantánea pública (MI) en el Panel de control de Skype Empresarial Server aplicando las directivas adecuadas a usuarios específicos.
ms.openlocfilehash: 45e22a0d7951bfe4d58d90a1e5190aa242f7b29a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099056"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Asignar una directiva de acceso de usuario externo a un usuario habilitado para Skype Empresarial

Si un usuario se ha habilitado para Skype Empresarial Server, puede configurar la federación SIP, el acceso remoto de usuarios y la conectividad de mensajería instantánea pública (MI) en el Panel de control de Skype Empresarial Server aplicando las directivas adecuadas a usuarios específicos. Por ejemplo, si creó una directiva para admitir el acceso de usuarios remotos, debe aplicarla al usuario antes de que el usuario pueda conectarse a Skype Empresarial Server desde una ubicación remota y colaborar con usuarios internos desde la ubicación remota.


> [!NOTE]  
> Para permitir el acceso de usuarios externos, debe habilitar la compatibilidad para cada tipo de acceso de usuarios externos que desee permitir y configurar las directivas adecuadas y otras opciones para controlar su uso. Para obtener más información, vea [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).


Use el procedimiento descrito en este tema para aplicar una directiva de acceso de usuarios externos creada previamente a una o varias cuentas de usuario.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario externo a una cuenta de usuario

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en  **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar** y, a continuación, en  **Mostrar detalles**.

5.  En **Editar usuario de Skype Empresarial Server** en Directiva de acceso **externo,** seleccione la directiva de usuario que desea aplicar.
     
> [!NOTE]  
> La **\<Automatic>** configuración aplica la configuración predeterminada del servidor o la directiva global.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Asignar directivas Per-User de acceso externo mediante cmdlets Windows PowerShell externos

Las directivas de acceso externo por usuario se pueden asignar mediante Windows PowerShell y el cmdlet Grant-CsExternalAccessPolicy usuario. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para asignar una directiva de acceso externo por usuario a un solo usuario

  - Este comando asigna la directiva de acceso externo por usuario RedmondExternalAccessPolicy al usuario Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para asignar una directiva de acceso externo por usuario a varios usuarios

  - Este comando asigna la directiva de acceso externo por usuario USAExternalAccessPolicy a todos los usuarios que tienen cuentas en la unidad organizativa (OU) de los Estados Unidos en Active Directory. Para obtener más información sobre el parámetro OU usado en este comando, consulte la documentación del cmdlet [Get-CsUser.](/powershell/module/skype/Get-CsUser)
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Para desasignación de una directiva de acceso externo por usuario

  - Este comando anula la asignación de una directiva de acceso externo por usuario que se había asignado a Ken Myer. Una vez anulada la asignación, el usuario Ken Myer será administrado por la directiva global o, si la hay, por su directiva de sitio local. Las directivas de sitio tienen preferencia sobre la directiva global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Para obtener más información, vea el tema de ayuda del cmdlet [Grant-CsExternalAccessPolicy.](/powershell/module/skype/Grant-CsExternalAccessPolicy)