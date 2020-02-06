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
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Usted controla quién puede invitar a usuarios anónimos mediante la configuración de una directiva de conferencia para admitir usuarios anónimos y la aplicación de esa Directiva de conferencia a usuarios específicos.
ms.openlocfilehash: b5427ec96d3593cf87656f562acf0afc183b92d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818421"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Asignar directivas de conferencia para admitir usuarios anónimos en Skype empresarial Server 


De forma predeterminada, todos los usuarios no pueden invitar a usuarios anónimos a participar en una reunión. Usted controla quién puede invitar a usuarios anónimos mediante la configuración de una directiva de conferencia para admitir usuarios anónimos y la aplicación de esa Directiva de conferencia a usuarios específicos. Para obtener más información sobre cómo configurar las directivas de conferencia para admitir usuarios anónimos, consulte [crear directivas de conferencia en Skype empresarial Server](../../conferencing/create-policies.md) y [administrar la Federación y el acceso externo a Skype empresarial Server](../managing-federation-and-external-access.md).

Use el procedimiento de esta sección para aplicar una directiva de conferencia que ya haya creado a uno o más usuarios o grupos de usuarios.

> [!NOTE]  
> Además de configurar y aplicar una directiva para que los usuarios puedan invitar a usuarios anónimos, también debe habilitar la compatibilidad con usuarios anónimos para su organización. Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios públicos en Skype empresarial Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Para configurar una directiva de usuario para la participación anónima en reuniones

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Conferencia**y, a continuación, siga uno de estos procedimientos:
    
    1.  Para crear una nueva Directiva de usuario, haga clic en **nueva**y, a continuación, haga clic en **Directiva de usuario**. Cree un nombre único en el campo **nombre** que indique lo que cubre la Directiva de usuario (por ejemplo, **EnableAnonymous** para una directiva de usuario que permita la comunicación con usuarios anónimos).
    
    2.  Para configurar una directiva de usuario existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

4.  En el cuadro de diálogo **directivas de conferencia** , active la casilla **permitir que los participantes inviten a usuarios anónimos** .

5.  Haga clic en **Confirmar**.

6.  En la barra de navegación izquierda, haga clic en **usuarios**, busque la cuenta de usuario que desea configurar.

7.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.

8.  En **Editar usuario de Skype empresarial Server** en **Directiva de conferencia**, seleccione la Directiva de usuario con la configuración de acceso de usuarios anónimos que desea aplicar a este usuario.  

    > [!NOTE]  
    > La <STRONG> &lt;configuración&gt; automática</STRONG> aplica la configuración predeterminada de la instalación del servidor y el servidor la aplica automáticamente.


Para permitir que los usuarios inviten a usuarios anónimos a conferencias, también debe habilitar la compatibilidad con usuarios anónimos de su organización. Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios públicos en Skype empresarial Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

