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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La compatibilidad con la federación es necesaria habilitar a los usuarios que tienen una cuenta con una organización confianza de clientes o socios, incluidos los dominios asociados y los usuarios de los usuarios de proveedor (IM) que admite, para colaborar con los usuarios de mensajería instantánea pública su organización.
ms.openlocfilehash: d82833dcd4e477e2c332c01d3d4ba2fdca5123aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896421"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Skype para Business Server

La compatibilidad con la federación es necesaria habilitar a los usuarios que tienen una cuenta con una organización confianza de clientes o socios, incluidos los dominios asociados y los usuarios de los usuarios de proveedor (IM) que admite, para colaborar con los usuarios de mensajería instantánea pública su organización. Federación también se requiere para usar un proveedor de servicio de Exchange hospedado para proporcionar correo de voz a los usuarios de Enterprise Voice cuyos buzones se encuentren en un servicio hospedado de Exchange como Microsoft Exchange Online. Cuando haya establecido una relación de confianza con estos dominios externos, puede autorizar a los usuarios en esos dominios tener acceso a la implementación y participar en Skype para las comunicaciones Business Server. Esta relación de confianza se denomina federación y no está relacionada con, o dependiente en una relación de confianza de Active Directory.

Para admitir el acceso de usuarios de dominios federados, debe habilitar la federación. Si se habilita la federación para su organización, también debe especificar si se va a implementar las siguientes opciones:

  - **Habilitar la detección de dominio de socio**   Si habilita esta opción, Skype para Business Server usa registros del sistema de nombres de dominio (DNS) para intentar descubrir dominios no incluidos en la lista de dominios permitidos, evaluar automáticamente el tráfico entrante de detectado asociados de socios y limitar o bloquear ese tráfico en función de nivel de confianza, la cantidad de tráfico y las configuraciones de administrador. Si no selecciona esta opción, está habilitado el acceso de usuario federado sólo para los usuarios en los dominios que incluyen en la lista de dominios permitidos. Si selecciona esta opción, puede especificar ese individuo dominios bloqueados o permitidos, incluida la restricción del acceso a servidores específicos que ejecutan el servicio de servidor perimetral de acceso en el dominio federado. Para obtener información detallada acerca de cómo controlar el acceso de dominios federados, vea [Configurar compatibilidad para dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Enviar una renuncia de archivado a los socios federados**     aviso de declinación de responsabilidades se envía a los socios federados que en su implementación de archivado está en su lugar. Si admite el archivado de comunicaciones externas con dominios de socios federados, debe habilitar la notificación de renuncia de archivado advertir a los socios que se van a archivar sus mensajes.

Si más adelante desea impedir el acceso a los usuarios de dominios federados temporal o permanente, puede deshabilitar la federación para su organización. Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios federados de su organización, incluida la especificación de las opciones de federación adecuada para ser compatibles para su organización.

> [!NOTE]  
> Habilitación de la federación para su organización sólo especifica que los servidores que ejecutan el servicio de servidor perimetral de acceso compatible con el enrutamiento de dominios federados. Los usuarios de dominios federados no pueden participar en conferencias en su organización o de mensajería instantánea hasta que también configurar al menos una directiva para admitir el acceso de usuarios federados. Los usuarios de proveedores de servicios de mensajería instantánea pública no pueden participar en conferencias en su organización o de mensajería instantánea hasta que también configurar al menos una directiva para admitir la conectividad de mensajería instantánea pública. Skype para Business Server no puede usar un servicio de Exchange hospedado para proporcionar contestador automático, Outlook Voice Access (incluido el correo de voz), o servicios de operador automático para los usuarios cuyos buzones se encuentren en un servicio hospedado de Exchange hasta que configure una voz hospedado Directiva de correo que proporciona información de enrutamiento. Para obtener información detallada acerca de cómo configurar las directivas para la comunicación con los usuarios de dominios federados en otras organizaciones, vea [Administrar SIP federados dominios para la organización](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Además, si desea admitir la comunicación con usuarios de proveedores de servicios de mensajería instantánea, debe configurar las directivas para admitirlo y configurar también la compatibilidad con los proveedores de servicios individuales que desea admitir. Para obtener información detallada, vea [Administrar SIP federados proveedores para su organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios federados para la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**y, a continuación, haga clic en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso** , haga clic en **Global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, realice una de las siguientes opciones:
    
      - Para habilitar el acceso de usuarios federados para la organización, active la casilla de verificación **Habilitar las comunicaciones con los usuarios federados** .
    
      - Para deshabilitar el acceso de usuarios federados para la organización, desactive la casilla de verificación **Habilitar las comunicaciones con los usuarios federados** .

6.  Si ha seleccionado la casilla de verificación **Habilitar las comunicaciones con los usuarios federados** , haga lo siguiente:
    
    1.  Si desea admitir la detección automática de dominios de socios, active la casilla de verificación **Habilitar la detección de dominio de socio** .
    
    2.  Si la organización admite el archivado de comunicaciones externas, active la casilla de verificación **Enviar declinación de responsabilidades a los socios federados de archivado** .

7.  Haga clic en **Confirmar**.

Para habilitar los usuarios federados puedan colaborar con los usuarios de su Skype para la implementación de Business Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para obtener información detallada, vea [Configurar directivas de control de acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md). Para controlar el acceso de dominios federados concretos, vea [Configurar compatibilidad para dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública mediante el uso de cmdlets de Windows PowerShell

Federación y conectividad de mensajería instantánea pública también se pueden administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar la federación y la conectividad de mensajería instantánea pública

  - Para habilitar la federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Para deshabilitar la federación y la conectividad de mensajería instantánea pública

  - Para deshabilitar la federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

