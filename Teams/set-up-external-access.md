---
title: Permitir a los usuarios ponerse en contacto con los usuarios de los equipos externos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 'Vea cómo configurar los equipos para permitir a los usuarios comunicarse con usuarios de otra organización, o permita que fuera talk de contactos a ellos. '
ms.openlocfilehash: af4b6a61117e96fdbdf869b2bf7fc54c286b42f0
ms.sourcegitcommit: c05731b8a757864c0f6620bfeda3ae28a3582011
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2018
ms.locfileid: "19863401"
---
# <a name="allow-users-to-contact-external-teams-users"></a>Permitir a los usuarios ponerse en contacto con los usuarios de los equipos externos
  
Siga los pasos de este artículo cuando:
  
- Haya usuarios de diferentes dominios en su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.
    
- Las personas que desee en la organización para usar los equipos ponerse en contacto con las personas de empresas específicas fuera de la organización.
    
- Cualquier persona que desee en el mundo que usa los equipos que puedan buscar y ponerse en contacto con usted, utilizando su dirección de correo electrónico. Si usted y se usa la configuración predeterminada, esto funcionará automáticamente. De lo contrario, deben asegurarse de que la configuración no esté bloqueando su dominio.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Habilitar comunicaciones entre empresas para los usuarios
<a name="bk_preview"> </a>

Debe tener [permisos de administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) en Office 365 en ambas organizaciones para ello.

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png)**utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**.
1. En el panel de navegación izquierdo, vaya a **configuración de toda la organización** > **acceso externo**. 

2. En la parte superior de la página de **acceso externo** , activar **el acceso externo**. 

3. Haga clic en **Guardar**. 

4. Asegúrese de que el administrador en la otra organización sigue los mismos pasos y entra en el dominio para su negocio como un dominio permitido.
 
5. **AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.

  
## <a name="test-and-troubleshoot"></a>Probar y solucionar problemas
<a name="bk_preview"> </a>

 **El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**
  
Para probar el programa de instalación, necesita un contacto en los equipos que no está detrás de un firewall de la compañía.
  
1. Después de cambiar la configuración del acceso externo, **esperar hasta 24 horas para prueba**.
    
2. Buscar su contacto en los equipos y enviar una solicitud de conversaciones.
    
    Si recibe un mensaje que se han podido enviar debido a la directiva de empresa, debe comprobar su [URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Pida a su contacto para enviar una solicitud de conversaciones. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).
    
4. Otra forma de comprobar si el problema es el servidor de seguridad es vaya a una ubicación de wifi no detrás de un firewall, como un cibercafé y use los equipos para enviar una solicitud a su contacto para conversaciones. Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Cómo buscar a otros, y permitir que me encuentren, al conectarme con otro negocio
<a name="bk_preview"> </a>

Después de habilitar el acceso externo con otros usuarios de los equipos, los usuarios puedan encontrar los usuarios federados de los equipos mediante la búsqueda de su nombre de inicio de sesión: por ejemplo, Rob@contoso.com. A continuación, deben agregar a la persona a su lista de contactos.
  
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Sugerencias para configurar las comunicaciones con empresas federadas
<a name="bk_preview"> </a>
    
- Cuando dos usuarios de los equipos con Office 365 dominios se comuniquen entre sí en dominios independientes, sólo pueden utilizar características de los equipos (por ejemplo, las conversaciones de vídeo o uso compartido de escritorio) que están activadas en ambas organizaciones.
    
- Si los usuarios de los equipos de la organización se pone en un juicio o en contexto, se guardarán todas las conversaciones de mensajería instantánea entre ese usuario y otro Skype para los usuarios empresariales o de Skype en **Elementos recuperables** en su buzón. Estas conversaciones no se guardarán en la carpeta **Historial de conversaciones** de su buzón.
  
<a name="bk_preview"> </a>
 
