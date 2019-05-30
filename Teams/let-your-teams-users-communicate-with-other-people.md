---
title: Comunicarse con usuarios de Microsoft Teams de otra organización
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Vea cómo configurar Teams para permitir que los usuarios se comuniquen con los usuarios de otra organización.
ms.openlocfilehash: e9e2a60c7f1f93df56408976a92e4aa47f3e486e
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494693"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir a los usuarios de su equipo conversar y comunicarse con los usuarios de otra organización de Teams

Siga los pasos de este artículo cuando:
  
- Tiene usuarios en diferentes dominios de su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.
    
- Quiere que las personas de su organización usen Teams para ponerse en contacto con personas de empresas específicas de fuera de su organización.
    
- Desea que cualquier persona del mundo que use Teams pueda encontrarse y ponerse en contacto con usted, usando su dirección de correo electrónico. Si usted y otro usuario habilitan el acceso externo y permiten los dominios de cada uno, esto funcionará. Si no funciona, el otro usuario debe asegurarse de que su configuración no esté bloqueando su dominio.

Esto permitirá a los usuarios buscar, llamar y enviar mensajes instantáneos, así como configurar reuniones contigo. Si quiere que los usuarios externos tengan acceso a los equipos y los canales, el acceso de invitados puede ser una mejor manera de hacerlo. Siga los pasos que se indican en este artículo y asegúrese de [activar el acceso de invitado](set-up-guests.md) para que los usuarios puedan comunicarse.

> [!IMPORTANT]
> Para federarse en este momento dentro del cliente de Microsoft Teams a un usuario externo fuera de su organización que no es actualmente invitado de su AAD/inquilino, debe estar configurado correctamente para un híbrido y pasar a Skype empresarial online. A partir de 2/25/2019, Teams aún no es compatible con la Federación nativa sin que el usuario del perfil SIP se haya alojado en Skype empresarial online. Para obtener más información sobre cómo configurar su cuenta para entornos híbridos y después migrada a Teams, consulte [actualizar la implementación híbrida de Skype empresarial a teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir a los usuarios de su equipo conversar y comunicarse con los usuarios de otra organización de Teams

Siga estos pasos.

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Paso 1: Asegúrese de configurar los puertos y las direcciones URL que se necesitan.

**El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Paso 2: permitir que su organización se comunique con otra organización de Teams

![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**

   1. En el navegación de la izquierda, vaya a **configuración** > de**acceso externo**de la organización. 

   2. En la parte superior de la página **acceso externo** , haga clic en **acceso externo** a **activado**. 

   3. Si desea permitir que todas las organizaciones de Teams se comuniquen con los usuarios de su organización, vaya al paso 5. 
   
   4. Si desea limitar las organizaciones que pueden comunicarse con los usuarios de su organización, puede permitir todos los dominios excepto algunos, o solo permitir organizaciones específicas. Para permitir todos los dominios excepto algunos, agregue los dominios que desea bloquear haciendo clic en **Agregar dominio**. En el panel **Agregar un dominio** , escriba el nombre de dominio, haga clic en **bloqueado** y luego en **listo**. Para limitar las comunicaciones a organizatioins específicos, agregue esos dominios a la lista con el estado **permitido**. Una vez que haya agregado cualquier dominio a la lista de permitidos, las comunicaciones con otras organizaciones se limitarán a las organizaciones cuyos dominios estén en la lista de permitidos. 
   
   5. Haga clic en **Guardar **. 

   6. A continuación, asegúrese de que el administrador de la organización de otros equipos realiza estos mismos pasos. Por ejemplo, en su lista de **dominios permitidos** , su administrador debe entrar en el dominio de su empresa si limita las organizaciones que pueden comunicarse con sus usuarios. 

### <a name="step-3---test-it"></a>Paso 3: pruébelo
Para probar la configuración, necesita un usuario de teams que no esté detrás de su firewall.
  
   1. Después de que usted y el administrador de la organización hayan cambiado la configuración de **acceso externo** , debe estar listo.
    
   2. En la aplicación de Teams, busque la persona por dirección de correo electrónico y envíe una solicitud a una conversación.
    
   3. Pídale al contacto de su equipo que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).
    
   4. Otra forma de comprobar si el problema es el Firewall es ir a una ubicación WiFi que no esté detrás de su firewall, como una cafetería, y usar Teams para enviar una solicitud a su contacto para conversar. Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicarse con los usuarios en una organización de Skype empresarial online

Si está configurando para permitir que los usuarios de su equipo encuentren y se pongan en contacto con usuarios que están en una organización de Skype empresarial y que limitan quién puede comunicarse con sus usuarios, deberá pedirle al administrador de esa organización que siga estos pasos.

![Un icono que muestra el logotipo](media/sfb-logo-30x30.png) de Skype empresarial con el **centro de administración de Skype empresarial** 

Haga que el administrador de la organización Realice estos pasos:
    
1. En el centro de administración de Office 365, vaya a **centros** > de administración**equipo & de Skype** > **Legacy**.
  
2. En el **centro de administración de Skype empresarial**, elija**comunicaciones externas**de la **organización** > .
    
3. Para configurar la comunicación con una empresa específica o con usuarios de otro dominio, en el cuadro desplegable, elija **activado solo para los dominios permitidos**.
    
    O, si desea permitir la comunicación con cualquier persona del mundo que tenga abiertas las directivas de Skype empresarial, elija **activado excepto para los dominios bloqueados**. Esta es la configuración que se aplica normalmente.
    
4. En **dominios bloqueados o**permitidos **+** , elija y agregue el nombre del dominio que desea permitir. Asegúrese de que el administrador de la otra organización realiza estos mismos pasos. Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.
    
### <a name="related-topics"></a>Temas relacionados

[Iniciar sesión en Microsoft Teams](sign-in-teams.md)
[aprendizaje para usuarios finales para equipos](enduser-training.md)

