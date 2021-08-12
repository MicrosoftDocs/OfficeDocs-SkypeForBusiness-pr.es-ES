---
title: Administración de la directiva de acceso externo a la organización
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
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
description: Después de implementar uno o varios servidores Edge, debe habilitar los tipos de acceso externo que se permitirán en la organización.
ms.openlocfilehash: 0de747552ff19852d7947178e0882aec227c9e2d75f9210597f8183b6703f101
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284760"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Administración de la directiva de acceso externo a la organización

Después de implementar uno o varios servidores Edge, debe habilitar los tipos de acceso externo que se permitirán en la organización.

De forma predeterminada, no hay ninguna directiva configurada para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, el acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad con el acceso de usuarios externos para su organización. Para controlar el uso del acceso de usuarios externos, debe configurar una o más directivas, especificando el tipo de acceso de usuarios externos que es compatible con cada directiva. Para la creación y configuración están disponibles los siguientes ámbitos de directivas. De forma predeterminada, se crea la directiva global, pero no se puede eliminar.

  - **Directiva global**   La directiva global se crea al implementar los servidores perimetrales. De forma predeterminada, no hay opciones de acceso de usuarios externos habilitadas en la directiva global. Para admitir el acceso de usuarios externos a nivel global, configure la directiva global para admitir uno o más tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de la organización, pero las directivas de sitio y las directivas de usuario reemplazan a la directiva global. Si elimina la directiva global, no se quita. En su lugar, se restablece la configuración predeterminada.

  - **Directiva de sitio**   Puede crear y configurar una o más directivas de sitio para limitar el acceso de usuarios externos a determinados sitios. La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva. Por ejemplo, si activa el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico. De forma predeterminada, una directiva de sitio se aplica a todos los usuarios de dicho sitio, aunque puede asignar una directiva de usuario a un usuario determinado para invalidar dicho parámetro de la directiva de sitio.

  - **Directiva de sitio**   Puede crear y configurar una o más directivas de usuario para limitar el acceso de usuarios remotos a determinados usuarios. La configuración de la directiva de usuario invalida la directiva global y la directiva de sitio, pero solo para los usuarios concretos a los que se ha asignado la directiva de usuario. Por ejemplo, si deshabilita el acceso de usuarios remotos en la directiva global y a la directiva de sitio, puede especificar una directiva de usuario para deshabilitar el acceso de usuarios remotos y, a continuación, asignar dicha directiva de usuario a usuarios específicos. Si crea una directiva de sitio, debe aplicarla a uno o más usuarios antes de que se haga efectiva.


> [!IMPORTANT]  
> Las opciones de configuración de directiva que se aplican en un nivel de directiva pueden sobrescribir la configuración que se aplica en otro nivel de directiva. La prioridad de las directivas de Skype Empresarial Server es: la directiva de usuario (mayor influencia) invalida una directiva de sitio y una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.


Entre estas opciones se incluyen los siguientes tipos de acceso externo:

  - **Habilitar comunicaciones con usuarios federados**   Habilite esta opción si desea admitir el acceso de usuarios a dominios de socios federados. Esta configuración configura la capacidad para que los usuarios se comuniquen con otros dominios federados SIP, así como con proveedores hospedados como Microsoft 365 o Office 365. 


  - **Habilitar comunicaciones con usuarios remotos**   Habilite esta opción si desea que los usuarios de la organización que están fuera del firewall, como los teletrabadores y los usuarios que están de viaje, puedan conectarse a Skype Empresarial Server a través de Internet.

  - **Habilitar comunicaciones con usuarios públicos**   Habilite esta opción si desea que los usuarios internos puedan comunicarse con contactos públicos del proveedor de mensajería instantánea.
   

> [!NOTE]  
> Además de habilitar la compatibilidad de acceso de usuarios externos, también debe configurar directivas para controlar el uso del acceso de usuarios externos en su organización antes de que los usuarios obtengan cualquier tipo de acceso para usuarios externos. Para detalles sobre cómo crear, configurar y aplicar directivas para acceso de usuarios externos, vea [Habilitar y deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).



**Para ver directivas de acceso externo con cmdlets de Windows PowerShell**

  - Las directivas de acceso externas se pueden ver con el shell de administración de Skype Empresarial Server y el cmdlet **Get-CsExternalAccessPolicy**. Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 
    
    Para ver información sobre todas las directivas de acceso externo escriba el comando siguiente en el shell de administración de Lync Server y presione ENTRAR:
    
    `Get-CsExternalAccessPolicy`
    
    Este comando devolverá información similar a la siguiente:
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
