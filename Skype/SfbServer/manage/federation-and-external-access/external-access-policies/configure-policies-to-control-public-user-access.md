---
title: Configurar directivas para controlar el acceso de usuarios públicos
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ublic conectividad de mensajería instantánea (mi) permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de servicios de mensajería instantánea pública.
ms.openlocfilehash: 230c3405a9d0a551758bee63fae8f927fdc5af19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280162"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurar directivas para controlar el acceso de usuarios públicos en Skype empresarial Server

La conectividad de mensajería instantánea pública (mi) permite a los usuarios de la organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de servicios de mensajería instantánea pública. Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios públicos pueden colaborar con usuarios internos de Skype empresarial Server. La conectividad de mensajería instantánea pública es una característica agregada que se basa en la configuración de la implementación y los usuarios. También depende del suministro del servicio en el proveedor de mensajería instantánea pública. 

Para controlar el acceso de los usuarios públicos, puede configurar directivas en el nivel global, de sitio y de usuario. La configuración de directiva de Skype empresarial Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de servidor de Skype empresarial es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.

En el caso de las invitaciones de mensajería instantánea, la respuesta depende del software de cliente. La solicitud se acepta a menos que los remitentes externos se bloquean explícitamente mediante una regla configurada por el usuario (es decir, la configuración de las listas **permitir** o **bloquear** del cliente del usuario). Además, las invitaciones de mensajería instantánea se pueden bloquear si un usuario decide bloquear todos los mensajes instantáneos de usuarios que no estén **** en su lista de permitidos.



> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios públicos, incluso si no ha habilitado la Federación de su organización. Sin embargo, las directivas que configure solo estarán vigentes cuando tenga habilitada la Federación de su organización. Para obtener más información sobre cómo habilitar la Federación, consulte [habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md). Además, si especifica una directiva de usuario para controlar el acceso de los usuarios públicos, la Directiva solo se aplica a los usuarios que están habilitados para Skype empresarial Server y que se han configurado para usar la Directiva. Para obtener detalles sobre cómo especificar usuarios públicos que pueden iniciar sesión en Skype empresarial Server, consulte [asignar una directiva de acceso de usuarios externos](assign-an-external-user-access-policy.md).


Use el procedimiento siguiente para configurar una directiva que admita el acceso de usuarios de uno o más proveedores de mensajería instantánea pública.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Para configurar una directiva de acceso externo para admitir el acceso de usuarios públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo** , realice una de las siguientes acciones:
    
      - Para configurar la directiva global para admitir el acceso de usuarios públicos, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.
    
      - Para crear una nueva Directiva de sitio, haga clic en **nueva**y, a continuación, haga clic en **Directiva del sitio**. En **seleccionar un sitio**, haga clic en el sitio adecuado de la lista y, a continuación, haga clic en **Aceptar**.
    
      - Para crear una nueva Directiva de usuario, haga clic en **nueva**y, a continuación, haga clic en **Directiva de usuario**. En **nueva Directiva de acceso externo**, cree un nombre único en el campo **nombre** que indique lo que cubre la Directiva de usuario (por ejemplo, **EnablePublicUsers** para una directiva de usuario que permita la comunicación para usuarios públicos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  Faculta Si desea agregar o editar una descripción, especifique la información de la Directiva en **Descripción**.

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios públicos para la Directiva, active la casilla **Habilitar comunicaciones con usuarios públicos** .
    
      - Para deshabilitar el acceso de usuarios públicos para la Directiva, desactive la casilla **Habilitar comunicaciones con usuarios públicos** .

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios públicos, también debe habilitar la compatibilidad con la Federación de su organización. Para obtener más información, consulte [configurar directivas para controlar el acceso de usuarios federados en Skype empresarial Server](configure-policies-to-control-federated-user-access.md).

Si se trata de una directiva de usuario, también debe aplicar la Directiva a los usuarios públicos que desee que puedan colaborar con los usuarios públicos. 


## <a name="see-also"></a>Vea también

[Administrar proveedores federados SIP para la organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
