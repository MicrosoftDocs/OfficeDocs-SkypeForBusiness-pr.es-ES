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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de implementar uno o más servidores perimetrales, debe habilitar a los tipos de acceso externo que se admite para su organización.
ms.openlocfilehash: 6e9721e8b5ec09aedbc76c4d0e547af0f7befbb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33923191"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Administrar la directiva de acceso de la organización

Después de implementar uno o más servidores perimetrales, debe habilitar a los tipos de acceso externo que se admite para su organización.

De forma predeterminada, no hay ningún las directivas configuradas para permitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad con el acceso de usuarios externos para su organización. Para controlar el uso de acceso de usuarios externos, debe configurar una o varias directivas, que especifica el tipo de acceso de usuarios externos admitido para cada directiva. Los ámbitos de directiva siguientes están disponibles para la creación y configuración. De forma predeterminada, la directiva Global se crea, pero no se puede eliminar.

  - **Directiva global**   la directiva global se crea al implementar los servidores perimetrales. De forma predeterminada, no hay opciones de acceso de usuarios externos están habilitadas en la directiva global. Para permitir el acceso de usuarios externos en el nivel global, configure la directiva global para admitir uno o varios tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de la organización, pero las directivas de sitio y directivas de usuario reemplazan la directiva global. Si se elimina la directiva global, no lo quita. En su lugar, se restablece a la configuración predeterminada.

  - **Directiva de sitio**   puede crear y configurar una o más directivas de sitio para limitar la compatibilidad para el acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilita el acceso de usuarios remotos para un sitio específico. De forma predeterminada, una directiva de sitio se aplica a todos los usuarios de ese sitio, pero puede asignar una directiva de usuario a un usuario para invalidar la configuración de directiva de sitio.

  - **Directiva de usuario**   puede crear y configurar una o más directivas de usuario para limitar la compatibilidad para el acceso de usuarios remotos a usuarios específicos. La configuración en la la información global de invalidaciones de directivas de usuario y la directiva de sitio, pero sólo para los usuarios específicos a quien se asigna la directiva de usuario. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global y la directiva de sitio, es posible que especifique una directiva de usuario que deshabilita el acceso de usuarios remotos y, a continuación, asignar esa directiva de usuario a usuarios específicos. Si crea una directiva de usuario, se debe aplicar a uno o más usuarios para que surta efecto.


> [!IMPORTANT]  
> La configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. Skype para la prioridad de la directiva de Business Server es: directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva Global (menos influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.


Estas opciones incluyen los siguientes tipos de acceso externo:

  - **Habilitar las comunicaciones con los usuarios federados**   habilite esta opción si desea admitir el acceso de usuarios para dominios de socio federado. Esta opción configura la capacidad de los usuarios a comunicarse con las demás federados SIP dominios, así como los proveedores hospedados como Microsoft Office 365. 


  - **Habilitar las comunicaciones con usuarios remotos**   habilite esta opción si desea que los usuarios de la organización que están fuera del firewall, por ejemplo, los usuarios que están de viaje, que puedan conectarse a Skype para Business Server a través de Internet y los teletrabajadores.

  - **Habilitar las comunicaciones con los usuarios públicos**   habilite esta opción si desea que los usuarios internos puedan comunicarse con los contactos de proveedor de mensajería instantánea pública.
   

> [!NOTE]  
> Además de habilitar el acceso de usuarios externos de soporte, también debe configurar las directivas para controlar el uso de acceso de usuarios externos en su organización antes de cualquier tipo de acceso de usuarios externos está disponible para los usuarios. Para obtener información detallada sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, vea [Habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).



**Para ver las directivas de acceso externo mediante el uso de cmdlets de Windows PowerShell**

  - Puede ver las directivas de acceso externo mediante Skype para Shell de administración de servidor empresarial y el cmdlet **Get-CsExternalAccessPolicy** . Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 
    
    Para ver información acerca de todas las directivas de acceso externo, escriba el siguiente comando en el Shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
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
