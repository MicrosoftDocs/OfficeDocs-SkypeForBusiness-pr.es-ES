---
title: Habilitar y deshabilitar el acceso de usuarios remotos
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si habilita el acceso de usuarios remotos para los usuarios remotos, los usuarios remotos compatibles conectan a través de Internet y no tienen conexión con una red privada virtual para colaborar con los usuarios internos con Skype para Business Server.
ms.openlocfilehash: aea136e6c8758fd646a20b8bc7a64a393d45a3e7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199930"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Habilitar o deshabilitar el acceso de usuarios remotos en Skype para Business Server

Los usuarios remotos son los usuarios de la organización que tienen una identidad de Active Directory persistente dentro de la organización. Los usuarios remotos a menudo inicie sesión en Skype para Business Server desde fuera de la red mediante el uso de una red privada virtual (VPN) cuando no están conectados a la red de su organización. Los usuarios remotos incluyen a los empleados que trabajan en casa o de viaje y otros trabajadores remotos, como proveedores de confianza, que se hayan concedido credenciales de empresa. Si habilita el acceso de usuarios remotos para los usuarios remotos, los usuarios remotos compatibles conectan a través de Internet y no tienen conexión con una red privada virtual para colaborar con los usuarios internos con Skype para Business Server.

Para permitir el acceso de usuarios remotos, debe habilitar el acceso de usuarios remotos. Cuando se habilita el acceso de usuarios remotos, habilitarla para toda la organización. Si más adelante desea temporal o permanente impedir el acceso de usuarios remotos, se puede deshabilitar para su organización. Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios remotos para su organización.


> [!NOTE]  
> Habilitación del acceso de usuarios remotos sólo se especifica que los servidores que ejecutan el servicio de servidor perimetral de acceso admiten comunicaciones con usuarios remotos, pero los usuarios remotos no pueden participar en conferencias en su organización o de mensajería instantánea (mi) hasta que configure también en menos de una directiva para administrar el uso de acceso de usuarios remotos. Skype para la configuración de directiva de Business Server que se aplican en un nivel de directiva puede invalidar la configuración que se aplica en el nivel de directiva de otra. Skype para la prioridad de la directiva de Business Server es: directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva Global (menos influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto. Para obtener información detallada acerca de cómo configurar las directivas para el uso de acceso de usuarios remotos, vea [Configurar directivas para controlar el acceso de usuarios remotos en Skype para Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios remotos para su organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, luego, en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso** , haga clic en **Global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, realice una de las siguientes opciones:
    
      - Para habilitar el acceso de usuarios remotos para su organización, active la casilla de verificación **Habilitar el acceso de usuarios remotos** .
    
      - Para deshabilitar el acceso de usuarios remotos para su organización, desactive la casilla de verificación **Habilitar el acceso de usuarios remotos** .

6.  Haga clic en **Confirmar**.

Para habilitar los usuarios remotos iniciar sesión en los servidores que ejecutan Skype para Business Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios remotos. Para obtener información detallada, vea [Configurar directivas para controlar el acceso de usuarios remotos en Skype para Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar el acceso de usuarios remotos mediante el uso de cmdlets de Windows PowerShell

Acceso de usuarios remotos puede administrarse mediante el uso de Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de Business Server 2013 o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Para habilitar el acceso de usuarios remotos

  - Para habilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Para deshabilitar el acceso de usuarios remotos

  - Para deshabilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


