---
title: Administradores Configurar Skype Empresarial para usuarios individuales
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
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
ms.openlocfilehash: 5be310e47a5094a0e424624cc711311865a5b842
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285308"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administradores: Configurar Skype Empresarial para usuarios individuales

En este artículo se explica cómo los administradores configuran Skype Empresarial para un pequeño número de usuarios. Para realizar estos pasos en masa, hemos incluido vínculos a los cmdlets de Windows PowerShell que puede usar.
  
Para permitir (o impedir) que todos en la empresa puedan comunicarse con personas ajenas a esta, consulte:
  
- [Permitir que los usuarios se pongan en contacto con usuarios externos de Skype empresarial](allow-users-to-contact-external-skype-for-business-users.md): puede permitir que su organización use características avanzadas de Skype empresarial (compartir Escritorios, buscar quién está conectado, etc.) para comunicarse con las personas en una empresa de confianza específica (federada). En este artículo también se explica cómo bloquear la comunicación con dominios específicos.
    
- [Permita que los usuarios de Skype empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md). Puede permitir que su organización use Skype Empresarial para buscar personas que usen la aplicación gratuita Skype y comunicarse con ellas con mensajería instantánea.
    
## <a name="configure-general-settings-for-one-user"></a>Establecer la configuración general de un usuario
<a name="__toc325019204"> </a>

Debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para poder realizar estos pasos.

![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con el centro de administración de Skype empresarial**
  
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
|Audio y vídeo HD  <br/> |Permitir que esta persona grabe reuniones de audio, reuniones de audio y vídeo, o no les permita programar ninguna reunión (ninguna).  <br/> |
|Registrar conversaciones y reuniones  <br/> |Elija lo que puede grabar esta persona.  <br/> Esta opción no está disponible en Skype empresarial Basic.  <br/> |
|Para cumplir con las normativas, desactive las características no archivadas  <br/> | Elija esta opción si tiene la obligación legal de conservar la información almacenada por medios electrónicos. <br/>  Al seleccionar esta opción, se desactivan las características que no se capturan cuando tiene configurada una [retención local](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) en el centro de administración de Exchange. Desactiva las siguientes características: <br/>  Transferencia de archivos por mensajería instantánea <br/>  Páginas de OneNote compartidas <br/>  Anotaciones de PowerPoint <br/> |
   
Para configurar estas opciones en masa, use PowerShell. Consulte [configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="block-external-communications"></a>Bloquear comunicaciones externas
<a name="__toc325019206"> </a>

Después de [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todas las personas de su empresa, puede bloquear de manera selectiva las comunicaciones externas de personas específicas con estos pasos.
  
1. Elija **usuarios**, seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, **** ![elija Editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)edición.
    
2. Elija **Comunicaciones externas** y después desactive las opciones correspondientes:
    
   - **Usuarios externos de Skype Empresarial**: desactive esta casilla si no desea que el usuario pueda comunicarse con los usuarios de Skype Empresarial en dominios federados.
    
   - **Usuarios externos de Skype**: desactive esta casilla si no desea que el usuario pueda comunicarse con personas que usan la aplicación gratuita Skype.
    
3. Haga clic en **Guardar**.
    
Para configurar estas opciones en masa, use PowerShell. Consulte [configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Editar la configuración de audioconferencia para un usuario
<a name="__toc314837483"> </a>

1. Elija **usuarios**, seleccione el usuario cuya configuración de audioconferencias desee editar y, a continuación, elija **Editar** ![edición](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Elija **audioconferencias**, seleccione su proveedor de servicios de audioconferencia, escriba o modifique la información solicitada y, a continuación, haga clic en **Guardar**.
    
|**Configuración de Audioconferencia**|**Descripción**|
|:-----|:-----|
|**Nombre del proveedor** <br/> |Elija su proveedor de la lista.  <br/> |
|**Número gratuito** (obligatorio) <br/> |Para un ACP de terceros, estos números de teléfono son los que recibió del proveedor de servicios de audioconferencia. Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia. Aplique formato a los números tal y como desee que aparezcan en las convocatorias de reunión de Skype empresarial y Microsoft Teams.  <br/> |
|**Número gratuito** <br/> |Para un ACP de terceros, estos números de teléfono son los que recibió del proveedor de servicios de audioconferencia. Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia. Aplique formato a los números tal y como desee que aparezcan en las convocatorias de reunión de Skype empresarial y Microsoft Teams.  <br/> |
|**ID de conferencia y PIN** necesario <br/> |El PIN del participante, o código de conferencia, que se usa para unirse a las reuniones programadas por este usuario y que se proporcionan desde un proveedor de servicios de audioconferencia de terceros. Si el usuario usa Microsoft como el proveedor de servicios de audioconferencia, esto no será necesario.  <br/> |
   
Para configurar estas opciones en masa, use PowerShell. Consulte [establecer los números de teléfono incluidos en los invitados](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Temas relacionados 

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Licencias complementarias de Skype Empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
