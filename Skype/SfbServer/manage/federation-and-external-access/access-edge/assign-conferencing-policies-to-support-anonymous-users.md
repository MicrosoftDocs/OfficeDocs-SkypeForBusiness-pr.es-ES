---
title: Asignar directivas de conferencia para admitir usuarios anónimos
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede controlar quién puede invitar a usuarios anónimos mediante la configuración de una directiva de conferencia para admitir usuarios anónimos y aplicar esa directiva de conferencia a usuarios específicos.
ms.openlocfilehash: afb107f7f3d91d634e5adaef4b9d0a2fbc1ee298
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919538"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Asignar directivas de conferencia para admitir usuarios anónimos en Skype para Business Server 


De forma predeterminada, todos los usuarios no podrán invitar a usuarios anónimos a participar en una reunión. Puede controlar quién puede invitar a usuarios anónimos mediante la configuración de una directiva de conferencia para admitir usuarios anónimos y aplicar esa directiva de conferencia a usuarios específicos. Para obtener información detallada sobre cómo configurar las directivas de una conferencia para admitir usuarios anónimos, vea [crear directivas de conferencia en Skype para Business Server](../../conferencing/create-policies.md) y [Managing federación y el acceso externo a Skype para Business Server](../managing-federation-and-external-access.md).

Use el procedimiento de esta sección para aplicar una directiva de conferencia que ya haya creado a uno o más usuarios o grupos de usuarios.

> [!NOTE]  
> Además de configurar y aplicar una directiva para permitir que los usuarios invitar a usuarios anónimos, también debe habilitar la compatibilidad para los usuarios anónimos para su organización. Para obtener información detallada, vea [Configurar directivas para controlar el acceso de usuarios públicos en Skype para Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Para configurar una directiva de usuario para la participación anónima en las reuniones

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **conferencia**y, a continuación, realice una de las siguientes opciones:
    
    1.  Para crear una nueva directiva de usuario, haga clic en **nuevo**y, a continuación, haga clic en **Directiva de usuario**. Cree un nombre único en el campo **nombre** que indica lo que abarca la directiva de usuario (por ejemplo, **EnableAnonymous** para una directiva de usuario que habilita la comunicación con los usuarios anónimos).
    
    2.  Para configurar una directiva de usuario existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

4.  En el cuadro de diálogo de **Las directivas de conferencia** , active la casilla de verificación **Permitir que los participantes invitar a usuarios anónimos** .

5.  Haga clic en **Confirmar**.

6.  En la barra de navegación izquierda, haga clic en **usuarios**, busque en la cuenta de usuario que desea configurar.

7.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.

8.  En **Editar Skype para usuarios de empresa Server** en **Directiva de conferencia**, seleccione la directiva de usuario con la configuración de acceso de usuario anónimo que desee aplicar a este usuario.  

    > [!NOTE]  
    > La <STRONG> &lt;automática&gt; </STRONG> configuración aplicar la configuración predeterminada de la instalación de servidor y se aplican automáticamente por el servidor.


Para permitir que los usuarios invitar a usuarios anónimos a las conferencias, también debe habilitar la compatibilidad con usuarios anónimos en su organización. Para obtener información detallada, vea [Configurar directivas para controlar el acceso de usuarios públicos en Skype para Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

