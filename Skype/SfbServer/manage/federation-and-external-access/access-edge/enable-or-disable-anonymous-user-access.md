---
title: Habilitar y deshabilitar el acceso anónimo de usuarios
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 35104d7d7128e76f7691a4ddf1ad9693a427eb40
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222754"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Habilitar o deshabilitar el acceso de usuarios anónimos en Skype para Business Server

Los usuarios anónimos son usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de su organización o en un dominio federado compatible, pero pueden ser invitados a participar de forma remota en una conferencia local. Permitiendo la participación remota en reuniones permite a los usuarios anónimos (es decir, los usuarios cuya identidad se comprobará mediante la clave de conferencia o reunión sólo) para participar en reuniones. Lo que permite la participación anónima requiere habilitar para la organización.

Si más adelante desea impedir el acceso a los usuarios anónimos temporal o permanente, se puede deshabilitar para su organización. Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuario anónimo para la organización.

> [!NOTE]  
> Al habilitar el acceso de usuarios anónimos para la organización sólo se especifica que los servidores que ejecutan el servicio de servidor perimetral de acceso admitan el acceso de los usuarios anónimos. Los usuarios anónimos no pueden participar en las reuniones de la organización hasta que también configura al menos una directiva de conferencia y aplica a uno o varios usuarios o grupos de usuarios. Los únicos usuarios que pueden invitar a los usuarios anónimos a las reuniones son aquellos usuarios que están asignados a una directiva de conferencia que está configurada para admitir usuarios anónimos. Para obtener información detallada acerca de cómo configurar las directivas de conferencia para admitir inviten a usuarios anónimos, vea [administrar las directivas de conferencia](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios anónimos para la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**y, a continuación, haga clic en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso** , haga clic en **Global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, realice una de las siguientes opciones:
    
      - Para habilitar el acceso de usuario anónimo para la organización, active la casilla de verificación **Habilitar las comunicaciones con los usuarios anónimos** .
    
      - Para deshabilitar el acceso de usuarios anónimos para su organización, desactive la casilla de verificación **Habilitar las comunicaciones con los usuarios anónimos** .

6.  Haga clic en **Confirmar**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar el acceso de usuarios anónimos mediante el uso de cmdlets de Windows PowerShell

Puede administrar el acceso de usuarios anónimos mediante el uso de Windows PowerShell y el cmdlet **Set-CsAccessEdgeConfiguration** . Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Para habilitar el acceso de usuarios anónimos

  - Para habilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Para deshabilitar el acceso de usuarios anónimos

  - Para deshabilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Consulte también

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
