---
title: Asignar una directiva de acceso de usuario externo
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si un usuario se ha habilitado para Skype empresarial Server, puede configurar la Federación SIP, el acceso de usuarios remotos y la conectividad de mensajería instantánea pública en el panel de control de Skype empresarial Server mediante la aplicación de las directivas apropiadas a usuarios específicos.
ms.openlocfilehash: c03eb957679877ec512b042e0db624adbb3e6f52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043682"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Asignar una directiva de acceso de usuario externo a un usuario habilitado para Skype empresarial

Si un usuario se ha habilitado para Skype empresarial Server, puede configurar la Federación SIP, el acceso de usuarios remotos y la conectividad de mensajería instantánea pública en el panel de control de Skype empresarial Server mediante la aplicación de las directivas apropiadas a usuarios específicos. Por ejemplo, si ha creado una directiva para admitir el acceso de usuarios remotos, debe aplicarla al usuario antes de que el usuario pueda conectarse a Skype empresarial Server desde una ubicación remota y colaborar con usuarios internos desde la ubicación remota.


> [!NOTE]  
> Para permitir el acceso de usuarios externos, debe habilitar la compatibilidad para cada tipo de acceso de usuarios externos que desee permitir y configurar las directivas adecuadas y otras opciones para controlar su uso. Para obtener más información, consulte [Managing Federation and external Access to Skype for Business Server](../managing-federation-and-external-access.md).


Use el procedimiento descrito en este tema para aplicar una directiva de acceso de usuarios externos creada previamente a una o varias cuentas de usuario.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario externo a una cuenta de usuario

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en  **Usuarios ** y, a continuación, busque en la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar ** y, a continuación, en  **Mostrar detalles **.

5.  En **Editar usuario de Skype empresarial Server** en **Directiva de acceso externo**, seleccione la Directiva de usuario que desea aplicar.
     
> [!NOTE]  
> La configuración de ** \<>automático** aplica el servidor predeterminado o la configuración de la directiva global.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Asignación de directivas de acceso externo por usuario mediante cmdlets de Windows PowerShell

Las directivas de acceso externo por usuario se pueden asignar mediante Windows PowerShell y el cmdlet Grant-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para asignar una directiva de acceso externo por usuario a un solo usuario

  - Este comando asigna la directiva de acceso externo por usuario RedmondExternalAccessPolicy al usuario Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para asignar una directiva de acceso externo por usuario a varios usuarios

  - Este comando asigna la directiva de acceso externo por usuario USAExternalAccessPolicy a todos los usuarios que tienen cuentas en la unidad organizativa (OU) de los Estados Unidos en Active Directory. Para obtener más información sobre el parámetro OU usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Para cancelar la asignación de una directiva de acceso externo por usuario

  - Este comando anula la asignación de una directiva de acceso externo por usuario que se había asignado a Ken Myer. Una vez anulada la asignación, el usuario Ken Myer será administrado por la directiva global o, si la hay, por su directiva de sitio local. Las directivas de sitio tienen preferencia sobre la directiva global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .


