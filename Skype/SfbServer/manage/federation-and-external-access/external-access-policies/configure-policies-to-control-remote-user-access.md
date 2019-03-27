---
title: Configurar directivas para el control del acceso de usuarios remotos
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Configurar uno o más directivas de acceso de usuarios externos para controlar si los usuarios remotos pueden colaborar con Skype interna para los usuarios de Business Server. Para controlar el acceso de usuarios remotos, puede configurar las directivas a nivel global, sitio y el nivel de usuario.
ms.openlocfilehash: f6d316f022e671bc7f7e70ebbe2a801b0b3e312c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899536"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurar directivas para controlar el acceso de usuarios remotos en Skype para Business Server

Configurar uno o más directivas de acceso de usuarios externos para controlar si los usuarios remotos pueden colaborar con Skype interna para los usuarios de Business Server. Para controlar el acceso de usuarios remotos, puede configurar las directivas a nivel global, sitio y el nivel de usuario. Las directivas de sitio invalidar la directiva global, y las directivas de usuario reemplazan las directivas globales y sitio. Para obtener información detallada sobre los tipos de directivas que se pueden configurar, consulte [Managing federación y el acceso externo a Skype para Business Server](../managing-federation-and-external-access.md). Skype para la configuración de directiva de Business Server que se aplican en un nivel de directiva puede invalidar la configuración que se aplica en el nivel de directiva de otra. Skype para la prioridad de la directiva de Business Server es: directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva Global (menos influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.

> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios remotos, incluso si no ha habilitado el acceso de usuarios remotos para su organización. Sin embargo, las directivas que configurar entren en vigor sólo cuando tenga acceso de usuarios remotos habilitado para su organización. Además, si se especifica una directiva de usuario para controlar el acceso de usuarios remotos, la directiva se aplica sólo a los usuarios que están habilitados para Skype para Business Server y configurados para utilizar la directiva. Para obtener información detallada acerca de cómo especificar los usuarios que pueden iniciar sesión en Skype para Business Server desde ubicaciones remotas, vea [asignar una directiva de acceso de usuarios externos](assign-an-external-user-access-policy.md).

Use el procedimiento siguiente para configurar cada directiva de acceso externo que desea usar para controlar el acceso de usuarios remotos.


> [!NOTE]  
> Este procedimiento describe cómo configurar una directiva sólo para habilitar las comunicaciones con usuarios remotos, pero también puede configurar cada directiva que se configura para admitir el acceso de usuarios remotos el acceso de usuarios federados y acceso de usuarios públicos. Para obtener información detallada acerca de cómo configurar directivas para admitir usuarios federados, vea [federados de configurar directivas para controlar el acceso de usuarios de Skype para Business Server](configure-policies-to-control-federated-user-access.md). Para obtener información detallada acerca de cómo configurar directivas para admitir usuarios públicos, vea [Administrar SIP proveedores para su organización en Skype para Business Server federados](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar una directiva de acceso externo para admitir el acceso de usuarios remotos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**y, a continuación, haga clic en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo** , realice una de las siguientes:
    
      - Para configurar la directiva global para permitir el acceso de usuarios remotos, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.
    
      - Para crear una nueva directiva de sitio, haga clic en **nuevo**y, a continuación, haga clic en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, haga clic en **Aceptar**.
    
      - Para crear una nueva directiva de usuario, haga clic en **nuevo**y, a continuación, haga clic en **Directiva de usuario**. En la **Nueva directiva de acceso externo**, cree un nombre único en el campo **nombre** que indica qué usuario cubiertos por la directiva (por ejemplo, **EnableRemoteUsers** para una directiva de usuario que permite a comunicaciones para los usuarios remotos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  (Opcional) Si desea agregar o editar una descripción, especifique la información de la directiva en **Descripción**.

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios remotos para la directiva, active la casilla de verificación **Habilitar las comunicaciones con usuarios remotos** .
    
      - Para deshabilitar el acceso de usuarios remotos para la directiva, desactive la casilla de verificación **Habilitar las comunicaciones con usuarios remotos** .

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios remotos, también debe habilitar la compatibilidad con acceso de usuarios remotos en la organización. Para obtener información detallada, vea [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Si se trata de una directiva de usuario, también debe aplicar la directiva a los usuarios que desea que puedan conectarse de forma remota. Para obtener información detallada, vea [asignar una directiva de acceso de usuarios externos](assign-an-external-user-access-policy.md).
