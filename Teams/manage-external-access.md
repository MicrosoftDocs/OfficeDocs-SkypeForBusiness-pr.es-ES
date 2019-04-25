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
description: El Administrador de TI puede configurar el acceso externo para otros dominios (federación) permitir que los usuarios de esos dominios a participar en los equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b04b125f5cb998c71f161bf31809a39097accf6c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245588"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>Administrar el acceso externo (federación) en Microsoft Teams
======================================================

Con acceso externo de Microsoft Teams, los usuarios de otros dominios pueden participar en las charlas y las llamadas. También puede permitir que a los usuarios externos que todavía se están usando Skype para la empresa para participar. 

Acceso externo (federación) y el acceso de invitado son diferentes:

- Acceso de invitado concede permiso de acceso a un individuo. Acceso externo concede permiso de acceso a todo el dominio.

- Acceso como invitado, una vez concedido por el propietario de un equipo, permite que a un invitado para [tener acceso a recursos](guest-experience.md), como discusiones de canal y archivos, para un equipo específico y chat con otros usuarios en el equipo que hayan sido invitados a. Con acceso externo (chat federado), los participantes externos chat no tienen acceso a la organización invitar a los equipos o recursos de equipo. Solo pueden participar en conversaciones federadas proporcionó en. Los administradores de inquilinos pueden elegir entre las opciones de dos comunicación dependiendo de qué nivel de colaboración es deseable con la parte externa. Pueden elegir los administradores enfoques o ambos, dependiendo de sus necesidades de la organización, pero se recomienda habilitar el acceso de invitado para una experiencia de los equipos más completo y en colaboración. 

Vea la siguiente tabla para obtener una comparación de externo y acceso a las características de invitado.

| Característica | Usuarios de acceso externo | Usuarios de acceso de invitado |
|---------|-----------------------|--------------------|
| Usuario puede hablar con una persona de otra empresa | Sí |Sí |
| Usuario puede llamar a alguien de otra compañía | Sí | Sí |
| Usuario puede ver si una persona de otra empresa está disponible para la llamada o chat | Sí | Sí<sup>1</sup> |
| Puede buscar usuario para los usuarios en los inquilinos externos | Sí<sup>2</sup> | No |
| Usuario puede compartir archivos | No | Sí |
| Usuario puede tener acceso a los recursos de los equipos | No | Sí |
| Usuario puede agregarse a una conversación en grupo | No | Sí |
| Se puede agregar el usuario a una reunión | Sí | Sí |
| Se pueden agregar usuarios adicionales a una conversación con un usuario externo | No hay<sup>3</sup> | N/D |
| Usuario se identifica como una parte externa | Sí | Sí |
| Se muestra la presencia | Sí | Sí |
| Fuera de la oficina se muestra el mensaje | No | Sí |
| Se puede bloquear un usuario individual | No | Sí |
| se admiten @mentions | No | Sí |
||||

<sup>1</sup> siempre que el usuario se ha agregado como invitado y ha iniciado sesión como invitado en el inquilino de invitado.<br>
<sup>2</sup> sólo por correo electrónico o la dirección de protocolo de inicio de sesión (SIP).<br>
<sup>3</sup> externo chat (federada) es sólo 1:1.

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a>Activar o desactivar el acceso externo (los usuarios pueden comunicarse con Skype para profesionales y los equipos de los usuarios)

Puede usar el & Teams Microsoft Skype para el centro de administración de negocio para administrar el acceso externo.

1. En la & Teams Microsoft Skype para el centro de administración de negocio, seleccione **configuración de toda la organización** > **acceso externo**.

     ![Captura de pantalla de acceso externo de la configuración de toda la organización](media/manage-external-access-1.png).

2. Permite activar o desactivar el cambio de **los usuarios pueden comunicarse con Skype para profesionales y los equipos de los usuarios** a **activado** o **desactivado**.

     ![Captura de pantalla del modificador de acceso externo activado](media/manage-external-access-2.png).

3. Haga clic en **Guardar **. 

## <a name="add-or-block-a-domain"></a>Agregar o bloquear un dominio

Siga estos pasos para agregar un dominio o desactivar el acceso externo para un dominio.

1. En la & Teams Microsoft Skype para el centro de administración de negocio, seleccione **configuración de toda la organización** > **acceso externo**.

2. Seleccione **Agregar un dominio**. 
 
    ![Captura de pantalla de externos página de acceso con agregar un vínculo de dominio](media/manage-external-access-3.png).

   Aparece el panel **Agregar un dominio** .

    ![Captura de pantalla de agregar un panel de dominio](media/manage-external-access-4.png).


3. En **Agregar un dominio**, escriba el nombre del dominio; Por ejemplo, escriba Contoso.com.

4. Seleccione **Permitido** o **Bloqueado**. Puede cambiar esta configuración en cualquier momento.

2. Seleccione **Listo**.

Después de agregar un dominio, podrá ver el nombre de dominio y el estado que se agrega a la lista de dominios en la página de acceso externo.

## <a name="more-information"></a>Más información

Para obtener información sobre el acceso de invitado en Microsoft Teams, vea [administrar el acceso de invitado en los equipos de Microsoft](manage-guests.md).