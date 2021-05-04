---
title: Experiencia de invitado en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Este artículo describe la funcionalidad de Microsoft Teams disponible para los invitados.
ms.openlocfilehash: e0efaaf036816980f5e104efebda253411827258
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129729"
---
# <a name="guest-experience-in-teams"></a>Experiencia de invitado en Teams

Cuando se invita a un invitado a unirse a un equipo, recibirá un mensaje de correo electrónico de bienvenida. Este mensaje contiene cierta información sobre el equipo y lo que puede esperar de él ahora que es miembro. El invitado debe aceptar la invitación seleccionando el enlace **Abrir Microsoft Teams** incluido en el mensaje de correo electrónico antes de poder acceder al equipo y a sus canales.
    
![Recorte de pantalla que muestra un ejemplo de correo electrónico de bienvenida](media/guest-experience-image1.png)
    
Todos los miembros del equipo ven un mensaje en el hilo del canal en el que se anuncia que el propietario del equipo ha agregado a un invitado y da el nombre del invitado. Todos los miembros del equipo pueden identificar con facilidad quién es un invitado. Una etiqueta en la esquina superior derecha de la conversación del canal indica el número de invitados en el equipo y la etiqueta **(Invitado)** se muestra junto al nombre de cada invitado.

![Recorte de pantalla en donde se muestra la etiqueta que indica el número de invitados en un equipo](media/guest-experience-image2.png)

Consulte los siguientes vídeos sobre la experiencia de invitado en Teams:
- [Unirse a un equipo como invitado](https://support.office.com/article/join-a-team-as-a-guest-928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Unirse a una reunión de Teams con invitados](https://support.office.com/article/join-a-company-meeting-a120c282-063d-46b8-b973-851197ab75d8)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Comparación entre las funciones de los miembros del equipo y los invitados

En la tabla siguiente se compara la funcionalidad de Teams disponible para los miembros del equipo de la organización y sus invitados. Los administradores de Teams controlan las características disponibles para los invitados.

| Función en Teams | Usuario de Teams de la organización | Invitado |
|:-----|:-----|:-----|
|Crear un canal  <br/>  *Los propietarios del equipo controlan este parámetro.*  <br/> |&#x2713;|&#x2713;|
|Participar en un chat privado  <br/> |&#x2713;|&#x2713;|
|Participar en una conversación del canal  <br/> |&#x2713;|&#x2713;|
|Publicar, eliminar y editar mensajes  <br/> |&#x2713;|&#x2713;|
|Compartir un archivo del canal  <br/> |&#x2713;|&#x2713;|
|Acceder a los archivos de SharePoint<br/> |&#x2713;|&#x2713;|
|Adjuntar archivos<br/> |&#x2713;|Solo publicaciones de canal|
|Descargar archivos de chats privados<br/> |&#x2713;|&#x2713;|
|Buscar en los archivos<br/> |&#x2713;||
|Compartir un archivo de chat  <br/> |&#x2713;||
|Agregar aplicaciones (pestañas, bots o conectores)  <br/> |&#x2713;||
|Crear reuniones o acceder a las programaciones  <br/> |&#x2713;||
|Acceder al almacenamiento de OneDrive para la Empresa  <br/> |&#x2713;||
|Crear directivas de acceso de invitado para todo el espacio empresarial y para los equipos y canales  <br/> |&#x2713;||
|Invitar a un usuario fuera del dominio de la organización en Microsoft 365 u Office 365 <br/>  *Los propietarios del equipo controlan estos ajustes.*  <br/> <br/> |&#x2713;||
|Crear un equipo  <br/> |&#x2713;||
|Descubrir y unirse a un equipo público  <br/> |&#x2713;||
|Ver organigrama  <br/> |&#x2713;||
|Usar traducción incorporada  <br/> |&#x2713;||
|Convertirse en propietario del equipo  <br/> |&#x2713;||

En la tabla siguiente se muestran las características de las llamadas y las reuniones disponibles para los invitados, en comparación con otros tipos de usuario.

| Característica de llamada | Invitado | Usuario E1 y E3 | Usuario de voz E5 y empresarial |
| --------------- | ----- | -------------- | -------------- |
| Llamadas de VoIP | Sí | Sí | Sí |
| Llamadas de grupo | Sí | Sí | Sí |
| Controles de llamada básicos compatibles (poner en espera, silenciar, activar o desactivar vídeo, pantalla compartida) | Sí | Sí | Sí |
| Transferir destino | Sí | Sí | Sí |
| Transferir una llamada | Sí | Sí | Sí |
| Transferencia consultiva | Sí | Sí | Sí |
| Agregar a otros usuarios a la llamada mediante VoIP | Sí | Sí | Sí |
| Agregar usuarios por número de teléfono a una llamada | No | No | Sí |
| Reenviar destino | No | Sí | Sí |
| Destino del grupo de llamada | No | Sí | Sí |
| Destino sin responder | No | Sí | Sí |
| Puede ser el destino de una llamada federada | No | Sí | Sí |
| Hacer llamadas federadas | No | Sí | Sí |
| Reenviar de inmediato sus llamadas | No | No | Sí |
| Hacer sonar simultáneamente sus llamadas | No | No | Sí |
| Redirigir las llamadas sin contestar | No | No | Sí |
| Las llamadas perdidas pasan al buzón de voz | No | No<sup>1</sup> |Sí |
| Tener un número de teléfono al que puede recibir llamadas | No | No | Sí |
| Llamar a números de teléfono | No | No | Sí |
| Acceder a la configuración de la llamada | No | No | Sí |
| Cambiar el saludo del buzón de voz | No | No<sup>1</sup> | Sí |
| Cambiar los tonos de llamada | No | No  | Sí |
| Compatibilidad con TTY | No | No | Sí |
| Tener delegados | No | No | Sí |
|  Ser un delegado | No | No | Sí |

<sup>1</sup> Esta característica estará disponible próximamente.

> [!NOTE]
> La directiva de **Restricciones de acceso del usuario invitado** en Azure Active Directory (Azure AD) determina los permisos de cada invitado en su directorio. Existen tres opciones de directiva.
>  - La configuración **Los usuarios invitados tienen el mismo acceso que los miembros (más inclusiva)** significa que los invitados tienen el mismo acceso a los datos del directorio como los usuarios habituales del directorio.
>  - La configuración **Los usuarios invitados tienen acceso limitado a las propiedades y la pertenencia a los objetos de directorio** significa que los invitados no tienen permisos para determinadas tareas de directorio, como la enumeración de usuarios, grupos u otros recursos de directorio con Microsoft Graph.
>  - La configuración **El acceso de usuarios invitados está restringido a las propiedades y la pertenencia a sus propios objetos de directorio (más restrictiva)** significa que los invitados solo puedan tener acceso a sus propios objetos de directorio.
>
>Para obtener más información, vea [¿Cuáles son los permisos de usuario predeterminados en Azure Active Directory?](/azure/active-directory/fundamentals/users-default-permissions)

## <a name="related-topics"></a>Temas relacionados

[Abandonar una organización como invitado](/azure/active-directory/b2b/leave-the-organization)
