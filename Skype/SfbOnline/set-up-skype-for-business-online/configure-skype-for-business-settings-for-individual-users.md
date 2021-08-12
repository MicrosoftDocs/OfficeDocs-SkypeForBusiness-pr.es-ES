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
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 54dc4e1ee649fff28ac1c7d0729bfbddae521622d76d07e1723ddcc7fd0bdbf1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312308"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administradores: Configurar Skype Empresarial para usuarios individuales

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> El Microsoft Teams de administración ha sustituido al Skype Empresarial de administración (portal heredado). Todas las opciones de Skype Empresarial están ahora en el centro Teams administración. Debe tener asignado el rol de administrador de [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global o Skype Empresarial administrador para administrar Skype Empresarial características en el centro Teams administración. Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)

En este artículo se explica cómo los administradores configuran Skype Empresarial para un pequeño número de usuarios. Para realizar estos pasos en masa, hemos incluido vínculos a los cmdlets Windows PowerShell que puede usar.
  
Para permitir (o impedir) que todos en la empresa puedan comunicarse con personas ajenas a esta, consulte:
  
- [](allow-users-to-contact-external-skype-for-business-users.md)Permitir a los usuarios ponerse en contacto con usuarios de Skype Empresarial externos: puede permitir que su organización use características avanzadas de Skype Empresarial (compartir escritorios, buscar quién está en línea, etc.) para comunicarse con personas de una empresa específica de confianza (federada). En el artículo también se explica cómo bloquear la comunicación con dominios específicos.
    
- [Permitir Skype Empresarial usuarios agregar Skype contactos.](let-skype-for-business-users-add-skype-contacts.md) Puede permitir que su organización use Skype Empresarial para buscar personas que usen la aplicación gratuita Skype y comunicarse con ellas con mensajería instantánea.
    
## <a name="configure-general-settings-for-one-user"></a>Establecer la configuración general de un usuario
<a name="__toc325019204"> </a>

Debe tener permisos [de administrador para](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) realizar estos pasos.

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**
  
1. Inicie sesión con su cuenta de trabajo o escuela.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**.
    
3. Seleccione **Usuarios**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Elija los usuarios que desea editar:
    
5. En el panel derecho, elija **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. En la página de opciones **General**, active o desactive las casillas correspondientes a las características que quiera cambiar y luego elija **Guardar**.
    
|**Opción**|**Detalles**|
|:-----|:-----|
|Audio y vídeo HD  <br/> |Permita que esta persona grabe reuniones de audio, reuniones de audio y vídeo, o que no le permita programar ninguna reunión (ninguna).  <br/> |
|Registrar conversaciones y reuniones  <br/> |Elija lo que puede grabar esta persona.  <br/> Esta opción no está disponible con Skype Empresarial Básico.  <br/> |
|Para cumplir con las normativas, desactive las características no archivadas  <br/> | Elija esta opción si tiene la obligación legal de conservar la información almacenada por medios electrónicos. <br/>  Al seleccionar esta opción, se desactivan las [](/exchange/security-and-compliance/in-place-and-litigation-holds) características que no se capturan cuando tiene una retención local configurada en el centro de administración Exchange local. Desactiva las siguientes características: <br/>  Transferencia de archivos por mensajería instantánea <br/>  Páginas de OneNote compartidas <br/>  Anotaciones de PowerPoint <br/> |
   
Para configurar estas opciones en masa, use PowerShell. Consulte [Configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="block-external-communications"></a>Bloquear comunicaciones externas
<a name="__toc325019206"> </a>

Después de [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todas las personas de su empresa, puede bloquear de manera selectiva las comunicaciones externas de personas específicas con estos pasos.
  
1. Elija **Usuarios,** seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, **elija Editar** editar ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .
    
2. Elija **Comunicaciones externas** y después desactive las opciones correspondientes:
    
   - **Usuarios externos de Skype Empresarial**: desactive esta casilla si no desea que el usuario pueda comunicarse con los usuarios de Skype Empresarial en dominios federados.
    
   - **Usuarios externos de Skype**: desactive esta casilla si no desea que el usuario pueda comunicarse con personas que usan la aplicación gratuita Skype.
    
3. Haga clic en **Guardar**.
    
Para configurar estas opciones en masa, use PowerShell. Consulte [Configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Editar la configuración de audioconferencia para un usuario
<a name="__toc314837483"> </a>

1. Elija **Usuarios,** seleccione el usuario cuya configuración de audioconferencia desea editar y, a continuación, **elija Editar** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) edición.
    
2. Elija **Audioconferencia,** seleccione su proveedor de audioconferencias, escriba o cambie la información solicitada y, después, haga clic en **Guardar.**
    
|**Configuración de Audioconferencia**|**Descripción**|
|:-----|:-----|
|**Nombre del proveedor** <br/> |Elija su proveedor de la lista.  <br/> |
|**Número gratuito** (obligatorio) <br/> |Para un ACP de terceros, estos números de teléfono son los que ha recibido del proveedor de servicios de audioconferencia. Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia. Aplicar formato a los números como desee que aparezcan en Skype Empresarial y Microsoft Teams de reunión.  <br/> |
|**Número gratuito** <br/> |Para un ACP de terceros, estos números de teléfono son los que ha recibido del proveedor de servicios de audioconferencia. Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia. Aplicar formato a los números como desee que aparezcan en Skype Empresarial y Microsoft Teams de reunión.  <br/> |
|**Id. de conferencia y PIN** (obligatorio) <br/> |El PIN del participante, o código de conferencia, se usa para unirse a las reuniones programadas por este usuario y se proporcionan desde un proveedor de audioconferencia de terceros. Si el usuario usa Microsoft como proveedor de audioconferencias, no será necesario.  <br/> |
   
Para configurar estas opciones en masa, use PowerShell. Vea [Establecer los números de teléfono incluidos en las invitaciones](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Temas relacionados 

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Licencias complementarias de Skype Empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
