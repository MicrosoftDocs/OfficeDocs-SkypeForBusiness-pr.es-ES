---
title: Asignar una directiva de acceso de usuario externo
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un usuario tiene habilitado para Skype para Business Server, puede configurar la federación SIP, acceso de usuarios remotos e instantánea pública conectividad de mensajería (IM en el Skype) para el Panel de Control de servidor empresarial mediante la aplicación de las directivas apropiadas a usuarios específicos.
ms.openlocfilehash: f07a407fee6f32f4cd4207c93ca19341e409ea78
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197635"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Asignar una directiva de acceso de usuarios externos a un Skype para usuarios de empresa habilitado

Si un usuario tiene habilitado para Skype para Business Server, puede configurar la federación SIP, acceso de usuarios remotos e instantánea pública conectividad de mensajería (IM en el Skype) para el Panel de Control de servidor empresarial mediante la aplicación de las directivas apropiadas a usuarios específicos. Por ejemplo, si ha creado una directiva para permitir el acceso de usuarios remotos, se debe aplicar al usuario antes de que el usuario puede conectarse a Skype para Business Server desde una ubicación remota y colaborar con los usuarios internos de la ubicación remota.


> [!NOTE]  
> Para permitir el acceso de usuarios externos, debe habilitar la compatibilidad con cada tipo de acceso de usuarios externos que desea admitir y configurar las directivas apropiadas y otras opciones para controlar su uso. Para obtener información detallada, vea [Managing federación y el acceso externo a Skype para Business Server](../managing-federation-and-external-access.md).


Use el procedimiento de este tema para aplicar una directiva de acceso de usuarios externos creada previamente a una o más cuentas de usuario.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario externo a una cuenta de usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar Skype para usuarios de empresa Server** en **Directiva de acceso externo**, seleccione la directiva de usuario que desea aplicar.
     
> [!NOTE]  
> La ** \<Automatic>** configuración aplica el servidor predeterminado o la configuración de la directiva global.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Asignación de directivas de acceso externo por usuario mediante el uso de Cmdlets de Windows PowerShell

Directivas de acceso externo por usuario pueden asignarse mediante el uso de Windows PowerShell y el cmdlet Grant-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para asignar una directiva de acceso externo por usuario a un solo usuario

  - Este comando asigna la directiva de acceso externo por usuario RedmondExternalAccessPolicy al usuario Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para asignar una directiva de acceso externo por usuario a varios usuarios

  - Este comando asigna la directiva de acceso externo por usuario USAExternalAccessPolicy a todos los usuarios que tienen cuentas en la unidad organizativa de Estados Unidos en Active Directory. Para obtener más información sobre el parámetro de unidad organizativa que se usa en este comando, consulte la documentación para el cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Para cancelar la asignación de una directiva de acceso externo por usuario

  - Este comando anula la asignación de cualquier directiva de acceso externo por usuario previamente asignada a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Para obtener más información, vea el tema de ayuda para el cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .


