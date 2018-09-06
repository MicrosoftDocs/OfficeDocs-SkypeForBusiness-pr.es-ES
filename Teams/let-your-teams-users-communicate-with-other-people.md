---
title: Comunicarse con los usuarios de los equipos de otra organización.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Strat_MT_TeamsAdmin
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Vea cómo configurar los equipos para permitir a los usuarios comunicarse con usuarios de otra organización.
ms.openlocfilehash: 3eaffac3571abc70d4964ea4a8955f187d1e988f
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "23844640"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir que el chat de los usuarios de los equipos y comunicarse con los usuarios de otra organización de los equipos

Siga los pasos de este artículo cuando:
  
- Tienen los usuarios en diferentes dominios en su negocio. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.
    
- Las personas que desee en la organización para usar los equipos ponerse en contacto con las personas de empresas específicas fuera de la organización.
    
- Cualquier persona que desee en el mundo que usa los equipos que puedan buscar y ponerse en contacto con usted, utilizando su dirección de correo electrónico. Si usted y otro usuario tanto habilitación el acceso externo y permitir que los demás dominios, esto funcionará. Si no funciona, el otro usuario, debe asegurarse de que su o su configuración no esté bloqueando su dominio.

Siga estos pasos:

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir que el chat de los usuarios de los equipos y comunicarse con los usuarios de otra organización de los equipos

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Paso 1: asegúrese de configurar los puertos y direcciones URL que son necesarios.

**El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Paso 2: habilitar la organización para comunicarse con otra organización de los equipos

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

   1. En el panel de navegación izquierdo, vaya a **configuración de toda la organización** > **acceso externo**. 

   2. En la parte superior de la página de **acceso externo** , haga clic en **acceso externo** a **en**. 

   3. Agregar dominio de la otra organización a la lista permitida, haga clic en **Agregar dominio**. En el panel **Agregar un dominio** , coloque en el nombre de dominio, haga clic en **permitidos** y, a continuación, en **Listo**.

   4. Haga clic en **Guardar**. 

   5. A continuación, asegúrese de que el Administrador de la organización de los equipos otros estos mismos pasos. Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.

### <a name="step-3---test-it"></a>Paso 3: ponerlo a prueba
Para probar el programa de instalación, necesita un usuario de los equipos que no está detrás de un firewall.
  
   1. Después de que usted y el Administrador de la organización han cambiado la configuración del **acceso externo** , debe proceder.
    
   2. En la aplicación de los equipos, buscar por dirección de correo electrónico a esa persona y enviar una solicitud de conversaciones.
    
   3. Pida a su contacto de los equipos para enviar una solicitud de conversaciones. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).
    
   4. Otra forma de comprobar si el problema es el servidor de seguridad es vaya a una ubicación de wifi no detrás de un firewall, como un cibercafé y use los equipos para enviar una solicitud a su contacto para conversaciones. Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicarse con usuarios en un Skype para la organización empresarial en línea

Si va a establecer hasta permiten a los usuarios de los equipos buscan y ponerse en contacto con los usuarios que se encuentran en un Skype para la organización empresarial, será el Administrador de esa organización que se deben seguir estos pasos.

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **Uso de Skype para el centro de administración de negocio** 

Tener la administración en que la organización siga estos pasos:
    
1. En Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**.
  
2. En **Centro de administración de Skype Empresarial**, seleccione **organización** > **comunicaciones externas**.
    
3. Para establecer la comunicación con un negocio específicos o con los usuarios en otro dominio, en el cuadro de lista desplegable, elija **sólo para permitido dominios**.
    
    O BIEN, si desea habilitar la comunicación con todo el mundo que tenga directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta es la configuración predeterminada.
    
4. En **dominios permitidos o bloqueados**, elija **+** y agregue el nombre del dominio que desea permitir. Asegúrese de que el administrador en la otra organización estos mismos pasos. Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.
    
### <a name="related-topics"></a>Temas relacionados

[Inicie sesión en los equipos](sign-in-teams.md)
[recursos de aprendizaje para los equipos de usuario final](enduser-training.md)

