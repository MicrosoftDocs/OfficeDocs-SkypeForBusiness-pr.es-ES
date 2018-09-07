---
title: Administradores Configurar Skype Empresarial para usuarios individuales
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 1296ec96d194be80ae3c48a947a0398f0eefb4e3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860333"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administradores: Configurar Skype Empresarial para usuarios individuales

En este artículo se explica cómo los administradores configuran Skype Empresarial para un pequeño número de usuarios. Para llevar a cabo estos pasos de forma masiva, hemos incluido vínculos a los cmdlets de Windows PowerShell que puede usar.
  
Para permitir (o impedir) que todos en la empresa puedan comunicarse con personas ajenas a esta, consulte:
  
- [Permitir a los usuarios ponerse en contacto con Skype externo para usuarios profesionales](allow-users-to-contact-external-skype-for-business-users.md): puede permitir que la organización utilice avanzada Skype para las características de Business (recurso compartido de escritorios, aspecto para quién está en línea, etc.) para comunicarse con personas en una determinada de confianza empresarial (federado). El artículo también explica cómo bloquear la comunicación con los dominios específicos.
    
- [Permiten Skype para usuarios profesionales agregar contactos de Skype](let-skype-for-business-users-add-skype-contacts.md). Puede permitir que su organización use Skype Empresarial para buscar personas que usen la aplicación gratuita Skype y comunicarse con ellas con mensajería instantánea.
    
## <a name="configure-general-settings-for-one-user"></a>Establecer la configuración general de un usuario
<a name="__toc325019204"> </a>

Debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para llevar a cabo estos pasos.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**.
    
3. Seleccione **Usuarios**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Elija los usuarios que desea editar:
    
5. En el panel derecho, elija **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. En la página de opciones **General**, active o desactive las casillas correspondientes a las características que quiera cambiar y luego elija **Guardar**.
    
|**Opción**|**Detalles**|
|:-----|:-----|
|Audio y vídeo HD  <br/> |Permita que esta persona pueda grabar reuniones de audio, reuniones con audio y vídeo, o impedirle que programe reuniones (ninguna).  <br/> |
|Registrar conversaciones y reuniones  <br/> |Elija lo que puede grabar esta persona.  <br/> Esta opción no está disponible con Skype para empresarial básica.  <br/> |
|Para cumplir con las normativas, desactive las características no archivadas  <br/> | Elija esta opción si tiene la obligación legal de conservar la información almacenada por medios electrónicos. <br/>  Si selecciona esta opción, se desactiva las características que no se capturan cuando haya una [Conservación local](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurado en el centro de administración de Exchange. Desactiva las siguientes características: <br/>  Transferencia de archivos por mensajería instantánea <br/>  Páginas de OneNote compartidas <br/>  Anotaciones de PowerPoint <br/> |
   
Para configurar estas opciones en masa, use PowerShell. Consulte [Administrar directivas en Skype Empresarial Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## <a name="block-external-communications"></a>Bloquear comunicaciones externas
<a name="__toc325019206"> </a>

Después de [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todas las personas de su empresa, puede bloquear de manera selectiva las comunicaciones externas de personas específicas con estos pasos.
  
1. Elija **los usuarios**, seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, elija **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Elija **Comunicaciones externas** y después desactive las opciones correspondientes:
    
  - **Usuarios externos de Skype Empresarial**: desactive esta casilla si no desea que el usuario pueda comunicarse con los usuarios de Skype Empresarial en dominios federados.
    
  - **Usuarios externos de Skype**: desactive esta casilla si no desea que el usuario pueda comunicarse con personas que usan la aplicación gratuita Skype.
    
3. Haga clic en **Guardar**.
    
Para configurar estas opciones en masa, use PowerShell. Consulte [Administrar comunicaciones en Skype Empresarial Online con usuarios y organizaciones externos](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Editar configuración de conferencia de audio de un usuario
<a name="__toc314837483"> </a>

1. Seleccione **los usuarios**, seleccione el usuario cuya configuración de conferencias de audio wan para editar, y, a continuación, elija **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Elija **conferencias de Audio**, seleccione el proveedor de conferencias de audio, escriba o cambiar la información solicitada y, a continuación, haga clic en **Guardar**.
    
|**Configuración de Audioconferencia**|**Descripción**|
|:-----|:-----|
|**Nombre del proveedor** <br/> |Elija su proveedor de la lista.  <br/> |
|**Número gratuito** (obligatorio) <br/> |Un ACP de terceros, estos números de teléfono son los que le proporcionó el proveedor de conferencia de audio. Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia. Dar formato a los números tal como desea que aparezca en Skype para las convocatorias de reunión de Microsoft Teams y profesionales.  <br/> |
|**Número gratuito** <br/> |Un ACP de terceros, estos números de teléfono son los que le proporcionó el proveedor de conferencia de audio. Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia. Dar formato a los números tal como desea que aparezca en Skype para las convocatorias de reunión de Microsoft Teams y profesionales.  <br/> |
|**PIN y el identificador de conferencia** (obligatorio) <br/> |El participante PIN o conferencia código, utilizado para unirse a reuniones que son programadas por este usuario y se proporcionan desde un proveedor de conferencia de audio de terceros. Si el usuario está utilizando Microsoft como proveedor de conferencias de audio, esto no sea necesario.  <br/> |
   
Para configurar estas opciones de configuración de forma masiva, use PowerShell. Vea [el teléfono los números incluidos en invitaciones](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Temas relacionados 

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Licencias complementarias de Skype Empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 