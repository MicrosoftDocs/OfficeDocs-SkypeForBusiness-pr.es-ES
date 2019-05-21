---
title: Configurar directivas para el control del acceso de usuarios remotos
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios remotos pueden colaborar con usuarios internos de Skype empresarial Server. Para controlar el acceso de usuarios remotos, puede configurar directivas en el nivel global, de sitio y de usuario.
ms.openlocfilehash: 96d91179e7b99910182ff360920f3d46b80aa6f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280141"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurar directivas para controlar el acceso de usuarios remotos en Skype empresarial Server

Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios remotos pueden colaborar con usuarios internos de Skype empresarial Server. Para controlar el acceso de usuarios remotos, puede configurar directivas en el nivel global, de sitio y de usuario. Las directivas de sitio invalidan la directiva global y las directivas de usuario invalidan las directivas globales y del sitio. Para obtener más información sobre los tipos de directivas que puede configurar, consulte [administrar la Federación y el acceso externo a Skype empresarial Server](../managing-federation-and-external-access.md). La configuración de directiva de Skype empresarial Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de servidor de Skype empresarial es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.

> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios remotos, incluso si no ha habilitado el acceso de usuarios remotos para su organización. Sin embargo, las directivas que configure solo estarán vigentes cuando tenga habilitado el acceso de usuarios remotos en su organización. Además, si especifica una directiva de usuario para controlar el acceso de usuarios remotos, la Directiva solo se aplica a los usuarios que están habilitados para Skype empresarial Server y que se han configurado para usar la Directiva. Para obtener detalles sobre cómo especificar usuarios que pueden iniciar sesión en Skype empresarial Server desde ubicaciones remotas, consulte [asignar una directiva de acceso a usuarios externos](assign-an-external-user-access-policy.md).

Use el procedimiento siguiente para configurar cada directiva de acceso externo que desee usar para controlar el acceso de usuarios remotos.


> [!NOTE]  
> Este procedimiento describe cómo configurar una directiva solo para habilitar las comunicaciones con usuarios remotos, pero cada directiva que se configura para admitir el acceso de usuarios remotos también puede configurar el acceso de usuarios federados y el acceso de usuarios públicos. Para obtener más información sobre cómo configurar directivas para admitir usuarios federados, consulte [configurar directivas para controlar el acceso de usuarios federados en Skype empresarial Server](configure-policies-to-control-federated-user-access.md). Para obtener más información sobre cómo configurar directivas para admitir usuarios públicos, consulte [administrar proveedores federados SIP para su organización en Skype empresarial Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar una directiva de acceso externo para admitir el acceso de usuarios remotos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo** , realice una de las siguientes acciones:
    
      - Para configurar la directiva global para que admita el acceso de usuarios remotos, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.
    
      - Para crear una nueva Directiva de sitio, haga clic en **nueva**y, a continuación, haga clic en **Directiva del sitio**. En **seleccionar un sitio**, haga clic en el sitio adecuado de la lista y, a continuación, haga clic en **Aceptar**.
    
      - Para crear una nueva Directiva de usuario, haga clic en **nueva**y, a continuación, haga clic en **Directiva de usuario**. En **nueva Directiva de acceso externo**, cree un nombre único en el campo **nombre** que indique lo que cubre la Directiva de usuario (por ejemplo, **EnableRemoteUsers** para una directiva de usuario que permita comunicaciones para usuarios remotos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  Faculta Si desea agregar o editar una descripción, especifique la información de la Directiva en **Descripción**.

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios remotos para la Directiva, active la casilla **habilitar las comunicaciones con usuarios remotos** .
    
      - Para deshabilitar el acceso de usuarios remotos para la Directiva, desactive la casilla **Habilitar comunicaciones con usuarios remotos** .

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios remotos, también debe habilitar el soporte técnico para el acceso de usuarios remotos en su organización. Para obtener más información, vea [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Si se trata de una directiva de usuario, también debe aplicar la Directiva a los usuarios que desee que puedan conectarse de forma remota. Para obtener más información, consulte [asignar una directiva de acceso de usuarios externos](assign-an-external-user-access-policy.md).
