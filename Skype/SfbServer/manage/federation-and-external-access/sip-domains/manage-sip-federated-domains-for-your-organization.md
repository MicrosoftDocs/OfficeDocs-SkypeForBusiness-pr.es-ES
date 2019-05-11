---
title: Administrar dominios federados SIP para la organización
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga información sobre cómo administrar y configurar los dominios SIP que se pueden federar con,
ms.openlocfilehash: aa793c5380c4baaa18876bfa2e2891a8260670dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903176"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Administrar dominios federados SIP para su organización en Skype para Business Server


Para administrar y configurar los dominios SIP que se pueden federar con, puede hacer lo siguiente:

  - Crear o editar una lista de dominios de socios federado de SIP de dominios permitidos.

  - Crear o editar una lista de dominios federados SIP dominios bloqueados.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configurar la compatibilidad con dominios externos permitidos en Skype para Business Server

Si ha configurado la compatibilidad con los socios federados, puede administrar qué dominios concretos pueden federarse con su organización. Configurar uno o más dominios externos específicos como dominios federados permitidos. Para ello, agregue cada dominio a la lista de dominios permitidos. Incluso si está habilitada la detección de socios para su organización, hacer esto si el dominio es un socio federado que es posible que necesite comunicarse con más de 1.000 de los usuarios o es posible que necesite enviar más de 20 mensajes por segundo. Si no está habilitada la detección de socios para su organización, sólo los usuarios de dominios externos que se agregue a la lista de dominios permitidos pueden participar en mensajería instantánea y conferencias con los usuarios de su organización. Si desea restringir el acceso para un dominio federado a un servidor específico que ejecuta el servicio de servidor perimetral de acceso del socio federado, puede especificar el nombre de dominio del servidor que ejecuta el servicio de servidor perimetral de acceso para cada dominio en la lista de dominios permitidos.

> [!NOTE]  
> Este procedimiento describe cómo configurar la compatibilidad con dominios específicos, pero implementar la compatibilidad para los usuarios federados también requiere habilitar la compatibilidad con los usuarios federados de su organización y configurar y aplicar directivas para controlar qué usuarios pueden colaborar con los usuarios federados. Para obtener información detallada acerca de cómo habilitar la compatibilidad con usuarios federados, vea [Habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md). Para obtener información detallada sobre la configuración de directivas para controlar la federación, vea [Configurar directivas de control de acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Para agregar un dominio externo a la lista de dominios permitidos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**y, a continuación, haga clic en **Dominios federados**.
4.  En la página **Dominios federados** , haga clic en **nuevo**y, a continuación, haga clic en **dominio permitido**.
5.  En **Nuevos dominios federados**, haga lo siguiente:
    
      - En **nombre de dominio (o FQDN)**, escriba el nombre de dominio del socio federado.       

        > [!NOTE]  
        > Este nombre debe ser único y no puede existir previamente como un dominio permitido para este servidor que ejecuta el servicio de servidor perimetral de acceso. El nombre no puede superar los 256 caracteres de longitud.<BR><br>La búsqueda en el nombre de dominio de socio federado realiza a una coincidencia de sufijo. Por ejemplo, si escribe **contoso.com**, la búsqueda devolverá también el dominio **it.contoso.com**.<BR><br>Un dominio de socio federado simultáneamente no puede ser bloqueado y permitido. Skype para Business Server impide que esto sucede por lo que no es necesario para la sincronización de las listas.
    
      - Si desea restringir el acceso para este dominio federado para los usuarios de un servidor específico que ejecuta el servicio de servidor perimetral de acceso, en el **servicio de servidor perimetral de acceso (FQDN)**, escriba el FQDN del servidor del dominio federado que ejecuta el servicio de servidor perimetral de acceso.    
      - Si desea proporcionar información adicional, en **comentario**, escriba la información que desea compartir con otros administradores del sistema sobre esta configuración.

6.  Haga clic en **Confirmar**.
7.  Repita los pasos del 4 al 6 para cada dominio de socio federado que desea permitir.

Para habilitar el acceso de usuarios federados, también debe habilitar la compatibilidad con acceso de usuarios federados en la organización. Para obtener información detallada, vea [Habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).

Además, debe configurar y aplicar la directiva a los usuarios que desea que puedan colaborar con los usuarios federados. Para obtener información detallada, vea [Configurar directivas de control de acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurar la compatibilidad con dominios externos bloqueados en Skype para Business Server 

Si ha configurado la compatibilidad con los socios federados, puede administrar qué dominios se bloqueará de federación con su organización. La lista de dominios bloqueados van a actuar como una lista de bloqueo (lista de entradas explícitas que no se podrán) y se aplicará en detección de dominios federados, si tiene habilitada esta opción. Para obtener información detallada, vea [Habilitar o deshabilitar la detección de los socios federados](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Bloquear uno o más dominios externos desde que se conectan a su organización. Para ello, agregue el dominio a la lista de dominios bloqueados.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Para agregar un dominio externo a la lista de dominios bloqueados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**.
4.  Haga clic en **Dominios federados**, haga clic en **nuevo**y, a continuación, haga clic en **dominio bloqueado**.
5.  En **Nuevos dominios federados**, haga lo siguiente:
    
      - En **nombre de dominio (o FQDN)**, escriba el nombre de dominio del socio federado que desea bloquear.

        > [!NOTE]  
        > El nombre no puede superar los 256 caracteres de longitud.<BR><br>La búsqueda en el nombre de dominio de socio federado realiza a una coincidencia de sufijo. Por ejemplo, si escribe **contoso.com**, la búsqueda devolverá también el dominio **it.contoso.com**.<BR><br>Un dominio de socio federado simultáneamente no puede ser bloqueado y permitido. Skype para Business Server impide que esto sucede por lo que no es necesario para la sincronización de las listas.
   
      - (Opcional) En **comentario**, escriba la información que desea compartir con otros administradores del sistema sobre esta configuración.

6.  Haga clic en **Confirmar**.
7.  Repita los pasos del 4 al 6 para cada socio federado que desea bloquear.

Para habilitar el acceso de usuarios federados, también debe habilitar la compatibilidad con acceso de usuarios federados en la organización. Para obtener información detallada, vea [Habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).

Además, debe configurar y aplicar la directiva a los usuarios que desea que puedan colaborar con los usuarios federados. Para obtener información detallada, vea [Configurar directivas de control de acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>Vea también

[Configurar directivas para controlar el acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Habilitar o deshabilitar la detección de socios de federación](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

