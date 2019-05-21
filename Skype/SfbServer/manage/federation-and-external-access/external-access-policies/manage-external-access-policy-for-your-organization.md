---
title: Administrar la directiva de acceso de la organización
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de implementar uno o varios servidores perimetrales, debe habilitar los tipos de acceso externo que será compatible con su organización.
ms.openlocfilehash: 014077fb331bc33933d0c673771f7765b9341570
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280120"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Administrar la directiva de acceso de la organización

Después de implementar uno o varios servidores perimetrales, debe habilitar los tipos de acceso externo que será compatible con su organización.

De forma predeterminada, no hay ninguna directiva configurada para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad de acceso de usuarios externos para su organización. Para controlar el uso del acceso de usuarios externos, debe configurar una o más directivas, especificando el tipo de acceso de usuarios externos admitido para cada Directiva. Los siguientes ámbitos de directivas están disponibles para la creación y la configuración. De forma predeterminada, se crea la directiva global, pero no se puede eliminar.

  - **Directiva global se**   crea la directiva global al implementar los servidores perimetrales. De forma predeterminada, no hay ninguna opción de acceso de usuario externo habilitada en la directiva global. Para admitir el acceso de usuarios externos en el nivel global, configure la directiva global para que admita uno o varios tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de la organización, pero las directivas del sitio y las directivas de usuario invalidan la directiva global. Si elimina la directiva global, no la quitará. En su lugar, lo restablecerá a la configuración predeterminada.

  - **Directiva de sitio**   puede crear y configurar una o varias directivas de sitio para limitar la compatibilidad con el acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico. De forma predeterminada, se aplica una directiva de sitio a todos los usuarios de ese sitio, pero puede asignar una directiva de usuario a un usuario para que anule la configuración de directiva de sitio.

  - **Directiva de usuario**   puede crear y configurar una o más directivas de usuario para limitar la compatibilidad del acceso de usuarios remotos a usuarios específicos. La configuración de la Directiva de usuario reemplaza la directiva global y la de sitio, pero solo para los usuarios específicos a los que se asigna la Directiva de usuario. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global y la Directiva de sitio, puede especificar una directiva de usuario que deshabilite el acceso de usuarios remotos y, a continuación, asignar esa Directiva de usuario a usuarios específicos. Si crea una directiva de usuario, debe aplicarla a uno o más usuarios para que tenga efecto.


> [!IMPORTANT]  
> La configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de la Directiva de servidor de Skype empresarial es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.


Estas opciones incluyen los siguientes tipos de acceso externo:

  - **Habilitar comunicaciones con usuarios**   federados: habilite esta opción si desea permitir el acceso de usuarios a dominios federados de socios federados. Esta opción configura la posibilidad de que los usuarios se comuniquen con otros dominios federados SIP, así como con proveedores hospedados como Microsoft Office 365. 


  - **Habilitar las comunicaciones con usuarios**   remotos habilite esta opción si quiere que los usuarios de su organización que estén fuera del firewall, como los teletrabajadores y los usuarios que viajan, puedan conectarse a Skype empresarial Server a través de Internet.

  - **Habilitar comunicaciones con usuarios**   públicos habilite esta opción si quiere que los usuarios internos puedan comunicarse con los contactos del proveedor de mensajería instantánea pública.
   

> [!NOTE]  
> Además de habilitar la compatibilidad de acceso de usuarios externos, también debe configurar directivas para controlar el uso del acceso de usuarios externos de su organización antes de que los usuarios tengan acceso a cualquier tipo de acceso de usuario externo. Para obtener más información sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, vea [habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).



**Para ver las directivas de acceso externas mediante cmdlets de Windows PowerShell**

  - Puede ver las directivas de acceso externas mediante el shell de administración de Skype empresarial Server y el cmdlet **Get-CsExternalAccessPolicy** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 
    
    Para ver información sobre todas las directivas de acceso externo, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
    `Get-CsExternalAccessPolicy`
    
    Este comando devolverá información similar a la siguiente:
    
    ```
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
