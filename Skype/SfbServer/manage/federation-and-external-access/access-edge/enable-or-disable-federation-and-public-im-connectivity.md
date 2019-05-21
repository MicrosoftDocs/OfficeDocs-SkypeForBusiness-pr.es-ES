---
title: Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La compatibilidad con la Federación es necesaria para habilitar a los usuarios que tienen una cuenta con un cliente de confianza o una organización asociada, incluidos los dominios y usuarios de los proveedores de mensajería instantánea (mi) pública a los que usted proporciona soporte técnico, para colaborar con los usuarios de su Organización.
ms.openlocfilehash: 86cc3e66b2e3252b6b25ff4bef09d3abeb4badf0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280246"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Skype empresarial Server

La compatibilidad con la Federación es necesaria para habilitar a los usuarios que tienen una cuenta con un cliente de confianza o una organización asociada, incluidos los dominios y usuarios de los proveedores de mensajería instantánea (mi) pública a los que usted proporciona soporte técnico, para colaborar con los usuarios de su Organización. La Federación también es necesaria para usar un proveedor de servicios de Exchange hospedado para proporcionar correo de voz a usuarios de voz de empresa cuyos buzones se encuentran en un servicio de Exchange hospedado como Microsoft Exchange Online. Una vez que haya establecido una relación de confianza con estos dominios externos, puede autorizar a los usuarios de esos dominios a que tengan acceso a su implementación y participen en las comunicaciones de Skype empresarial Server. Esta relación de confianza se denomina Federación y no está relacionada con una relación de confianza de Active Directory o no depende de ella.

Para admitir el acceso de usuarios de dominios federados, debe habilitar la Federación. Si habilita la Federación de su organización, también debe especificar si desea implementar las siguientes opciones:

  - **Habilitar la detección**   de dominios asociados si habilita esta opción, Skype empresarial Server usará los registros del sistema de nombres de dominio (DNS) para intentar descubrir dominios no incluidos en la lista de dominios permitidos, lo que evalúa automáticamente el tráfico entrante de descubierto los socios federados y limitan o bloquean el tráfico según el nivel de confianza, la cantidad de tráfico y la configuración de administrador. Si no selecciona esta opción, acceso de usuarios federados solo se habilitará para los usuarios de los dominios que incluya en la lista de dominios permitidos. Independientemente de si selecciona esta opción, puede especificar que los dominios individuales se bloqueen o se permitan, incluido el acceso restringido a servidores específicos que ejecuten el servicio perimetral de acceso en el dominio federado. Para obtener más información sobre cómo controlar el acceso por parte de los dominios federados, consulte [configurar la compatibilidad de dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Enviar una renuncia de archivado a los socios**     federados el aviso de declinación de responsabilidades se envía a los socios federados que el archivado de la implementación está en su lugar. Si admite el archivado de comunicaciones externas con dominios federados, debe habilitar la notificación de renuncia de archivado para avisar a los socios de que sus mensajes se han archivado.

Si posteriormente desea impedir de forma temporal o permanente el acceso de los usuarios de dominios federados, puede deshabilitar la Federación de su organización. Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios federados de su organización, incluyendo la especificación de las opciones de Federación adecuadas para que la organización admita.

> [!NOTE]  
> Habilitar la Federación para la organización solo especifica que los servidores que ejecutan el servicio perimetral de acceso admiten el enrutamiento a dominios federados. Los usuarios de dominios federados no pueden participar en conversaciones o conferencias de su organización hasta que también configure al menos una directiva para admitir el acceso de usuarios federados. Los usuarios de proveedores de servicios de mensajería instantánea pública no pueden participar en mensajes instantáneos o conferencias de su organización hasta que también configure al menos una directiva para que admita la conectividad de mensajería instantánea pública. Skype empresarial Server no puede usar un servicio de Exchange hospedado para proporcionar contestación de llamadas, Outlook Voice Access (incluido el correo de voz) o servicios de operador automático para usuarios cuyos buzones se encuentran en un servicio de Exchange hospedado hasta que se configure una voz hospedada Directiva de correo que proporciona información de enrutamiento. Para obtener más información sobre cómo configurar directivas para la comunicación con usuarios de dominios federados en otras organizaciones, consulte [administrar dominios federados SIP para su organización](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Además, si desea admitir la comunicación con usuarios de proveedores de servicios de mensajería instantánea, debe configurar directivas para admitirlo y también configurar la compatibilidad de los proveedores de servicios individuales que desee admitir. Para obtener más información, consulte [administrar proveedores federados SIP para su organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios federados para su organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **configuración del borde de Access**.

4.  En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración del límite de acceso**, realice una de las siguientes acciones:
    
      - Para habilitar el acceso de usuarios federados para su organización, active la casilla **Habilitar comunicaciones con usuarios federados** .
    
      - Para deshabilitar el acceso de usuarios federados para su organización, desactive la casilla **Habilitar comunicaciones con usuarios federados** .

6.  Si seleccionó la casilla **Habilitar comunicaciones con usuarios federados** , haga lo siguiente:
    
    1.  Si desea admitir el descubrimiento automático de dominios asociados, active la casilla de verificación **Habilitar la detección de dominios asociados** .
    
    2.  Si su organización admite el archivado de comunicaciones externas, active la casilla de verificación **Enviar renuncia de archivado a socios federados** .

7.  Haga clic en **Confirmar**.

Para permitir a los usuarios federados colaborar con los usuarios de su implementación de Skype empresarial Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md). Para controlar el acceso a dominios federados específicos, vea [configurar la compatibilidad de dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública mediante cmdlets de Windows PowerShell

La Federación y la conectividad de mensajería instantánea pública también se pueden administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar la Federación y la conectividad de mensajería instantánea pública

  - Para habilitar la Federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Para deshabilitar la Federación y la conectividad de mensajería instantánea pública

  - Para deshabilitar la Federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

