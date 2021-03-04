---
title: Usar el acceso de invitados y el acceso externo para colaborar con personas fuera de su organización
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Priority
description: Obtenga información acerca de cómo buscar y agregar usuarios de fuera de la organización en Microsoft Teams, así como cómo llamarlos y chatear con ellos, mediante el acceso externo (federación) y el acceso de invitado.
ms.openlocfilehash: e3524bfeb7e21e18d0d742c7208bbe307bdd16c8
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421325"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>Usar el acceso de invitados y el acceso externo para colaborar con personas fuera de su organización

Cuando necesite comunicarse y colaborar con otras personas fuera de su organización, Microsoft Teams le ofrece dos opciones:

- **Acceso externo**: un tipo de federación que permite a los usuarios buscar usuarios de otras organizaciones, así como llamarlos y chatear con ellos. Estas personas no se pueden agregar a los equipos a menos que se les invite.
- **Acceso de invitado**: el acceso de invitado le permite invitar a personas de fuera de la organización a unirse a un equipo. Las personas invitadas obtienen una cuenta de invitado en Azure Active Directory.

Tenga en cuenta que Teams le permite invitar a personas de fuera de su organización a reuniones. Esto no requiere que se configure el acceso externo ni de invitado.

## <a name="external-access-federation"></a>Acceso externo (federación)

Configure el acceso externo si necesita buscar personas de fuera de su organización que usen Teams, Skype Empresarial (en línea o local) o Skype, así como llamarlas o chatear y organizar reuniones con ellas. 

De forma predeterminada, el acceso externo está habilitado para todos los dominios. Puede permitir o bloquear dominios específicos, o desactivar el acceso externo, para restringirlo.

![Captura de pantalla de la configuración de acceso externo](media/external-access-federation-settings.png)

Para configurar el acceso externo, vea [Administrar el acceso externo](manage-external-access.md). 

## <a name="guest-access"></a>Acceso de invitado

Use el acceso de invitado para agregar a una persona de fuera de su organización a un equipo, donde puede chatear, llamar, reunirse y colaborar en archivos. A un invitado se le pueden dar casi todos los mismos permisos de Teams que a un miembro nativo de un equipo.

Los invitados se agregan al directorio de Azure Active Directory de la organización como usuarios B2B y deben iniciar sesión en Teams con su cuenta de invitado. Esto significa que es posible que un invitado tenga que cerrar sesión en su propia organización para iniciar sesión en la suya.

Para configurar el acceso de invitado para Teams, vea [Colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

## <a name="compare-external-and-guest-access"></a>Comparación entre el acceso de invitado y el acceso externo

En las tablas siguientes se muestran las diferencias entre usar el acceso externo (federación) y los invitados. En ambos casos, se identifica a usuarios de fuera de la organización como externos.

### <a name="things-your-users-can-do"></a>Cosas que pueden hacer los usuarios

| Los usuarios pueden | Usuarios de acceso externo | Invitados |
|---------|-----------------------|--------------------|
| Chatear con personas de otra organización | Sí | Sí |
| Llamar a alguien de otra organización | Sí | Sí |
| Ver si una persona de otra organización está disponible para una llamada o chat | Sí | Sí<sup>1</sup> |
| Buscar personas de otras organizaciones | Sí<sup>2</sup> | No |
| Compartir archivos | No | Sí |
| Ver el mensaje de fuera de la oficina | No | Sí |
| Bloquear a alguien en otra organización | No | Sí |
| Usar las @menciones | Sí<sup>3</sup> | Sí |

### <a name="things-people-outside-your-organization-can-do"></a>Cosas que pueden hacer las personas de fuera de la organización

| Las personas de fuera de la organización pueden | Usuarios de acceso externo | Invitados |
|---------|-----------------------|--------------------|
| Acceder a los recursos de Teams | No | Sí |
| Agregarse a un chat grupal | No | Sí |
| Invitarse a una reunión | Sí | Sí |
| Realizar llamadas privadas | Sí | Sí<sup>5</sup> |
| Ver el número de teléfono de los participantes de la reunión por acceso telefónico | No<sup>4</sup> | Sí |
| Usar vídeo IP | Sí | Sí<sup>5</sup> |
| Uso compartido de la pantalla | Sí<sup>3</sup> | Sí<sup>5</sup> |
| Usar Reunirse ahora | No | Sí<sup>5</sup> |
| Editar los mensajes enviados | Sí<sup>3</sup> | Sí<sup>5</sup> |
| Eliminar mensajes enviados | Sí<sup>3</sup> | Sí<sup>5</sup> |
| Usar Giphy en las conversaciones | Sí<sup>3</sup> | Sí<sup>5</sup> |
| Usar memes en las conversaciones | Sí<sup>3</sup> | Sí<sup>5</sup> |
| Usar adhesivos en las conversaciones | Sí<sup>3</sup> | Sí<sup>5</sup> |
| Se muestra la presencia | Sí | Sí |
| Usar las @menciones | Sí<sup>3</sup> | Sí |

<br>

<sup>1</sup> Si el usuario se ha agregado como invitado y ha iniciado sesión con la cuenta de invitado.<br>
<sup>2</sup> Solo mediante la dirección de correo o el Protocolo de inicio de sesión (SIP).<br>
<sup>3</sup> Compatible con chat individual entre dos usuarios de Teams solo de dos organizaciones diferentes. <br>
<sup>4</sup> Por defecto, los participantes externos no pueden ver los números de teléfono de los participantes mediante teléfono. Si desea mantener la privacidad de estos números de teléfono, seleccione **Tonos** de **entrada/salida tipo de anuncio** (esto evita que los Teams lean los números). Para obtener más información, consulte [Activar o desactivar los anuncios de entrada y salida de las reuniones en Microsoft Teams.](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md). <br>
<sup>5</sup> Está permitido de forma predeterminada, pero el administrador de Teams puede desactivarlo.

## <a name="related-topics"></a>Temas relacionados

[Acceso externo a Teams](manage-external-access.md)

[Acceso de invitado a Teams](guest-access.md)

