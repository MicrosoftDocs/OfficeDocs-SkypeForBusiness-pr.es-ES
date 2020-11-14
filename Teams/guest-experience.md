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
description: En este artículo se describe la funcionalidad de Microsoft Teams disponible para los invitados.
ms.openlocfilehash: a2c4bcf380eb90f7c0a00c8f6f4f9141b80f8460
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030296"
---
# <a name="guest-experience-in-teams"></a>Experiencia de invitado en Teams

Cuando se invita a un invitado a unirse a un equipo, recibe un mensaje de correo electrónico de bienvenida. Este mensaje incluye cierta información sobre el equipo y qué esperar ahora que sea miembro. El invitado debe aceptar la invitación seleccionando **Abrir Microsoft Teams** en el mensaje de correo electrónico para que puedan acceder al equipo y a sus canales.
    
![Captura de pantalla que muestra un ejemplo de un mensaje de correo electrónico de bienvenida](media/guest-experience-image1.png)
    
Todos los miembros del equipo ven un mensaje en el hilo del canal en el que se anuncia que el propietario del equipo ha agregado a un invitado y da el nombre del invitado. Todos los miembros del equipo pueden identificar con facilidad quién es un invitado. Una etiqueta en la esquina superior derecha del subproceso de canal indica el número de invitados en el equipo y aparece una etiqueta **(invitado)** junto al nombre de cada invitado.

![Captura de pantalla que muestra una etiqueta que indica el número de invitados en el equipo](media/guest-experience-image2.png)

Consulte estos vídeos sobre la experiencia de invitado en Teams:
- [Unirse a un equipo como invitado](https://support.office.com/article/join-a-team-as-a-guest-928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Unirse a una reunión de equipos con invitados](https://support.office.com/article/join-a-company-meeting-a120c282-063d-46b8-b973-851197ab75d8)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Comparación de las capacidades de miembro de equipo y de invitado

En la siguiente tabla se compara la funcionalidad de Teams disponible para los miembros del equipo de una organización y sus invitados. Los administradores de equipos controlan las características disponibles para los invitados.

|**Funcionalidad en Microsoft Teams**|**Usuario de Microsoft Teams de la organización**|**Usuario invitado**|
|:-----|:-----|:-----|
|Crear un canal  <br/>  *Los propietarios del equipo controlan este parámetro.*  <br/> |&#x2713;|&#x2713;|
|Participar en un chat privado  <br/> |&#x2713;|&#x2713;|
|Participar en una conversión del canal  <br/> |&#x2713;|&#x2713;|
|Publicar, eliminar y editar mensajes  <br/> |&#x2713;|&#x2713;|
|Compartir un archivo del canal  <br/> |&#x2713;|&#x2713;|
|Obtener acceso a archivos de SharePoint<br/> |&#x2713;|&#x2713;|
|Adjuntar archivos<br/> |&#x2713;|&#x2713;|
|Descargar archivos de conversaciones privadas<br/> |&#x2713;|&#x2713;|
|Buscar en archivos<br/> |&#x2713;||
|Compartir un archivo del chat  <br/> |&#x2713;||
|Agregar aplicaciones (fichas, bots o conectores)  <br/> |&#x2713;||
|Crear reuniones o programaciones de Access  <br/> |&#x2713;||
|Obtener acceso al almacenamiento de OneDrive para la empresa  <br/> |&#x2713;||
|Crear directivas de acceso de invitados a equipos y canales para todos los inquilinos  <br/> |&#x2713;||
|Invitar a un usuario fuera del dominio de la organización de Microsoft 365 o de Office 365 <br/>  *Los propietarios del equipo controlan este parámetro.*  <br/> <br/> |&#x2713;||
|Crear un equipo  <br/> |&#x2713;||
|Descubrir un equipo público y unirse a él  <br/> |&#x2713;||
|Ver el organigrama  <br/> |&#x2713;||
|Usar traducción en línea  <br/> |&#x2713;||
|Convertirse en propietario del equipo  <br/> |&#x2713;||

En la tabla siguiente se muestran las características de llamadas y reuniones disponibles para los invitados, en comparación con otros tipos de usuarios.

| Característica de llamadas | Invitado | Usuario E1 y E3 | E5 y usuarios de la telefonía IP empresarial |
| --------------- | ----- | -------------- | -------------- |
| Llamadas VOIP | Sí | Sí | Sí |
| Llamadas grupales | Sí | Sí | Sí |
| Controles de llamadas principales compatibles (mantener, silenciar, activar o desactivar vídeo, pantalla compartida) | Sí | Sí | Sí |
| Transferir destino | Sí | Sí | Sí |
| Puede transferir una llamada | Sí | Sí | Sí |
| Permite la transferencia de asesoría | Sí | Sí | Sí |
| Puede agregar otros usuarios a una llamada a través de VOIP | Sí | Sí | Sí |
| Puede añadir usuarios por número de teléfono a una llamada | No | No | Sí |
| Destino de reenvío | No | Sí | Sí |
| Destino del grupo de llamadas | No | Sí | Sí |
| Objetivo sin contestar | No | Sí | Sí |
| Puede ser el objetivo de una llamada federada | No | Sí | Sí |
| Puede hacer una llamada federada | No | Sí | Sí |
| Puede desviar sus llamadas inmediatamente | No | No | Sí |
| Puede llamar simultáneamente a sus llamadas | No | No | Sí |
| Puede enrutar las llamadas no contestadas | No | No | Sí |
| Las llamadas perdidas pueden ir al buzón de voz | No | No<sup>1</sup> |Sí |
| Tener un número de teléfono que pueda recibir llamadas | No | No | Sí |
| Puede marcar números de teléfono | No | No | Sí |
| Puede acceder a la configuración de llamadas | No | No | Sí |
| Puede cambiar el saludo del buzón de voz | No | No<sup>1</sup> | Sí |
| Puede cambiar los tonos de timbre | No | No  | Sí |
| Compatible con TTY | No | No | Sí |
| Puede tener delegados | No | No | Sí |
|  Puede ser un delegado | No | No | Sí |

<sup>1</sup> esta característica estará disponible próximamente.

> [!NOTE]
> La Directiva de **restricciones de acceso de usuario invitado** en Azure Active Directory (Azure ad) determina los permisos para los invitados de su directorio. Existen tres opciones de directiva.
>  - La configuración **Los usuarios invitados tienen el mismo acceso que los miembros (más inclusiva)** significa que los invitados tienen el mismo acceso a los datos del directorio como los usuarios habituales del directorio.
>  - La configuración **Los usuarios invitados tienen acceso limitado a las propiedades y la pertenencia a los objetos de directorio** significa que los invitados no tienen permisos para determinadas tareas de directorio, como la enumeración de usuarios, grupos u otros recursos de directorio con Microsoft Graph.
>  - La configuración **El acceso de usuarios invitados está restringido a las propiedades y la pertenencia a sus propios objetos de directorio (más restrictiva)** significa que los invitados solo puedan tener acceso a sus propios objetos de directorio.
>
>Para obtener más información, vea [¿Cuáles son los permisos de usuario predeterminados en Azure Active Directory?](https://go.microsoft.com/fwlink/?linkid=2135493)

## <a name="related-topics"></a>Temas relacionados

[Abandonar una organización como usuario invitado](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization)
