---
title: Habilitar y deshabilitar el acceso de usuarios remotos
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: Si habilita el acceso de usuarios remotos para usuarios remotos, los usuarios remotos admitidos se conectan a través de Internet y no tienen que conectarse con una VPN para colaborar con usuarios internos con Skype Empresarial Server.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817400"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Habilitar o deshabilitar el acceso de usuarios remotos en Skype Empresarial Server

Los usuarios remotos son usuarios de la organización que tienen una identidad persistente de Active Directory en la organización. Los usuarios remotos suelen iniciar sesión en Skype Empresarial Server desde fuera de la red mediante una red privada virtual (VPN) cuando no están conectados a la red de su organización. Entre los usuarios se encuentran los empleados que trabajan en casa o fuera de la oficina, así como otros trabajadores remotos, como los proveedores de confianza, a los que se conceden credenciales corporativas. Si habilita el acceso de usuarios remotos para usuarios remotos, los usuarios remotos admitidos se conectan a través de Internet y no tienen que conectarse con una VPN para colaborar con usuarios internos con Skype Empresarial Server.

Si más adelante desea impedir de forma provisional o definitiva el acceso a usuarios de dominios federados, deshabilite la federación para la organización. Para habilitar o deshabilitar el acceso de usuarios federados en su organización, siga el procedimiento de esta sección, que también incluye las opciones de federación adecuadas que debe admitir la organización.


> [!NOTE]  
> Al habilitar el acceso de usuarios remotos solo se especifica que los servidores que ejecuten el servicio perimetral de acceso permitan la comunicación con usuarios remotos, pero dichos usuarios no pueden participar en mensajes instantáneos ni en conferencias de la organización hasta que también se configure una directiva para administrar el uso del acceso de usuarios remotos. La configuración de directiva de Skype Empresarial Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de las directivas de Skype Empresarial Server es: la directiva de usuario (mayor influencia) invalida una directiva de sitio y una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto. Para obtener más información sobre cómo configurar directivas para el uso del acceso de usuarios remotos, consulte Configurar directivas para controlar el acceso de usuarios remotos [en Skype Empresarial Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios remotos en la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y luego en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para habilitar el acceso de usuarios remotos en la organización, active la casilla **Habilitar el acceso remoto de usuarios**.
    
      - Para deshabilitar el acceso remoto de usuarios en la organización, desactive la casilla **Habilitar el acceso remoto de usuarios**.

6.  Haga clic en **Confirmar**.

Para permitir que los usuarios remotos inicien sesión en los servidores que ejecutan Skype Empresarial Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios remotos. Para obtener más información, consulte [Configurar directivas para controlar el acceso de usuarios remotos en Skype Empresarial Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar el acceso de usuarios remotos mediante cmdlets Windows PowerShell remoto

El acceso de usuarios remotos se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration usuario. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server 2013 o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Para habilitar el acceso de usuarios remotos

  - Para habilitar el acceso de usuarios remotos, defina el valor de la propiedad **AllowOutsideUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Para deshabilitar el acceso de usuarios remotos

  - Para inhabilitar el acceso de usuarios remotos, defina el valor de la propiedad **AllowOutsideUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


