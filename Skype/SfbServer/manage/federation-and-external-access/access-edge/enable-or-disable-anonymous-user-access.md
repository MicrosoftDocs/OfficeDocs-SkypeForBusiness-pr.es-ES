---
title: Habilitar y deshabilitar el acceso anónimo de usuarios
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a368a364f39fe8178e9ce4f17a17bea96fea7b23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280274"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Habilitar o deshabilitar el acceso de usuarios anónimos en Skype empresarial Server

Los usuarios anónimos son usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de su organización o en un dominio federado admitido, pero se les puede invitar a participar de forma remota en una conferencia local. Al permitir la participación anónima en las reuniones, habilita los usuarios anónimos (es decir, los usuarios cuya identidad se comprueba a través de la reunión o de la clave de conferencia) para unirse a las reuniones. Permitir la participación anónima requiere habilitarlo para su organización.

Si posteriormente desea impedir de forma temporal o permanente el acceso de usuarios anónimos, puede deshabilitarlo para su organización. Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios anónimos a su organización.

> [!NOTE]  
> Al permitir el acceso de usuarios anónimos a su organización, solo se especifica que los servidores que ejecutan el servicio perimetral de acceso admiten el acceso de usuarios anónimos. Los usuarios anónimos no pueden participar en ninguna reunión de su organización hasta que también configure al menos una directiva de conferencia y la aplique a uno o más usuarios o grupos de usuarios. Los únicos usuarios que pueden invitar a usuarios anónimos a las reuniones son aquellos a los que se les ha asignado una directiva de conferencia que está configurada para admitir usuarios anónimos. Para obtener más información sobre cómo configurar directivas de conferencia para que admitan la invitación a usuarios anónimos, vea [Administrar directivas de conferencia](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios anónimos para su organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **configuración del borde de Access**.

4.  En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración del límite de acceso**, realice una de las siguientes acciones:
    
      - Para habilitar el acceso de usuarios anónimos para su organización, seleccione la casilla de verificación **habilitar las comunicaciones con usuarios anónimos** .
    
      - Para deshabilitar el acceso de usuarios anónimos para su organización, desactive la casilla **habilitar las comunicaciones con usuarios anónimos** .

6.  Haga clic en **Confirmar**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar el acceso de usuarios anónimos mediante cmdlets de Windows PowerShell

Puede administrar el acceso de usuarios anónimos mediante Windows PowerShell y el cmdlet **set-CsAccessEdgeConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Para habilitar el acceso de usuarios anónimos

  - Para habilitar el acceso de usuarios anónimos, establece el valor de la propiedad **AllowAnonymousUsers** en True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Para deshabilitar el acceso de usuarios anónimos

  - Para deshabilitar el acceso de usuarios anónimos, establece el valor de la propiedad **AllowAnonymousUsers** en False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Vea también

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
