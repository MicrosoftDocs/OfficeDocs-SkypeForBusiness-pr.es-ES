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
localization_priority: Normal
description: Si se ha habilitado un usuario en Skype empresarial Server, puede configurar la Federación SIP, el acceso de usuarios remotos y la conectividad de mensajería instantánea (mi) pública en el panel de control de Skype empresarial Server aplicando las directivas apropiadas a usuarios específicos.
ms.openlocfilehash: ae8bea38a01f9211fc3338faf3e97f737c99e1a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280176"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Asignar una directiva de acceso de usuarios externos a un usuario habilitado para Skype empresarial

Si se ha habilitado un usuario en Skype empresarial Server, puede configurar la Federación SIP, el acceso de usuarios remotos y la conectividad de mensajería instantánea (mi) pública en el panel de control de Skype empresarial Server aplicando las directivas apropiadas a usuarios específicos. Por ejemplo, si creó una directiva para admitir el acceso de usuarios remotos, debe aplicarla al usuario antes de que el usuario pueda conectarse a Skype empresarial Server desde una ubicación remota y colaborar con usuarios internos desde la ubicación remota.


> [!NOTE]  
> Para admitir el acceso de usuarios externos, debe habilitar la compatibilidad para cada tipo de acceso de usuario externo que desee admitir, así como configurar las directivas apropiadas y otras opciones para controlar su uso. Para obtener más información, consulte [administrar la Federación y el acceso externo a Skype empresarial Server](../managing-federation-and-external-access.md).


Use el procedimiento de este tema para aplicar una directiva de acceso de usuarios externos creada previamente a una o más cuentas de usuario.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario externo a una cuenta de usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar usuario de Skype empresarial Server** , en **Directiva de acceso externo**, seleccione la Directiva de usuario que desea aplicar.
     
> [!NOTE]  
> La configuración de ** \<Automatic>** aplica el servidor predeterminado o la configuración de la directiva global.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Asignar directivas de acceso externo por usuario mediante cmdlets de Windows PowerShell

Las directivas de acceso externo por usuario se pueden asignar mediante Windows PowerShell y el cmdlet Grant-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para asignar una directiva de acceso externo por usuario a un solo usuario

  - Este comando asigna el RedmondExternalAccessPolicy de directiva de acceso externo por usuario al usuario Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para asignar una directiva de acceso externo por usuario a varios usuarios

  - Este comando asigna el USAExternalAccessPolicy de directiva de acceso externo por usuario a todos los usuarios que tienen cuentas en la OU de Estados Unidos en Active Directory. Para obtener más información sobre el parámetro de Uo que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Para cancelar la asignación de una directiva de acceso externo por usuario

  - Este comando elimina la asignación de una directiva de acceso externo por usuario asignada previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .


