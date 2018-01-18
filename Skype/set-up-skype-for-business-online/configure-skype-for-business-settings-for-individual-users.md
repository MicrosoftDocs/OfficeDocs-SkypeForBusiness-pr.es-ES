---
title: "Administradores de configurar Skype para configuración de negocio para usuarios individuales"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: "Obtenga información sobre cómo cambiar el Skype para configuración de negocio para usuarios individuales como: conferencias de Audio y vídeo, grabación de llamadas y reuniones. "
ms.openlocfilehash: 0623c6dd913316584bd38e4076317c050c4a2812
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administradores: Configurar Skype negocio para usuarios individuales

Este artículo explica cómo los administradores configuran Skype para el negocio para un número reducido de usuarios. Para realizar estos pasos de forma masiva, hemos incluido vínculos a los cmdlets de Windows PowerShell que puede utilizar.
  
Para permitir (o bloquean) todas las personas de su empresa para comunicarse con usuarios externos, consulte:
  
- [Permitir a los usuarios ponerse en contacto con Skype externo para usuarios profesionales](allow-users-to-contact-external-skype-for-business-users.md): puede hacer que su organización utilice avanzada Skype para funciones de negocios (compartir escritorios, busque quién está en línea, etc.) para comunicarse con otras personas en un determinado de confianza empresarial (federado). El artículo también explica cómo bloquear la comunicación con dominios específicos.
    
- [Permiten Skype para usuarios de negocios agregar contactos de Skype](let-skype-for-business-users-add-skype-contacts.md). Puede permitir a la organización utilizar Skype para empresarios para buscar y mensajería instantánea que utilizan Skype, la aplicación gratuita.
    
## <a name="configure-general-settings-for-one-user"></a>Configuración general para un usuario
<a name="__toc325019204"> </a>

Debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para realizar estos pasos.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Seleccione **Admin centros** > **Skype para el negocio**.
    
3. Elegir **los usuarios**.
    
    ![En Skype para el centro de administración de negocios, elegir los usuarios.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Seleccione los usuarios que desea editar.
    
5. En el panel derecho, elija **Editar**.
    
    ![Elija el icono de edición.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. En la página opciones **generales** , seleccione o desactive la casilla de verificación situada junto a las características que desea cambiar y, a continuación, elija **Guardar**.
    
|**Opción**|**Detalles**|
|:-----|:-----|
|Audio y vídeo de alta definición  <br/> |Permitir a esta persona para grabar reuniones audio, reuniones de audio y vídeo, o no les permiten programar cualquier meeetings (ninguno).  <br/> |
|Reuniones y grabar conversaciones  <br/> |Elija lo que esta persona puede registrar.  <br/> Esta opción no está disponible con Skype para Business Basic.  <br/> |
|Para el cumplimiento, desactivar las características no son archivados  <br/> | Elija esta opción si está legalmente necesaria para conservar la información almacenada electrónicamente. <br/>  Esta opción desactiva las funciones que no se capturan cuando haya un [Mantenga In situ](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) establecido el centro de administración de Exchange. Desactiva las siguientes características: <br/>  Transferencia de archivos por mensajería instantánea <br/>  Páginas de OneNote compartidas <br/>  Anotaciones de PowerPoint <br/> |
   
Para configurar estas opciones de forma masiva, usar PowerShell. Consulte [Gestión de directivas en Skype para los negocios en línea](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## <a name="block-external-communications"></a>Bloque de comunicaciones externas
<a name="__toc325019206"> </a>

Después de [Permitir Skype para usuarios de negocios agregar contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todos los usuarios de su empresa, puede bloquear selectivamente comunicaciones externas de determinados individuos siguiendo estos pasos.
  
1. Elegir **usuarios**, seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, elija **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Elija **comunicaciones externas**y, a continuación, desactive las opciones según corresponda:
    
  - **Skype externo para usuarios profesionales**: desactive esta casilla si no desea que el usuario pueda comunicarse con Skype para usuarios profesionales de dominios federados.
    
  - **Los usuarios externos de Skype**: desactive esta casilla si no desea que el usuario sea capaz de comunicarse con personas que utilizan la aplicación freeSkype.
    
3. Haga clic en **Guardar**.
    
Para configurar estas opciones de forma masiva, usar PowerShell. Consulte [administración de las comunicaciones en Skype para los negocios en línea con usuarios externos y las organizaciones](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Editar configuración de conferencia de audio de un usuario
<a name="__toc314837483"> </a>

1. Seleccione **los usuarios**, seleccione el usuario cuya configuración de conferencias de audio que desea para editar, y, a continuación, elija **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Elegir **las conferencias de Audio**, seleccione el proveedor de conferencia de audio, escriba o cambie la información solicitada y, a continuación, haga clic en **Guardar**.
    
|**Configuración de Audioconferencia**|**Descripción**|
|:-----|:-----|
|**Nombre del proveedor** <br/> |Elija el proveedor de la lista.  <br/> |
|**Número gratuito** (obligatorio) <br/> |Para un ACP de terceros, estos números de teléfono son los que recibe del proveedor de conferencia de audio. Si el usuario utiliza Microsoft como proveedor de conferencia de audio, estos serán los números que se establecen en el puente de conferencia de audio. Dar formato a los números como desee que aparezcan en Skype para las convocatorias de reunión de negocios y Teams de Microsoft.  <br/> |
|**Número gratuito** <br/> |Para un ACP de terceros, estos números de teléfono son los que recibe del proveedor de conferencia de audio. Si el usuario utiliza Microsoft como proveedor de conferencia de audio, estos serán los números que se establecen en el puente de conferencia de audio. Dar formato a los números como desee que aparezcan en Skype para las convocatorias de reunión de negocios y Teams de Microsoft.  <br/> |
|**Conferencia ID y PIN** (obligatorio) <br/> |El participante PIN o conferencia código utilizado para unirse a las reuniones que son programadas por este usuario y son proporcionadas por un proveedor de conferencia de audio de terceros. Si el usuario utiliza Microsoft como proveedor de conferencia de audio, esto no será necesario.  <br/> |
   
Para configurar estas opciones de forma masiva, usar PowerShell. Consulte [el teléfono invita números incluidos en](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Temas relacionados 

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

Puede obtener más información en [Conferencias de acceso telefónico en Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
