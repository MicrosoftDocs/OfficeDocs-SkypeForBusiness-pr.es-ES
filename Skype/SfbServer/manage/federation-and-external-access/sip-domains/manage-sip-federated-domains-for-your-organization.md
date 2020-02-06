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
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Obtenga información sobre cómo administrar y configurar dominios SIP con los que se puede federar.
ms.openlocfilehash: af014c6c24d3655612846e97cfa7ff5c7b9c816b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818241"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Administrar dominios federados SIP para su organización en Skype empresarial Server


Para administrar y configurar dominios SIP con los que se puede federar, puede hacer lo siguiente:

  - Crear o editar una lista de dominios permitidos de dominios de socios federados de SIP.

  - Crear o editar una lista de dominios bloqueados de dominios federados de SIP.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configurar la compatibilidad de los dominios externos permitidos en Skype empresarial Server

Si ha configurado la compatibilidad con los socios federados, puede administrar los dominios específicos que se pueden federar con su organización. Configure uno o varios dominios externos específicos como dominios federados permitidos. Para ello, agregue cada dominio a la lista de dominios permitidos. Incluso si el descubrimiento de Partners está habilitado para su organización, haga esto si el dominio es un socio federado que puede que necesite comunicarse con más de 1.000 de sus usuarios o que necesite enviar más de 20 mensajes por segundo. Si el descubrimiento de Partners no está habilitado para su organización, solo los usuarios de dominios externos que agregue a la lista de dominios permitidos podrán participar en la mensajería instantánea y las conferencias con los usuarios de su organización. Si desea restringir el acceso de un dominio federado a un servidor específico que ejecute el servicio perimetral de acceso del socio federado, puede especificar el nombre de dominio del servidor que ejecuta el servicio perimetral de acceso para cada dominio de la lista de dominios permitidos.

> [!NOTE]  
> Este procedimiento describe cómo configurar la compatibilidad con dominios específicos, pero la implementación de soporte técnico para usuarios federados también requiere que habilite la compatibilidad con usuarios federados para su organización, y configure y aplique directivas para controlar qué usuarios pueden colaborar con usuarios federados. Para obtener más información sobre cómo habilitar la compatibilidad de los usuarios federados, consulte [habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md). Para obtener más información sobre cómo configurar directivas para controlar la Federación, consulte [configurar directivas para controlar el acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Para agregar un dominio externo a la lista de dominios permitidos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, a continuación, en **dominios federados**.
4.  En la página **dominios federados** , haga clic en **nuevo**y, a continuación, haga clic en **dominio permitido**.
5.  En **nuevos dominios federados**, haga lo siguiente:
    
      - En **nombre de dominio (o FQDN)**, escriba el nombre del dominio del socio federado.       

        > [!NOTE]  
        > Este nombre debe ser único y no puede existir como dominio permitido para este servidor que ejecuta el servicio perimetral de acceso. El nombre no puede superar los 256 caracteres de longitud.<BR><br>La búsqueda en el nombre de dominio del socio federado realiza una coincidencia de sufijo. Por ejemplo, si escribe **contoso.com**, la búsqueda también devolverá el dominio **it.contoso.com**.<BR><br>Un dominio del socio federado no puede bloquearse y permitirse al mismo tiempo. Skype empresarial Server impide que esto suceda, por lo que no es necesario sincronizar las listas.
    
      - Si desea restringir el acceso a este dominio federado a los usuarios de un servidor específico que ejecute el servicio perimetral de acceso, en el **servicio perimetral de acceso (FQDN)**, escriba el FQDN del servidor del dominio federado que ejecuta el servicio perimetral de acceso.    
      - Si desea proporcionar información adicional, en **Comentario**, escriba la información que desea compartir con otros administradores del sistema acerca de esta configuración.

6.  Haga clic en **Confirmar**.
7.  Repita los pasos 4 a 6 para cada dominio de socio federado que desee permitir.

Para habilitar el acceso de usuarios federados, también debe habilitar la compatibilidad con el acceso de usuarios federados de su organización. Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).

Además, debe configurar y aplicar la Directiva a los usuarios que desee que puedan colaborar con los usuarios federados. Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurar la compatibilidad de los dominios externos bloqueados en Skype empresarial Server 

Si ha configurado la compatibilidad con los socios federados, puede administrar los dominios que estarán bloqueados para que no se federen con su organización. La lista de dominios bloqueados actuará como una lista de bloqueados (lista de entradas explícitas no permitidas) y se aplicará en la detección de dominios federados, si tiene esta opción habilitada. Para obtener más información, vea [habilitar o deshabilitar el descubrimiento de socios de Federación](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Bloquear la conexión de uno o varios dominios externos a su organización. Para ello, agregue el dominio a la lista de dominios bloqueados.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Para agregar un dominio externo a la lista de dominios bloqueados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**.
4.  Haga clic en **dominios federados**, en **nuevo**y, a continuación, en **dominio bloqueado**.
5.  En **nuevos dominios federados**, haga lo siguiente:
    
      - En **nombre de dominio (o FQDN)**, escriba el nombre del dominio del socio federado que desea bloquear.

        > [!NOTE]  
        > El nombre no puede superar los 256 caracteres de longitud.<BR><br>La búsqueda en el nombre de dominio del socio federado realiza una coincidencia de sufijo. Por ejemplo, si escribe **contoso.com**, la búsqueda también devolverá el dominio **it.contoso.com**.<BR><br>Un dominio del socio federado no puede bloquearse y permitirse al mismo tiempo. Skype empresarial Server impide que esto suceda, por lo que no es necesario sincronizar las listas.
   
      - Faculta En **Comentario**, escriba la información que desea compartir con otros administradores del sistema acerca de esta configuración.

6.  Haga clic en **Confirmar**.
7.  Repita los pasos 4 a 6 para cada socio federado que desee bloquear.

Para habilitar el acceso de usuarios federados, también debe habilitar la compatibilidad con el acceso de usuarios federados de su organización. Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).

Además, debe configurar y aplicar la Directiva a los usuarios que desee que puedan colaborar con los usuarios federados. Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>Vea también

[Configurar directivas para controlar el acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Habilitar o deshabilitar la detección de socios de federación](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

