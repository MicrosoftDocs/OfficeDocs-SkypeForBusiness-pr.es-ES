---
title: Problemas conocidos de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.custom: seo-marvel-mar2020
ms.reviewer: marcl
audience: admin
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: Use esta lista de problemas conocidos en la aplicación cliente de Microsoft Teams y en la experiencia de los administradores para solucionar problemas en la organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1343317d29f196caf151ead5a6429fb3edf19d87
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902305"
---
# <a name="known-issues-for-microsoft-teams"></a>Problemas conocidos de Microsoft Teams

En este artículo se indican los problemas conocidos de Microsoft Teams por área de características.

## <a name="common-issues-and-resolutions"></a>Problemas conocidos y resolución

> [!NOTE]
> Si necesita ayuda para implementar Teams para admitir a los trabajadores remotos (WFH) debido a COVID-19, consulte [Soporte técnico para trabajadores remotos con Teams](support-remote-work-with-teams.md). También puede optar por la ayuda de implementación del programa Microsoft 365 FastTrack; visite el [Centro de FastTrack](https://www.microsoft.com/fasttrack) para enviar una solicitud.

### <a name="for-all-teams-customers"></a>Para todos los clientes de Teams

| |  |
|---------|---------|
|**¿Es nuevo en Teams?**    |Consulte [Introducción a Microsoft Teams](get-started-with-teams-quick-start.md).         |
|**Habilitar el acceso de invitado a Teams**     |Revise la [Lista de comprobación de acceso para invitados de Teams](guest-access-checklist.md) y asegúrese de que se han completado todos los pasos. Consulte los siguientes recursos adicionales:<ul><li>[Comprender el acceso de invitado de Microsoft Teams](guest-access.md)</li>[Cómo se une un invitado a un Equipo](guest-joins.md) <li>[Configuración de la lista de comprobación para el acceso de invitado de Microsoft Teams](guest-access-checklist.md)</li></ul>|
|**Reuniones y acceso telefónico de Teams**    |¿Necesita ayuda para activar o configurar las audioconferencias en Teams? ¿Se ha creado este usuario recientemente? Si es así, tendrá que esperar entre 2 y 24 horas **para que la configuración se aplique**.<br>Para comprobar que el usuario tiene licencia para las audioconferencias y un número de pago predeterminado:<br><ol><li>En el Centro de administración de Microsoft 365, vaya a **Usuarios activos** y seleccione el usuario en cuestión.</li><li> Según la versión del centro de administración, elija **Licencias y aplicaciones** o haga clic en **Editar**, en **Licencias de producto**.</li><li> Confirme que el usuario tiene licencias seleccionadas para Audioconferencia, Microsoft Teams y Skype Empresarial Online (Plan 2).</li><li>En **Centros de administración**, haga clic en **Mostrar todo** y luego en **Teams**.</li><li>En el Centro de administración de Microsoft Teams, haga clic en **Portal heredado**.</li><li>En el Centro de administración de Skype Empresarial, haga clic en **audioconferencia** y luego en **usuarios**.</li><li>Seleccione el usuario en cuestión y compruebe que tiene un número de teléfono de pago predeterminado.</li> </ol> Para obtener más información, vea [Planes de llamadas para Office 365](calling-plans-for-office-365.md) o llame al Equipo de facturación comercial de Microsoft Commerce para preguntas relacionadas con las licencias. <br><br>Recursos adicionales:<ul><li>[Reuniones y conferencias en Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md)</li><li>[Audioconferencia en Office 365](audio-conferencing-in-office-365.md)</li></ul>       |
|**Licencia de Teams Exploratory**     |La experiencia de Microsoft Teams Exploratory permite a los usuarios de su organización que tienen Azure Active Directory (AAD) y a los que no tienen licencia para Teams activar una experiencia de Teams Exploratory Los administradores pueden activar o desactivar esta característica para los usuarios de su organización. La anterior [oferta de prueba comercial en la nube de Microsoft](iw-trial-teams.md) se ha reemplazado por la experiencia exploratoria de Teams. <br><br>Recursos adicionales:<ul><li>[¿Cómo pueden los usuarios inscribirse en la experiencia de Teams Exploratory?](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Administrar la experiencia de Teams Exploratory](teams-exploratory.md#manage-the-teams-exploratory-experience)</li></ul>|
|**Canales privados**    |Los canales privados de Microsoft Teams crean espacios prioritarios para la colaboración de los equipos. Solo los usuarios del equipo que sean propietarios o miembros del canal privado podrán acceder al canal. Cualquier persona, incluidos los invitados, puede agregarse como miembro de un canal privado siempre y cuando ya sean miembros del equipo.<br><br>Un canal privado puede ser útil para limitar la colaboración a solo aquellos usuarios que necesitan conocer una información o para facilitar la comunicación entre un grupo de personas asignadas a un proyecto específico, sin tener que crear un equipo adicional para administrar.<br><br>Recursos adicionales:<ul><li>[¿Cómo pueden los usuarios inscribirse en la experiencia de Teams Exploratory?](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Administrar la experiencia de Teams Exploratory](teams-exploratory.md#manage-the-teams-exploratory-experience)</li><ul>        |
|**Directivas de reunión**|Las [Directivas de reunión](meeting-policies-in-teams.md) se usan para controlar las características disponibles para sus participantes en reuniones programadas por usuarios de la organización. Después de crear una directiva y realizar los cambios, puede asignar usuarios a la directiva.         |
||**Cambiar o crear una directiva de reunión**<br><br>Para cambiar o crear una directiva de reunión, vaya al Centro de administración de Microsoft Teams > **Reuniones** > **Directivas de reunión**. Seleccione una directiva de la lista o seleccione **Agregar**. Si está creando una nueva directiva, agregue un nombre y una descripción. El nombre no puede contener caracteres especiales ni tener más de 64 caracteres. Elija la configuración y, después, haga clic en **Guardar**. Por ejemplo, supongamos que tiene un grupo de usuarios y quiere limitar el ancho de banda que necesitaría la reunión. Cree una nueva directiva personalizada denominada "ancho de banda limitado" y deshabilite las opciones siguientes:<br><br>En **Audio y vídeo**:<ul><li>Desactive Permitir la grabación en la nube.</li><li>Desactive Permitir vídeo IP.</li></ul>En **Uso compartido de contenido**:<ul><li>Desactive el modo de uso compartido de la pantalla.</li><li>Desactive Permitir pizarra.</li><li>Desactive Permitir notas compartidas.</li></ul>Luego asigne la directiva a los usuarios:         |
| |**Asignar una directiva de reunión a los usuarios**<br><br><ol><li>En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</li><li>Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.</li><li>En **Directiva de reunión**, seleccione la directiva que quiera asignar y haga clic en **Aplicar**.</li></ol>Para asignar una directiva a varios usuarios a la vez, vea [Modificar la configuración de usuario de Teams en masa](edit-user-settings-in-bulk.md). Puede hacer lo siguiente:<ol><li>En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Reuniones > Directivas de reunión**.</li><li>Haga clic a la izquierda del nombre de la directiva para seleccionarla.</li><li>Seleccione **Administrar usuarios**.</li><li>En el panel **Administrar usuarios**, busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.</li><li>Cuando termine de agregar usuarios, haga clic en **Guardar**.</li>         |
|**Solución de problemas de un teclado de marcado ausente**     |Haga lo siguiente: <ul><li>Asegúrese de que el usuario tiene una [licencia de Teams](assign-teams-licenses.md) asignada.</li><li>Asegúrese de que el usuario tiene un [Plan de llamadas](calling-plan-landing-page.md) asignado.</li><li>Habilite al usuario para [Telefonía IP empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-enterprise-voice-online-and-phone-system-voicemail#to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail).</li></ul>      |
|**Solución de problemas de inicio de sesión de Teams**   |En primer lugar, asegúrese de que el [Servicio de Microsoft Teams está en buen estado](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/servicehealth). Después, compruebe si hay códigos de error comunes y revise [¿Por qué tengo problemas para iniciar sesión en Microsoft Teams?](https://support.office.com/article/a02f683b-61a3-4008-9447-ee60c5593b0f)  Es posible que también tenga que revisar [Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).         |

### <a name="for-education-customers"></a>Para los clientes de educación

|||
|---------|---------|
|Sus usuarios ven un mensaje de "¡Se está perdiendo muchas cosas!" mensaje.   |Asegúrese de [Habilitar Microsoft Teams para su escuela](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams). En los inquilinos de EDU, Teams no está habilitado por defecto; tendrá que activarlo primero. <br><br>Para obtener ayuda con las clases de Teams, consulte [Formación y aprendizaje remotos en Office 365 Educación](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4) donde obtendrá la información más reciente sobre cómo configurar el centro educativo, la planificación de lecciones, las reuniones virtuales y cómo compartir contenido con los alumnos.<br><br>Por último, asegúrese de consultar los vídeos y las cartas de aprendizaje y otros elementos de Microsoft Teams para administradores de TI en [Formación de administradores para Teams](itadmin-readiness.md).        |

Vea el [Solucionador de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) para obtener más información sobre la resolución de problemas en Microsoft Teams.
