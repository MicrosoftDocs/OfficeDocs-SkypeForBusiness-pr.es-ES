---
title: Habilitar y deshabilitar el acceso de usuarios remotos
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si habilita el acceso de usuarios remotos para usuarios remotos, los usuarios remotos compatibles se conectan a través de Internet y no tienen que conectarse usando una VPN para colaborar con usuarios internos que usen Skype empresarial Server.
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280239"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Habilitar o deshabilitar el acceso de usuarios remotos en Skype empresarial Server

Los usuarios remotos son usuarios de su organización que tienen una identidad de Active Directory persistente dentro de la organización. Los usuarios remotos a menudo inician sesión en Skype empresarial Server desde fuera de la red mediante una red privada virtual (VPN) cuando no están conectados a la red de su organización. Los usuarios remotos incluyen empleados que trabajan en casa o que están de viaje y otros trabajadores remotos, como proveedores de confianza, a los que se les han concedido credenciales empresariales. Si habilita el acceso de usuarios remotos para usuarios remotos, los usuarios remotos compatibles se conectan a través de Internet y no tienen que conectarse usando una VPN para colaborar con usuarios internos que usen Skype empresarial Server.

Para admitir el acceso de usuarios remotos, debe habilitar el acceso de usuarios remotos. Cuando se habilita el acceso de usuarios remotos, se habilita para toda la organización. Si posteriormente desea evitar el acceso de usuarios remotos de forma temporal o permanente, puede deshabilitarlo para su organización. Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios remotos a su organización.


> [!NOTE]  
> Habilitar el acceso de usuarios remotos solo especifica que los servidores que ejecutan el servicio perimetral de acceso admiten comunicaciones con usuarios remotos, pero los usuarios remotos no pueden participar en la mensajería instantánea (mi) ni en conferencias de su organización hasta que también configure en menos una directiva para administrar el uso del acceso de usuarios remotos. La configuración de directiva de Skype empresarial Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de servidor de Skype empresarial es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto. Para obtener más información sobre cómo configurar directivas para el uso de acceso de usuarios remotos, vea [configurar directivas para controlar el acceso de usuarios remotos en Skype empresarial Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios remotos a su organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, luego, en **Configuración perimetral de acceso**.

4.  En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración del límite de acceso**, realice una de las siguientes acciones:
    
      - Para habilitar el acceso de usuarios remotos a su organización, seleccione la casilla de verificación **Habilitar el acceso de usuarios remotos** .
    
      - Para deshabilitar el acceso de usuarios remotos a su organización, desactive la casilla **Habilitar el acceso de usuarios remotos** .

6.  Haga clic en **Confirmar**.

Para permitir que los usuarios remotos inicien sesión en sus servidores con Skype empresarial Server, también debe configurar al menos una directiva de acceso externo para que admita el acceso de usuarios remotos. Para obtener más información, consulte [configurar directivas para controlar el acceso de usuarios remotos en Skype empresarial Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar el acceso de usuarios remotos mediante cmdlets de Windows PowerShell

El acceso de usuarios remotos se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server 2013 o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Para habilitar el acceso de usuarios remotos

  - Para habilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Para deshabilitar el acceso de usuarios remotos

  - Para deshabilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


