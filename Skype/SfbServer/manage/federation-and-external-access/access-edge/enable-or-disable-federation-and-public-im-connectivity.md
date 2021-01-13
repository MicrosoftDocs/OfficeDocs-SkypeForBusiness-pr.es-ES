---
title: Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
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
description: Es obligatorio tener compatibilidad para la federación con el fin de que los usuarios que dispongan de una cuenta con un cliente de confianza o con una organización de un socio, incluso dominios y usuarios de proveedores de mensajería instantánea pública que usted admita, puedan colaborar con los usuarios de su organización.
ms.openlocfilehash: 390b23a92f91d762c3703a36c063dde54dff1de1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817420"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública en Skype Empresarial Server

Es obligatorio tener compatibilidad para la federación con el fin de que los usuarios que dispongan de una cuenta con un cliente de confianza o con una organización de un socio, incluso dominios y usuarios de proveedores de mensajería instantánea pública que usted admita, puedan colaborar con los usuarios de su organización. La federación también es necesaria para usar un proveedor de servicios hospedados de Exchange para proporcionar correo de voz a usuarios de Telefonía IP empresarial cuyos buzones de correo se ubican en un servicio hospedado de Exchange como Microsoft Exchange Online. Cuando haya establecido una relación de confianza con estos dominios externos, puede autorizar a los usuarios de esos dominios para que accedan a su implementación y participen en las comunicaciones de Skype Empresarial Server. Esta relación de confianza se denomina federación y no está relacionada ni depende de una relación de confianza con Active Directory.

Para admitir el acceso de usuarios de dominios federados, es preciso que habilite la federación. Si habilita la federación en su organización, deberá especificar también si se van a implementar las opciones siguientes:

  - **Habilitar la detección de dominios asociados**   Si habilita esta opción, Skype Empresarial Server usa registros del Sistema de nombres de dominio (DNS) para intentar detectar dominios que no aparecen en la lista de dominios permitidos, evaluando automáticamente el tráfico entrante de socios federados detectados y limitando o bloqueando ese tráfico en función del nivel de confianza, la cantidad de tráfico y la configuración del administrador. Si no selecciona esta opción, el acceso de usuarios federados se habilitará solamente para los usuarios en los dominios que haya incluido en la lista de dominios admitidos. Independientemente de si selecciona esta opción o no, podrá especificar que se bloqueen o permitan dominios individuales, incluso restringir el acceso de servidores específicos que se ejecuten en el servicio perimetral de acceso del dominio federado. Para obtener más información sobre cómo controlar el acceso por dominios federados, consulte Configurar la [compatibilidad con dominios externos permitidos.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)

  - **Enviar un aviso de declinación de responsabilidades de archivado a socios federados**    Se envía un aviso de declinación de responsabilidades a los socios federados que el archivado de la implementación está en su lugar. Si admite el archivado de las comunicaciones externas con los dominios de socios federados, debe habilitar la notificación de declinación de responsabilidad para avisar a los socios que sus mensajes están siendo archivados.

Si más adelante desea impedir, de forma temporal o permanente, el acceso de usuarios de dominios federados, puede deshabilitar la para su organización. Use el procedimiento que aparece en esta sección para habilitar o deshabilitar el acceso de usuarios federados en su organización, así como para especificar las opciones de federación apropiadas para su organización.

> [!NOTE]  
> Si se habilita la federación para la organización solo se indica que los servidores que ejecutan el servicio perimetral de acceso admiten el enrutamiento a dominios federados. Los usuarios de dominios federados no pueden participar en la mensajería instantánea o conferencias en su organización hasta que configure asimismo al menos una directiva para admitir el acceso de usuarios federados. Los usuarios de proveedores de servicios de mensajería instantánea pública no podrán participar en la mensajería instantánea ni en conferencias de la organización hasta que configure también al menos una directiva para admitir conectividad de mensajería instantánea pública. Skype Empresarial Server no puede usar un servicio de Exchange hospedado para proporcionar respuesta a llamadas, Outlook Voice Access (incluido el correo de voz) ni servicios de operador automático para los usuarios cuyos buzones se encuentran en un servicio de Exchange hospedado hasta que configure una directiva de correo de voz hospedado que proporcione información de enrutamiento. Para obtener más información sobre cómo configurar directivas para la comunicación con usuarios de dominios federados de otras organizaciones, consulte Administrar dominios federados [SIP para su organización.](../sip-domains/manage-sip-federated-domains-for-your-organization.md) Por otra parte, si desea admitir la comunicación con usuarios de los proveedores de servicios de mensajería instantánea, es preciso que configure directivas para aportar tal compatibilidad, así como para aportar compatibilidad a los proveedores de servicios individuales que desee. Para obtener más información, [consulte Administrar proveedores federados SIP para su organización.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios federados en la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para habilitar el acceso de usuarios federados en la organización, active la casilla **Habilitar comunicaciones con usuarios federados**.
    
      - Para deshabilitar el acceso de usuarios federados en la organización, desactive la casilla **Habilitar comunicaciones con usuarios federados**.

6.  Si activó la casilla **Habilitar comunicaciones con usuarios federados**, haga lo siguiente:
    
    1.  Si desea admitir la detección automática de dominios de socios, active la casilla **Habilitar detección de dominio de socio**.
    
    2.  Si la organización admite el archivado de comunicaciones externas, active la casilla **Enviar declinación de responsabilidades de archivado a los socios federados**.

7.  Haga clic en **Confirmar**.

Para permitir que los usuarios federados colaboren con usuarios en su implementación de Skype Empresarial Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para obtener más información, [vea Configurar directivas para controlar el acceso de usuarios federados.](../external-access-policies/configure-policies-to-control-federated-user-access.md) Para controlar el acceso a dominios federados específicos, consulte [Configurar la compatibilidad con dominios externos permitidos.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública mediante cmdlets de Windows PowerShell

La federación y la conectividad de mensajería instantánea pública también se pueden administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration web. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar la federación y la conectividad de mensajería instantánea pública

  - Para habilitar la federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Para deshabilitar la federación y la conectividad de mensajería instantánea pública

  - Para deshabilitar la federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

