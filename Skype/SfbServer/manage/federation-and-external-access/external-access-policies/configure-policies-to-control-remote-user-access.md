---
title: Configurar directivas para el control del acceso de usuarios remotos
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios remotos pueden colaborar con usuarios Skype Empresarial Server usuarios internos. Para controlar el acceso de usuarios remotos, puede configurar directivas en el nivel global, de sitio y de usuario.
ms.openlocfilehash: 205ff2cf39a28630677390d5ee39e4dfe4beffad8be3155dd686d50fede40865
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309379"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurar directivas para controlar el acceso remoto de usuarios en Skype Empresarial Server

Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios remotos pueden colaborar con usuarios Skype Empresarial Server usuarios internos. Para controlar el acceso de usuarios remotos, puede configurar directivas en el nivel global, de sitio y de usuario. Las directivas de sitio invalidan la directiva global y las directivas de usuario invalidan las directivas de sitio y globales. Para obtener más información sobre los tipos de directivas que puede configurar, vea [Managing federation and external access to Skype Empresarial Server](../managing-federation-and-external-access.md). Skype Empresarial Server la configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de las directivas de Skype Empresarial Server es: la directiva de usuario (mayor influencia) invalida una directiva de sitio y una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.

> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios remotos, incluso aunque no se haya habilitado el acceso de usuarios remotos en su organización. Sin embargo, las directivas que se configuran solo son efectivas cuando se habilita el acceso de usuarios remotos en su organización. Además, si especifica una directiva de usuario para controlar el acceso remoto de usuarios, la directiva solo se aplica a los usuarios que están habilitados para Skype Empresarial Server y configurados para usar la directiva. Para obtener más información sobre cómo especificar usuarios que pueden iniciar sesión en Skype Empresarial Server desde ubicaciones remotas, vea Asignar una directiva de acceso [de usuarios externos.](assign-an-external-user-access-policy.md)

Use el procedimiento siguiente para configurar cada directiva de acceso externo que desea usar para controlar el acceso de usuarios remotos.


> [!NOTE]  
> Este procedimiento describe cómo se configura una directiva solo para habilitar comunicaciones con usuarios remotos, pero cada directiva que se configura para permitir el acceso de usuarios remotos puede también configurar el acceso de usuarios federados y usuarios públicos. Para obtener más información acerca de cómo configurar directivas para admitir usuarios federados, vea [Configure policies to control federated user access in Skype Empresarial Server](configure-policies-to-control-federated-user-access.md). Para obtener más información sobre cómo configurar directivas para admitir usuarios públicos, vea Administrar proveedores [federados SIP](../sip-providers/manage-sip-federated-providers-for-your-organization.md)para su organización en Skype Empresarial Server .


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar una directiva de acceso de usuarios externos para permitir el acceso de usuarios remotos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo**, siga uno de estos procedimientos:
    
      - Para configurar la directiva global para permitir el acceso de usuarios remotos, haga clic en la directiva global, seleccione **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
      - Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.
    
      - Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. En **Nueva directiva de acceso externo**, cree un nombre único en el campo **Nombre** que indique los aspectos que cubre la directiva de usuario (por ejemplo, **EnableRemoteUsers** para una directiva de usuario que permita comunicaciones a usuarios remotos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en **Editar** y, a continuación en **Mostrar detalles**.

5.  (Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción**.

6.  Siga uno de estos procedimientos:
    
      - Para habilitar el acceso de usuarios remotos de la directiva, active la casilla **Habilitar comunicaciones con usuarios remotos**.
    
      - Para deshabilitar el acceso de usuarios remotos de la directiva, desactive la casilla **Habilitar comunicaciones con usuarios remotos**.

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios remotos, también debe permitir el acceso de usuarios remotos en su organización. Para obtener más información, [vea Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

Si se trata de una directiva de usuario, también debe aplicar la directiva a usuarios a los que quiera permitir conectarse de forma remota. Para obtener más información, vea [Asignar una directiva de acceso de usuario externo.](assign-an-external-user-access-policy.md)
