---
title: Configurar directivas para controlar el acceso de usuarios públicos
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: La conectividad de mensajería instantánea (MI) permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de servicios de mensajería instantánea pública.
ms.openlocfilehash: 28bb1c94cb42068fe99f07a6608a3ac1c50991ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823596"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurar directivas para controlar el acceso de usuarios públicos en Skype Empresarial Server

La conectividad de mensajería instantánea (MI) pública permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de servicios de mensajería instantánea pública. Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios públicos pueden colaborar con usuarios internos de Skype Empresarial Server. La conectividad de mensajería instantánea pública es una característica adicional que se basa en la configuración de la implementación y los usuarios. También depende del aprovisionamiento del servicio en el proveedor de mensajería instantánea pública. 

Puede configurar directivas de nivel global, de sitio y de usuario para controlar el acceso de usuarios públicos. La configuración de directiva de Skype Empresarial Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de las directivas de Skype Empresarial Server es: la directiva de usuario (mayor influencia) invalida una directiva de sitio y una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.

En el caso de las invitaciones de mensajería instantánea, la respuesta depende del software cliente. Se acepta la solicitud a menos que los remitentes externos queden explícitamente bloqueados por una regla configurada por el usuario (es decir, la configuración de las listas **Permitir** y **Bloquear** del cliente del usuario). Además, las invitaciones de mensajería instantánea se pueden bloquear si un usuario opta por bloquear todos los mensajes instantáneos de los usuarios que no estén en su lista **Permitir**.



> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios públicos, incluso aunque no haya habilitado una federación para la organización. Sin embargo, las directivas que configure únicamente surtirán efecto cuando haya habilitado la federación en la organización. Para obtener más información sobre cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos.](../access-edge/enable-or-disable-remote-user-access.md) Además, si especifica una directiva de usuario para controlar el acceso de usuarios públicos, la directiva solo se aplica a los usuarios habilitados para Skype Empresarial Server y configurados para usar la directiva. Para obtener más información sobre cómo especificar usuarios públicos que pueden iniciar sesión en Skype Empresarial Server, consulte [Asignar una directiva de acceso de usuarios externos.](assign-an-external-user-access-policy.md)


Use el procedimiento que se describe a continuación para configurar una directiva que admita el acceso de usuarios de uno o varios proveedores de mensajería instantánea pública.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Para configurar una directiva de acceso externo para permitir el acceso de usuarios públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.

4.  En la página  **Directiva de acceso externo**, siga uno de estos procedimientos:
    
      - Para configurar la directiva global para permitir el acceso de usuarios públicos, haga clic en la directiva global, en  **Editar** y en  **Mostrar detalles**.
    
      - Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.
    
      - Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. En **Nueva directiva de acceso externo**, cree un nombre único en el campo **Nombre** que indique lo que cubre la directiva de usuario (por ejemplo, **EnablePublicUsers** para una directiva de usuario que permita comunicaciones para usuarios públicos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en  **Editar** y, a continuación en  **Mostrar detalles**.

5.  (Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción**.

6.  Siga uno de estos procedimientos:
    
      - Para habilitar el acceso de usuarios públicos para la directiva, active la casilla  **Habilitar comunicaciones con usuarios públicos**.
    
      - Para deshabilitar el acceso de usuarios públicos para la directiva, desactive la casilla  **Habilitar comunicaciones con usuarios públicos**.

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios públicos, también debe permitir la federación en su organización. Para obtener más información, [consulte Configurar directivas para controlar el acceso de usuarios federados en Skype Empresarial Server.](configure-policies-to-control-federated-user-access.md)

Si se trata de una directiva de usuario, también tiene que aplicar la directiva a los usuarios públicos que desee que puedan colaborar con usuarios públicos. 


## <a name="see-also"></a>Consulte también

[Administrar proveedores federados SIP para la organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
