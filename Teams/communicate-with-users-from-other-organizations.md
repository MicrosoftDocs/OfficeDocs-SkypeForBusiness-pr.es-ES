---
title: Llamadas y chats con usuarios de otras organizaciones
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información acerca de cómo llamar, chatear, buscar y agregar usuarios fuera de la organización en Microsoft Teams, a través del acceso externo (federación) y el acceso de invitado.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 401b63aad667d355516486deb6f056e0995dbe26
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031816"
---
<a name="call-and-chat-with-users-from-other-organizations-in-microsoft-teams"></a>Llamadas y chats con usuarios de otras organizaciones en Microsoft Teams
======================================================

Cuando necesite comunicarse y colaborar con personas de fuera de su organización, Microsoft Teams le ofrece dos formas diferentes de hacer que esto ocurra. La primera, **acceso externo (federación)**, le permite buscar, llamar y conversar con usuarios de otros dominios (por ejemplo, contoso.com). La segunda, **acceso de invitado**, le permite agregar personas a los equipos, como invitados, mediante su dirección de correo electrónico. Puede colaborar con los invitados igual que lo haría con cualquier otro usuario de su organización.

Puede usar tanto el acceso externo como el acceso de invitado si lo desea; uno no excluye al otro.

A continuación, le mostramos a grandes rasgos cómo elegir entre ambas (para obtener una comparación detallada, consulte abajo [Comparar el acceso externo y el de invitado](#compare-external-and-guest-access)):

## <a name="external-access"></a>Acceso externo

Use el **acceso externo** (federación) cuando necesite una solución que permita que los usuarios externos de otros dominios le encuentren, le llamen, y conversen o configuren reuniones con usted. Los usuarios externos no tienen acceso a los equipos de la organización o a los recursos de equipo. Elija el acceso externo para comunicarse con los usuarios de fuera de su organización que siguen en Skype Empresarial (en línea o de forma local) o en Skype (disponible a principios de 2020). 

El acceso externo está activado de forma predeterminada en Teams, lo que significa que su organización puede comunicarse con todos los dominios externos. El administrador de Teams puede desactivar esta opción o especificar los dominios que se van a incluir (o excluir). Para obtener más información, consulte [administrar el acceso externo](manage-external-access.md). 

Si desea que los usuarios externos tengan acceso a los equipos y canales, la opción de [acceso de invitado](#guest-access) es más aconsejable. 


## <a name="guest-access"></a>Acceso de invitado

Use el **acceso de invitado** para agregar un usuario individual (independientemente del dominio) a un equipo, donde podrá chatear, hacer llamadas, reunirse y colaborar en los archivos de la organización (almacenados en SharePoint o OneDrive para la Empresa) mediante aplicaciones de Microsoft 365 u Office 365 como Word, Excel o PowerPoint. Se puede otorgar a un usuario invitado casi todas las capacidades de un miembro de equipo nativo. Para más información, consulte [Acceso invitado en Teams](guest-access.md).

- Los invitados se agregarán al Active Directory de su organización
- Para comunicarse con un invitado, este debe de iniciar sesión en Teams con la cuenta de invitado. Esto significa que un invitado puede tener que cerrar sesión en su propia cuenta de Teams para iniciar sesión en la de usted, o cambiar de organización si es la misma cuenta.
- Los usuarios invitados tienen acceso a más recursos en Teams, como archivos, equipos y canales, que los usuarios de acceso externo (federado).
- El administrador de Teams controla en el Centro de administración de Teams todas las tareas que un invitado puede o no realizar. Para más información, consulte [Administrar el acceso de los invitados](manage-guests.md).

Si está listo para habilitar el acceso de los invitados en su organización, comience con [Colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).


## <a name="compare-external-and-guest-access"></a>Comparación entre el acceso de invitado y el acceso externo

| Característica | Usuarios de acceso externo | Usuarios de acceso invitado |
|---------|-----------------------|--------------------|
| El usuario puede conversar con alguien en otra empresa | Sí |Sí |
| El usuario puede llamar a alguien en otra empresa | Sí | Sí |
| El usuario puede ver si una persona de otra empresa está disponible para una llamada o chat | Sí | Sí<sup>1</sup> |
| El usuario puede buscar a usuarios en espacios empresariales externos | Sí<sup>2</sup> | No |
| El usuario puede compartir archivos | No | Sí |
| El usuario puede acceder a los recursos de Teams | No | Sí |
| Se puede agregar un usuario a un chat grupal | No | Sí |
| El usuario puede recibir una invitación a una reunión | Sí | Sí |
| Se pueden agregar usuarios adicionales a un chat con un usuario externo. | No<sup>3</sup> | N/D |
| El usuario se identifica como una parte externa | Sí | Sí |
| Se muestra la presencia | Sí | Sí |
| Se muestra un mensaje de «fuera de la oficina» | No | Sí |
| Se puede bloquear a un usuario individual | No | Sí |
| Se admiten @menciones | Sí<sup>4</sup> | Sí |
| Realizar llamadas privadas | Sí | Sí |
| Ver el número de teléfono de los participantes de la reunión por acceso telefónico | No<sup>5</sup> | Sí |
| Permitir vídeo IP | Sí | Sí |
| Modo de uso compartido de pantalla | Sí<sup>4</sup> | Sí |
| Se permite Reunirse ahora | No | Sí |
| Editar los mensajes enviados | Sí<sup>4</sup> | Sí |
| Se pueden eliminar los mensajes enviados | Sí<sup>4</sup> | Sí |
| Usar Giphy en la conversación | Sí<sup>4</sup> | Sí |
| Usar memes en las conversaciones | Sí<sup>4</sup> | Sí |
| Usar Adhesivos en las conversaciones | Sí<sup>4</sup> | Sí |
||||

<sup>1</sup> Si el usuario se ha agregado como invitado y ha iniciado sesión como invitado en el espacio empresarial del invitado.<br>
<sup>2</sup> Solo mediante la dirección de correo o el Protocolo de inicio de sesión (SIP)<br>
<sup>3</sup> El chat externo (federado) solo es 1:1.<br>
<sup>4</sup> Compatible con chat 1:1 entre dos usuarios de Teams solo de dos organizaciones diferentes. <br>
<sup>5</sup> De forma predeterminada, los participantes externos no pueden ver el número de teléfono de los participantes de marcado. Si desea mantener la privacidad de estos números de teléfono, seleccione **Tonos** para **Entrada/salida tipo de anuncio** (esto evita que Teams lean los números). Para obtener más información, consulte [Activar o desactivar los anuncios de entrada y salida para las reuniones de Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).

## <a name="related-topics"></a>Temas relacionados

[Acceso externo a Teams](manage-external-access.md)

[Acceso de invitado a Teams](guest-access.md)

