---
title: Comunicación con usuarios de otras organizaciones en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Infórmese sobre cómo comunicarse con usuarios de otras organizaciones en Microsoft Teams mediante acceso externo (federación) y el acceso de invitado.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 8132fa07445beb9e9d26195a4269d025169ec94f
ms.sourcegitcommit: d46e739785595727e2b3e1e5f96f5bff65e78540
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753387"
---
<a name="communicate-with-users-from-other-organizations-in-microsoft-teams"></a>Comunicación con usuarios de otras organizaciones en Microsoft Teams
======================================================

Microsoft Teams le ofrece dos formas diferentes para comunicarse y colaborar con personas de fuera de su organización. La primera es el **acceso externo** (federación) que le permite buscar, llamar y conversar con usuarios de otros dominios (como contoso.com). La segunda es el **acceso de invitado** que le permite agregar personas a sus equipos como invitados, mediante su dirección de correo. Puede colaborar con los invitados igual que lo haría con cualquier otro usuario de su organización.

Puede usar tanto el acceso externo como el acceso de invitado si lo desea; uno no excluye al otro.

A continuación, le mostramos a grandes rasgos cómo elegir entre ambas (para obtener una comparación detallada, consulte abajo [Comparar el acceso externo y el de invitado](#compare-external-and-guest-access)):

## <a name="external-access"></a>Acceso externo

Use el **acceso externo** (federación) cuando necesite una solución para que los usuarios externos de otros dominios le encuentren, le llamen, y conversen y concierten reuniones con usted. Los usuarios externos no tienen acceso a los equipos de su organización ni a los recursos de su equipo. Elija el acceso externo para comunicarse con los usuarios externos que siguen usando Skype Empresarial (en línea o local) o Skype (a partir de principios de 2020). 

El acceso externo está activado de forma predeterminada en Teams, lo que significa que su organización puede comunicarse con todos los dominios externos. El administrador Teams puede desactivar esta opción o especificar los dominios que se van a incluir (o excluir). Para obtener más información, consulte [Administrar el acceso externo](manage-external-access.md). 

Si desea que los usuarios externos tengan acceso a los equipos y canales, la opción de [acceso de invitado](#guest-access) es más aconsejable. 


## <a name="guest-access"></a>Acceso de invitado

Use el **acceso de invitado** para agregar un usuario individual (independientemente del dominio) a un equipo, donde podrá chatear, hacer llamadas, reunirse y colaborar en los archivos de la organización (almacenados en SharePoint o OneDrive para la Empresa) mediante aplicaciones de Office 365 como Word, Excel o PowerPoint. A un usuario invitado se le pueden dar casi todas las mismas capacidades de equipo que a un miembro de equipo nativo. Para obtener más información, consulte [Acceso de invitado a Teams](guest-access.md).

- Los invitados se agregarán al Active Directory de su organización
- Para comunicarse con un invitado, este debe haber iniciado sesión en Teams con su cuenta de invitado. Esto significa que un invitado puede tener que cerrar sesión en su propia cuenta de Teams para iniciar sesión en la de usted.
- Los usuarios invitados tienen acceso a más recursos en Teams, como archivos, equipos y canales, que los usuarios de acceso externo (federado).
- El administrador de Teams controla en el Centro de administración de Teams todas las tareas que un invitado puede o no realizar. Para obtener más información, consulte [Administrar el acceso de invitado](manage-guests.md).

Si está listo para activar el acceso de invitado en su organización, comience por la [Lista de comprobación de acceso de invitado](guest-access-checklist.md).


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
<sup>4</sup> Compatible con chat 1:1 entre dos usuarios de Teams solo de dos organizaciones diferentes. *Esta es una característica en versión preliminar o anticipada.*

## <a name="related-topics"></a>Temas relacionados

[Acceso externo a Teams](manage-external-access.md)

[Acceso de invitado a Teams](guest-access.md)

