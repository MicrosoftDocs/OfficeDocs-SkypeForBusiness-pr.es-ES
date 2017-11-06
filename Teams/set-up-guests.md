---
title: Configurar el acceso de invitado a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Habilite la característica de acceso de invitado en Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a>Configurar el acceso de invitado a Microsoft Teams
======================================

Microsoft Teams se creó a partir de los grupos de Office 365 y también depende de SharePoint Online. Es por ello que se debe habilitar una configuración específica en los grupos de Office 365 y en SharePoint Online, además de tener que activar la característica de acceso de invitado en Teams.


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a>Permitir la adición de invitados en Grupos de Office 365
<a name="bkmk_ControlAddingGuestUsers"> </a>


1. Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. En el menú de navegación, elija **Configuración** y luego **Servicios y complementos**.
    
  
3. Seleccione **Grupos de Office 365**.
    
     ![Grupos de Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. En la página de grupos de Office 365, configure el botón de alternancia en **Activado** o **Desactivado**, dependiendo de si quiere que los propietarios del equipo y el grupo que no pertenecen a la organización accedan a los grupos de Office 365. Pulse o haga clic en el botón de alternancia, cambie a **Activado** junto a **Let group owners add people outside the organization to groups** (Permitir que los propietarios de grupo agreguen a los grupos personas externas a la organización).


![La captura de pantalla muestra el panel Grupos de Office 365 con las opciones activadas para permitir que los miembros del grupo externos a la organización accedan al contenido del grupo y para permitir que los propietarios del grupo agreguen a los grupos personas que no pertenecen a la organización.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a>Habilitar el uso compartido en SharePoint Online

Con la opción Compartir en SharePoint Online, es posible agregar a los invitados a su organización. De forma predeterminada, la opción Compartir está habilitada. Si desea más información sobre cómo se desactiva la opción Compartir, consulte [Activar o desactivar la opción de uso compartido](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).
  
   Los administradores pueden crear cuentas de invitado en Azure Active Directory, aparte de la configuración del uso compartido externo. Si este uso está desactivado, solo el administrador podrá crear cuentas de invitado. 
    

> [!IMPORTANT]
> Si desactiva la opción Compartir, el acceso de invitado no estará disponible. 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Activar o desactivar el acceso de invitado a Microsoft Teams
<a name="bkmk_TurnonOrTurnOff"> </a>

Como administrador de Office 365, debe habilitar la característica de invitado antes de que usted o los usuarios de su organización (específicamente, los propietarios de los equipos) puedan agregar a invitados. 

La configuración de invitado se establece en Azure Active Directory. Los cambios tardan de 2 a 24 en ser efectivos en toda la organización de Office 365. Si un usuario ve el mensaje "Póngase en contacto con su administrador" cuando intenta agregar un invitado a su equipo, es muy probable que la característica de invitado no esté habilitada o que la configuración no haya entrado aún en vigor.



1. Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. En el menú de navegación, elija **Configuración** y luego **Servicios y complementos**.
    
     ![Inicie sesión en Office 365, acceda al Centro de administración de Office 365, seleccione Configuración y, a continuación, elija Servicios y complementos.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. Seleccione **Microsoft Teams**.
    
     ![La captura de pantalla muestra la opción del complemento de Microsoft Teams, como se selecciona en el Centro de administración de Office 365.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. En **Select the user/license type you want to configure** (Seleccione el tipo de usuario/licencia que desea configurar), seleccione **Invitado**.
   
    ![La captura de pantalla del complemento de Microsoft Teams muestra la licencia de invitado seleccionada y la opción de Microsoft Teams establecida en Activado.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. Pulse o haga clic en el botón de alternancia que hay junto a **Turn Microsoft Teams on or off for all users of this type** (Activar o desactivar Microsoft Teams para todos los usuarios de este tipo), cambie a **Activado** para activar Microsoft Teams y el acceso de invitado para su organización y, por último, seleccione **Guardar**. 
    
  

