---
title: Asignar directivas de conferencia para admitir usuarios anónimos
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Para controlar quién puede invitar a usuarios anónimos, se debe configurar una directiva de conferencias que admita la participación de usuarios anónimos, y aplicar dicha directiva a usuarios específicos.
ms.openlocfilehash: d37c67548f8b1b5c97f5ae13ac7bd2fb8e14dfc9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616566"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Asignar directivas de conferencia para admitir usuarios anónimos en Skype Empresarial Server 


De forma predeterminada, ningún usuario tiene permitido invitar a usuarios anónimos a participar en una reunión. Para controlar quién puede invitar a usuarios anónimos, se debe configurar una directiva de conferencias que admita la participación de usuarios anónimos, y aplicar dicha directiva a usuarios específicos. Para obtener más información sobre cómo configurar directivas de conferencia para admitir usuarios anónimos, vea Create [conferencing policies in Skype Empresarial Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype Empresarial Server](../managing-federation-and-external-access.md).

Use el procedimiento de esta sección para aplicar una directiva de conferencia que ya haya creado a uno o varios usuarios o grupos de usuarios.

> [!NOTE]  
> Además de configurar y aplicar una directiva para permitir a los usuarios invitar a usuarios anónimos, también debe habilitar la compatibilidad con usuarios anónimos para su organización. Para obtener más información, vea [Configure policies to control public user access in Skype Empresarial Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Para configurar una directiva de usuario para la participación anónima en reuniones

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, siga uno de estos procedimientos:
    
    1.  Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. Cree un nombre único en el **campo Nombre** que indique lo que cubre la directiva de usuario (por ejemplo, **EnableAnonymous** para una directiva de usuario que permita las comunicaciones con usuarios anónimos).
    
    2.  Para configurar una directiva de usuario existente, haga clic en la directiva adecuada que aparece en la tabla, haga clic en **Editar** y, a continuación, haga clic **en Mostrar detalles.**

4.  En el **cuadro de diálogo Directivas de** conferencia, active la casilla Permitir que los **participantes inviten a** usuarios anónimos.

5.  Haga clic en **Confirmar**.

6.  En la barra de navegación izquierda, haga clic **en Usuarios**, busque en la cuenta de usuario que desea configurar.

7.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar** y, a continuación, en  **Mostrar detalles**.

8.  En **Editar Skype Empresarial Server usuario** en directiva de conferencia, seleccione la directiva de usuario con la configuración de acceso de usuario anónimo que desea aplicar a este usuario.   

    > [!NOTE]  
    > La <STRONG> &lt; configuración &gt; </STRONG> automática aplica la configuración de instalación predeterminada del servidor y la aplica automáticamente el servidor.


Para permitir a los usuarios invitar a usuarios anónimos a conferencias, también tiene que habilitar la compatibilidad con usuarios anónimos en la organización. Para obtener más información, vea [Configure policies to control public user access in Skype Empresarial Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

