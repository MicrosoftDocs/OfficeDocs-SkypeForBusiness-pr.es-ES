---
title: "Gestionar el acceso de los usuarios a Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Aprenda a habilitar o deshabilitar el acceso a nivel de usuario por cada usuario.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: d1a0262aa41a6e7bbd2d6891c26baf9976ce86c5
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2017
---
<a name="manage-user-access-to-microsoft-teams"></a>Gestionar acceso de los usuarios a Microsoft Teams
=====================================

A nivel de usuario, el acceso a Microsoft Teams puede habilitarse o deshabilitarse por usuario, asignando o quitando la licencia de producto de Microsoft Teams.

Actualmente, no hay opciones de directiva para activar a desactivar características, o un subconjunto de características, de Microsoft Teams a nivel de un usuario individual fuera de la licencia.

| | |
|---------|---------|
|![](media/Manage_user_access_to_Microsoft_Teams_image1.png)<br></br>Nota |Microsoft recomienda que Microsoft Teams se habilite para todos los usuarios de una empresa, de modo que los equipos puedan formarse de manera orgánica para proyectos y otras iniciativas dinámicas. Incluso si decide realizar un piloto, podría ser útil mantener Microsoft Teams habilitado para todos los usuarios, pero solo enfocarse en las comunicaciones con el grupo piloto de usuarios. |

Las licencias de Microsoft Teams se gestionan directamente a nivel de usuario a través de las interfaces de gestión de usuarios del centro de administración de Office 365 Un administrador puede asignar licencias a nuevos usuarios cuando se crean nuevas cuentas, o bien a usuarios con cuentas existentes. El administrador debe tener privilegios de administrador de control de usuarios y de administrador global para Office 365 para poder gestionar licencias de Microsoft Teams.

Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.

![](media/Manage_user_access_to_Microsoft_Teams_image2.png) ![](media/Manage_user_access_to_Microsoft_Teams_image3.png)

Una licencia de usuario de Microsoft Teams puede deshabilitarse en cualquier momento. Una vez que la licencia se deshabilita, se evitará el acceso de los usuarios a Microsoft Teams y el usuario ya no podrá ver Microsoft Teams en el iniciador de aplicaciones y la página de inicio de Office 365.

![](media/Manage_user_access_to_Microsoft_Teams_image4.png)

Además de usar el centro de administración de Office 365, los administradores de Office 365 también pueden usar Office 365 PowerShell para asignar y quitar licencias. Para asignar una licencia a un usuario, utilice la siguiente sintaxis:

Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"

En el siguiente ejemplo se asigna una licencia del plan de licencias litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) al usuario belindan@litwareinc.com sin licencia.

Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"

Para obtener más detalles y ejemplos, consulte [*Asignar licencias a cuentas de usuario con PowerShell de Office 365*](https://go.microsoft.com/fwlink/?linkid=855755)

Para quitar licencias de una cuenta de usuario existente, utilice la siguiente sintaxis:

Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"

En el siguiente ejemplo se elimina la licencia litwareinc:ENTERPRISEPACK de la cuenta de usuario BelindaN@litwareinc.com.

Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"

Para obtener más detalles y ejemplos, consulte [*Eliminar licencias de cuentas de usuario con PowerShell de Office 365*](https://go.microsoft.com/fwlink/?linkid=855756)

| | | |
|---------|---------|---------|
|![](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Punto de decisión         |<ul><li>¿Cuál es el plan de su organización para comenzar a usar Microsoft Teams en toda la organización?  (Piloto o Abierto)</li></ul>         |
|![](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Siguientes pasos         |<ul><li>Si realiza la adopción a través de Piloto, decida si desea hacerlo a través de licencias o comunicación dirigida.</li><li>Según cuál sea su decisión, realice los pasos para asegurarse de que solo los usuarios piloto puedan acceder a Microsoft Teams (si es necesario).</li><li>Documente qué usuarios tendrán (o no tendrán) acceso a Microsoft Teams a continuación.</li></ul>         |
