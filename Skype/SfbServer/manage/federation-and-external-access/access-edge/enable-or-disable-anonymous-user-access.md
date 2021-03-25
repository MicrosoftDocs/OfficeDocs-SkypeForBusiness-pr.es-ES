---
title: Habilitar y deshabilitar el acceso de usuario anónimo
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
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
description: ''
ms.openlocfilehash: a65cd80311aaf1d13d5d9471ff285b94545176d1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119389"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Habilitar o deshabilitar el acceso de usuarios anónimos en Skype Empresarial Server

Los usuarios anónimos son usuarios que no tienen una cuenta de usuario en los Servicios de dominio de Active Directory de la organización o en un dominio federado compatible, pero pueden ser invitados a participar de forma remota en una conferencia local. Al permitir la participación anónima en reuniones, permite a los usuarios anónimos (es decir, usuarios cuya identidad se comprueba a través de la clave de reunión o conferencia solamente) unirse a reuniones. Permitir la participación anónima requiere habilitarla para su organización.

Si más adelante desea impedir de forma temporal o permanente el acceso de usuarios anónimos, puede deshabilitarlo para su organización. Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios anónimos para su organización.

> [!NOTE]  
> Al habilitar el acceso de usuarios anónimos para la organización, solo se especifica que los servidores que ejecutan el servicio perimetral de acceso admiten el acceso de usuarios anónimos. Los usuarios anónimos no pueden participar en ninguna reunión de la organización hasta que también configure al menos una directiva de conferencia y la aplique a uno o varios usuarios o grupos de usuarios. Los únicos usuarios que pueden invitar a usuarios anónimos a reuniones son aquellos usuarios a los que se asigna una directiva de conferencia configurada para admitir usuarios anónimos. Para obtener más información sobre cómo configurar directivas de conferencia para admitir la invitación a usuarios anónimos, vea [Manage conferencing policies](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios anónimos para su organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para habilitar el acceso de usuarios anónimos para su organización, active la casilla Habilitar **comunicaciones con** usuarios anónimos.
    
      - Para deshabilitar el acceso de usuarios anónimos para su organización, desactive la casilla Habilitar **comunicaciones con usuarios** anónimos.

6.  Haga clic en **Confirmar**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar el acceso de usuarios anónimos mediante Windows PowerShell cmdlets

Puede administrar el acceso de usuarios anónimos mediante Windows PowerShell y el cmdlet **Set-CsAccessEdgeConfiguration.** Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Para habilitar el acceso de usuarios anónimos

  - Para habilitar el acceso de usuarios anónimos, establezca el valor de la **propiedad AllowAnonymousUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Para deshabilitar el acceso de usuarios anónimos

  - Para deshabilitar el acceso de usuarios anónimos, establezca el valor de la **propiedad AllowAnonymousUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Consulta también

[Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
