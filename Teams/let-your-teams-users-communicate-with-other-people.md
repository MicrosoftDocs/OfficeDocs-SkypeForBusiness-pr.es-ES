---
title: Comunicarse con usuarios de Microsoft Teams de otra organización
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
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Vea cómo configurar los equipos para permitir a los usuarios comunicarse con usuarios de otra organización.
ms.openlocfilehash: 6c61c8d932dfe72c1d7764ce78701c0b1e3acfc0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460303"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir que el chat de los usuarios de los equipos y comunicarse con los usuarios de otra organización de los equipos

Siga los pasos de este artículo cuando:
  
- Tienen los usuarios en diferentes dominios en su negocio. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.
    
- Las personas que desee en la organización para usar los equipos ponerse en contacto con las personas de empresas específicas fuera de la organización.
    
- Cualquier persona que desee en el mundo que usa los equipos que puedan buscar y ponerse en contacto con usted, utilizando su dirección de correo electrónico. Si usted y otro usuario tanto habilitación el acceso externo y permitir que los demás dominios, esto funcionará. Si no funciona, el otro usuario, debe asegurarse de que su o su configuración no esté bloqueando su dominio.

Esto le permitirá a los usuarios buscar, llamar y enviar mensajes instantáneos, así como configurar reuniones con usted. Si desea que los usuarios externos tengan acceso a los equipos y los canales, acceso de invitado podría ser una mejor manera para ir. Siga los pasos descritos en este artículo y asegúrese de que al [activar el acceso de invitado](set-up-guests.md) para que los usuarios puedan comunicarse.

> [!IMPORTANT]
> Para poder federar actualmente el cliente de Microsoft Teams a un usuario externo fuera de la organización que actualmente no es un invitado de su inquilino de AAD, debe estar correctamente el programa de instalación para la implementación híbrida y movido a Skype para profesionales en línea. A partir de 25/2/2019, los equipos aún no admite federación nativa sin que el usuario del perfil SIP que se hospedados en Skype para profesionales en línea. Para obtener más información sobre la configuración de su cuenta de seguridad para entornos híbridos y, a continuación, se mueven a los equipos, consulte [Actualización de Skype para su implementación híbrida empresarial en los equipos](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir que el chat de los usuarios de los equipos y comunicarse con los usuarios de otra organización de los equipos

Siga estos pasos.

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Paso 1: asegúrese de configurar los puertos y direcciones URL que son necesarios.

**El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Paso 2: habilitar la organización para comunicarse con otra organización de los equipos

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

   1. En el panel de navegación izquierdo, vaya a **configuración de toda la organización** > **acceso externo**. 

   2. En la parte superior de la página de **acceso externo** , haga clic en **acceso externo** a **en**. 

   3. Si desea permitir que todas las organizaciones de los equipos para comunicarse con los usuarios de su organización, vaya al paso 5. 
   
   4. Si desea limitar que las organizaciones pueden comunicarse con los usuarios de la organización puede permitir que todos los pero algunos dominios o permitir sólo las organizaciones específicas. Para permitir que todos los pero algunos dominios, agregue los dominios que desee bloquear, haga clic en **Agregar dominio**. En el panel **Agregar un dominio** , poner en el nombre de dominio, haga clic en **bloqueado** y, a continuación, en **Listo**. Para limitar las comunicaciones a organizatioins específica, añada esos dominios a la lista con un estado de **Alowed**. Una vez haya agregado cualquier dominio a la lista Permitir, communications a otras organizaciones se limitará a sólo esas organizaciones cuyos dominios se encuentran en la lista Permitir. 
   
   5. Haga clic en **Guardar**. 

   6. A continuación, asegúrese de que el Administrador de la organización de los equipos otros estos mismos pasos. Por ejemplo, en su lista de **permitidos dominios** , su administrador debe introducir el dominio para su negocio si limita a que las organizaciones pueden comunicarse con sus usuarios. 

### <a name="step-3---test-it"></a>Paso 3: ponerlo a prueba
Para probar el programa de instalación, necesita un usuario de los equipos que no está detrás de un firewall.
  
   1. Después de que usted y el Administrador de la organización han cambiado la configuración del **acceso externo** , debe proceder.
    
   2. En la aplicación de los equipos, buscar por dirección de correo electrónico a esa persona y enviar una solicitud de conversaciones.
    
   3. Pida a su contacto de los equipos para enviar una solicitud de conversaciones. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).
    
   4. Otra forma de comprobar si el problema es el servidor de seguridad es vaya a una ubicación de wifi no detrás de un firewall, como un cibercafé y use los equipos para enviar una solicitud a su contacto para conversaciones. Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicarse con usuarios en un Skype para la organización empresarial en línea

Si se establecer para permitir que la búsqueda de los usuarios de los equipos y contacto a los usuarios que se encuentran en un Skype para la organización de empresa que limita quién puede ponerse en contacto con sus usuarios, le pedirá la administración de esa organización que se deben seguir estos pasos.

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **Uso de Skype para el centro de administración de negocio** 

Tener la administración en que la organización siga estos pasos:
    
1. En el centro de administración de Office 365, vaya a **Centros de administrador de** > **& equipos Skype** > **portal heredado**.
  
2. En **Centro de administración de Skype Empresarial**, seleccione **organización** > **comunicaciones externas**.
    
3. Para establecer la comunicación con un negocio específicos o con los usuarios en otro dominio, en el cuadro de lista desplegable, elija **sólo para permitido dominios**.
    
    O bien, si desea habilitar la comunicación con todos los demás en el mundo que tiene abierto Skype para las directivas de negocio, elija **en excepto dominios bloqueados**. Esta es la configuración predeterminada.
    
4. En **dominios permitidos o bloqueados**, elija **+** y agregue el nombre del dominio que desea permitir. Asegúrese de que el administrador en la otra organización estos mismos pasos. Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.
    
### <a name="related-topics"></a>Temas relacionados

[Inicie sesión en Microsoft Teams](sign-in-teams.md)
[recursos de aprendizaje para los equipos de usuario final](enduser-training.md)

