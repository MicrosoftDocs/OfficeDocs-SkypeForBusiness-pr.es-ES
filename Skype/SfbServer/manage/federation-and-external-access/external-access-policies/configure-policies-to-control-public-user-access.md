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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: público (IM) conectividad de mensajería instantánea permite a los usuarios de su organización utilizar la mensajería instantánea para comunicarse con los usuarios de servicios de mensajería instantánea proporcionados por los proveedores de servicios de mensajería instantánea pública.
ms.openlocfilehash: 6cccef5de36b733e1af13092137bf0a35e843b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920442"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurar directivas para controlar el acceso de usuarios públicos en Skype para Business Server

Conectividad de mensajería instantánea pública permite a los usuarios de su organización utilizar la mensajería instantánea para comunicarse con los usuarios de servicios de mensajería instantánea proporcionados por los proveedores de servicios de mensajería instantánea pública. Configurar uno o más directivas de acceso de usuarios externos para controlar si los usuarios públicos pueden colaborar con Skype interna para los usuarios de Business Server. Conectividad de mensajería instantánea pública es una función de agregado que se basa en la configuración de su implementación y los usuarios. También depende el aprovisionamiento del servicio en el proveedor de mensajería instantánea pública. 

Para controlar el acceso de usuarios públicos, puede configurar las directivas a nivel global, sitio y el nivel de usuario. Skype para la configuración de directiva de Business Server que se aplican en un nivel de directiva puede invalidar la configuración que se aplica en el nivel de directiva de otra. Skype para la prioridad de la directiva de Business Server es: directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva Global (menos influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.

En el caso de las invitaciones de mensajería instantánea, la respuesta depende del software cliente. Se acepta la solicitud a menos que los remitentes externos queden explícitamente bloqueados por una regla configurada por el usuario (es decir, la configuración en el cliente del usuario **Permitir** y las listas de **bloqueados** ). Además, las invitaciones de mensajería instantánea se pueden bloquear si un usuario decide bloquear todos los mensajes Instantáneos de los usuarios que no están en su lista **Permitir** .



> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios públicos, incluso si no ha habilitado la federación para su organización. Sin embargo, las directivas que configurar entren en vigor sólo cuando tenga federación habilitada para su organización. Para obtener información detallada acerca de cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md). Además, si se especifica una directiva de usuario para controlar el acceso de usuarios públicos, la directiva se aplica sólo a los usuarios que están habilitados para Skype para Business Server y configurados para utilizar la directiva. Para obtener información detallada acerca de cómo especificar los usuarios públicos que pueden iniciar sesión en Skype para Business Server, vea [asignar una directiva de acceso de usuarios externos](assign-an-external-user-access-policy.md).


Use el siguiente procedimiento para configurar una directiva para admitir el acceso a los usuarios de uno o varios proveedores de mensajería instantánea pública.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Para configurar una directiva de acceso externo para admitir el acceso de usuarios públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**y, a continuación, haga clic en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo** , realice una de las siguientes:
    
      - Para configurar la directiva global para permitir el acceso de usuarios públicos, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.
    
      - Para crear una nueva directiva de sitio, haga clic en **nuevo**y, a continuación, haga clic en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, haga clic en **Aceptar**.
    
      - Para crear una nueva directiva de usuario, haga clic en **nuevo**y, a continuación, haga clic en **Directiva de usuario**. En la **Nueva directiva de acceso externo**, cree un nombre único en el campo **nombre** que indica qué usuario cubiertos por la directiva (por ejemplo, **EnablePublicUsers** para una directiva de usuario que se habilita la comunicación de los usuarios públicos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  (Opcional) Si desea agregar o editar una descripción, especifique la información de la directiva en **Descripción**.

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios públicos para la directiva, active la casilla de verificación **Habilitar las comunicaciones con los usuarios públicos** .
    
      - Para deshabilitar el acceso de usuarios públicos para la directiva, desactive la casilla de verificación **Habilitar las comunicaciones con los usuarios públicos** .

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios públicos, también debe habilitar la compatibilidad para la federación en la organización. Para obtener información detallada, vea [federados de configurar directivas para controlar el acceso de usuarios de Skype para Business Server](configure-policies-to-control-federated-user-access.md).

Si se trata de una directiva de usuario, también debe aplicar la directiva a los usuarios públicos que desea que puedan colaborar con los usuarios públicos. 


## <a name="see-also"></a>Vea también

[Administrar proveedores federados SIP para la organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
