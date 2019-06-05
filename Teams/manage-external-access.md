---
title: Administrar el acceso externo (federación) en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: Su administrador de ti puede configurar el acceso externo para otros dominios (Federación) para permitir que los usuarios de esos dominios participen en Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702723"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>Administrar el acceso externo (federación) en Microsoft Teams
======================================================

Con el acceso externo de Microsoft Teams, los usuarios de otros dominios pueden participar en tus chats y llamadas. También puede permitir que los usuarios externos que siguen usando Skype empresarial online o Skype empresarial local participen en él. 

El acceso externo (Federación) y el acceso de invitados son diferentes:

- Acceso de invitado concede permiso de acceso a una persona. Acceso externo concede permiso de acceso a un dominio completo.

- El acceso de invitados, una vez otorgado por el propietario de un equipo, permite que un invitado [tenga acceso a recursos](guest-experience.md), como archivos y debates de canales, para un equipo específico y conversa con otros usuarios del equipo al que han sido invitados. Con el acceso externo (chat federado), los participantes del chat externo no tienen acceso a los equipos de la organización o a los recursos del equipo. Solo pueden participar en un chat federado. Los administradores de inquilinos pueden elegir entre las dos opciones de comunicación dependiendo del nivel de colaboración que sea deseable con la parte externa. Los administradores pueden elegir entre dos enfoques o ambos, según las necesidades de la organización, pero recomendamos habilitar el acceso de invitados para disfrutar de una experiencia de Teams más completa. 

Consulte la tabla siguiente para obtener una comparación de las características de acceso externo e invitado.

| Característica | Usuarios de acceso externo | Usuarios de acceso de invitado |
|---------|-----------------------|--------------------|
| El usuario puede chatear con alguien de otra empresa | Sí |Sí |
| El usuario puede llamar a alguien de otra empresa | Sí | Sí |
| El usuario puede ver si alguien de otra empresa está disponible para realizar llamadas o chats | Sí | Sí<sup>1</sup> |
| El usuario puede buscar usuarios en espacios empresariales externos | Sí<sup>2</sup> | No |
| El usuario puede compartir archivos | No | Sí |
| El usuario puede acceder a los recursos de Teams | No | Sí |
| Se puede Agregar un usuario a un chat grupal | No | Sí |
| Se puede Agregar un usuario a una reunión | Sí | Sí |
| Se pueden agregar usuarios adicionales a un chat con un usuario externo | No<sup>3</sup> | N/D |
| El usuario se identifica como una fiesta externa | Sí | Sí |
| Se muestra la presencia | Sí | Sí |
| Se muestra un mensaje de fuera de la oficina | No | Sí |
| Usuario individual puede bloquearse | No | Sí |
| @mentions son compatibles | No | Sí |
| Hacer llamadas privadas | Sí | Sí |
| Permitir video IP | Sí | Sí |
| Modo de uso compartido de pantalla | Sí | Sí |
| Permitir reunirse ahora | No | Sí |
| Editar mensajes enviados | Sí | Sí |
| Puede eliminar mensajes enviados | Sí | Sí |
| Usar Giphy en la conversación | Sí | Sí |
| Usar memes en una conversación | Sí | Sí |
| Usar adhesivos en la conversación | Sí | Sí |
||||

<sup>1</sup> siempre que el usuario se haya agregado como invitado y haya iniciado sesión como invitado para el inquilino invitado.<br>
<sup>2</sup> solo por correo electrónico o dirección de protocolo de inicio de sesión (SIP).<br>
<sup>3</sup> el chat externo (federado) solo es 1:1.

> [!NOTE]
> Para obtener más información sobre las características de invitado y la experiencia de invitado, vea [activar o desactivar el acceso de invitado a Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) y [Cómo es la experiencia de invitado](https://docs.microsoft.com/microsoftteams/guest-experience).

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a>Activar o desactivar el acceso externo (los usuarios pueden comunicarse con usuarios de Skype empresarial y Teams)

Puede usar Microsoft Teams & el centro de administración de Skype empresarial para administrar el acceso externo.

1. En el centro de administración de Microsoft Teams & de Skype empresarial, seleccione **configuración** > **externa**de la organización.

     ![Captura de pantalla de la configuración de acceso externo a toda la organización](media/manage-external-access-1.png).

2. Activar o desactivar los **usuarios pueden comunicarse con los usuarios de Skype empresarial y Teams** cambien a **activado** o desactivado. ****

     ![Captura de pantalla del interruptor de acceso externo activado](media/manage-external-access-2.png).

3. Haga clic en **Guardar **. 

## <a name="add-or-block-a-domain"></a>Agregar o bloquear un dominio

Siga estos pasos para agregar un dominio o deshabilitar el acceso externo para un dominio.

1. En el centro de administración de Microsoft Teams & de Skype empresarial, seleccione **configuración** > **externa**de la organización.

2. Seleccione **Agregar un dominio**. 
 
    ![Captura de pantalla de la página acceso externo con el vínculo Agregar un dominio](media/manage-external-access-3.png).

   Aparece el panel **Agregar un dominio** .

    ![Captura de pantalla del panel agregar un dominio](media/manage-external-access-4.png).


3. En **Agregar un dominio**, escriba el nombre del dominio. por ejemplo, escriba Contoso.com.

4. Seleccione **Permitido** o **Bloqueado**. Puedes cambiar esta configuración en cualquier momento.

2. Seleccione **listo**.

Después de agregar un dominio, verá el nombre de dominio y el estado añadidos a la lista de dominios en la página acceso externo.

## <a name="more-information"></a>Más información

Para obtener información sobre el acceso de invitados en Microsoft Teams, consulte [administrar el acceso de invitado en Microsoft Teams](manage-guests.md).
