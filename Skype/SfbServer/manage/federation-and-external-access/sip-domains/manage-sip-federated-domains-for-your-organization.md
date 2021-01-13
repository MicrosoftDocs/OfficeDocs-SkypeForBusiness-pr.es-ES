---
title: Administrar dominios federados SIP para la organización
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: Obtenga información sobre cómo administrar y configurar dominios SIP con los que puede federar,
ms.openlocfilehash: 7b04225542387d52a36533c9639b02f773731e9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817220"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Administrar dominios federados SIP para su organización en Skype Empresarial Server


Para administrar y configurar los dominios SIP con los que se puede federar, puede hacer lo siguiente:

  - Cree o modifique una lista de dominios permitidos que incluya dominios de socios federados SIP.

  - Cree o modifique una lista de dominios bloqueados que incluya dominios de socios federados SIP.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configurar la compatibilidad con dominios externos permitidos en Skype Empresarial Server

Si ha configurado la compatibilidad para socios federados, puede administrar qué dominios específicos pueden federar con su organización. Se configuran uno o más dominios externos específicos como dominios federados permitidos. Para hacerlo, agregue cada uno de los dominios a la lista de dominios admitidos. Incluso en el caso de que la detección de socios esté habilitada en la organización, haga lo anterior si el dominio es un socio federado que podría necesitar comunicarse con más de 1.000 usuarios o enviar más de 20 mensajes por segundo. Si la detección de socios no está habilitada en la organización, solo los usuarios de dominios externos que agregue a la lista de dominios permitidos podrán participar en reuniones y compartir mensajería instantánea con usuarios de su organización. Si desea restringir el acceso de un dominio federado a un servidor específico que ejecuta el servicio perimetral de acceso del socio federado, puede especificar el nombre de dominio del servidor que ejecuta el servicio perimetral de acceso para cada dominio de la lista de dominios permitidos.

> [!NOTE]  
> Este procedimiento describe cómo configurar la compatibilidad para dominios específicos, pero para permitir usuarios federados es necesario habilitar también dicha compatibilidad en la organización y, además, configurar y aplicar directivas para determinar qué usuarios pueden colaborar con usuarios federados. Para obtener más información sobre cómo habilitar la compatibilidad con usuarios federados, vea [Habilitar o deshabilitar el acceso de usuarios remotos.](../access-edge/enable-or-disable-remote-user-access.md) Para obtener más información acerca de cómo configurar directivas para controlar la federación, vea [Configurar directivas para controlar el acceso de usuarios federados.](../external-access-policies/configure-policies-to-control-federated-user-access.md)

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Para agregar un dominio externo a la lista de dominios permitidos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
3.  En el barra de navegación izquierda, haga clic en **Acceso de usuarios externos** y, a continuación, en **Dominios federados**.
4.  En la página **Dominios federados**, haga clic en **Nuevo** y, a continuación, seleccione **Dominio permitido**.
5.  En **Nuevos dominios federados**, haga lo siguiente:
    
      - En **Nombre de dominio (o FQDN)**, escriba el nombre de dominio de socio federado.       

        > [!NOTE]  
        > El nombre debe ser único y no puede haber otro dominio permitido con el mismo nombre en el servidor que ejecuta el servicio perimetral de acceso. El nombre no puede superar los 256 caracteres.<BR><br>La búsqueda del dominio de socio federado busca la coincidencia de sufijos. Por ejemplo, si escribe **contoso.com**, la búsqueda devolverá el dominio **it.contoso.com**.<BR><br>Un dominio de socio federado no puede bloquearse y permitirse simultáneamente. Skype Empresarial Server impide que esto suceda para que no tenga que sincronizar las listas.
    
      - Si desea restringir el acceso de este dominio federado a usuarios de un servidor específico que ejecuta el servicio perimetral de acceso, en **Servicio perimetral de acceso(FQDN)**, escriba el FQDN del servidor del dominio federado que ejecuta el servicio perimetral de acceso.    
      - Si desea proporcionar información adicional, en **Comentario**, escriba la información que desee compartir con otros administradores del sistema sobre esta configuración.

6.  Haga clic en **Confirmar**.
7.  Repita los pasos del 4 al 6 para cada dominio de socio federado que desee permitir.

Para habilitar el acceso de usuarios federados, también debe permitir el acceso de usuarios federados en su organización. Para obtener más información, vea [Habilitar o deshabilitar el acceso de usuarios remotos.](../access-edge/enable-or-disable-remote-user-access.md)

Además, debe configurar y aplicar la directiva a los usuarios que quiera permitir que colaboren con usuarios federados. Para obtener más información, [vea Configurar directivas para controlar el acceso de usuarios federados.](../external-access-policies/configure-policies-to-control-federated-user-access.md)

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurar la compatibilidad con dominios externos bloqueados en Skype Empresarial Server 

Si ha configurado la compatibilidad para socios federados, puede administrar los dominios que se bloquearán de la federación con su organización. La lista de dominios bloqueados actuará como una lista de bloqueo (lista de entradas explícitas que no se van a permitir) y se aplicará en la detección de dominios federados, si tiene activada esta opción. Para obtener más información, vea [Habilitar o deshabilitar la detección de socios de federación.](../access-edge/enable-or-disable-discovery-of-federation-partners.md)

Bloquee uno o más dominios externos para que no puedan conectarse a su organización. Para hacerlo, agregue el dominio a la lista de dominios bloqueados.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Para agregar un dominio externo a la lista de dominios bloqueados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**.
4.  Seleccione **Dominios federados**, haga clic en **Nuevo** y, a continuación, seleccione **Dominio bloqueado**.
5.  En **Nuevos dominios federados**, haga lo siguiente:
    
      - En **Nombre de dominio (o FQDN)**, escriba el nombre de dominio de socio federado que desea bloquear.

        > [!NOTE]  
        > El nombre no puede superar los 256 caracteres.<BR><br>La búsqueda del dominio de socio federado busca la coincidencia de sufijos. Por ejemplo, si escribe **contoso.com**, la búsqueda devolverá el dominio **it.contoso.com**.<BR><br>Un dominio de socio federado no puede bloquearse y permitirse simultáneamente. Skype Empresarial Server impide que esto suceda para que no tenga que sincronizar las listas.
   
      - (Opcional) En **Comentario**, escriba la información que desea compartir con otros administradores del sistema sobre esta configuración.

6.  Haga clic en **Confirmar**.
7.  Repita los pasos del 4 al 6 para cada socio federado que desee bloquear.

Para habilitar el acceso de usuarios federados, también debe permitir el acceso de usuarios federados en su organización. Para obtener más información, vea [Habilitar o deshabilitar el acceso de usuarios remotos.](../access-edge/enable-or-disable-remote-user-access.md)

Además, debe configurar y aplicar la directiva a los usuarios que quiera permitir que colaboren con usuarios federados. Para obtener más información, [vea Configurar directivas para controlar el acceso de usuarios federados.](../external-access-policies/configure-policies-to-control-federated-user-access.md)


## <a name="see-also"></a>Consulte también

[Configurar directivas para controlar el acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Habilitar o deshabilitar la detección de socios de federación](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

