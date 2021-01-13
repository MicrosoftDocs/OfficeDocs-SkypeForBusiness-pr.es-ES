---
title: Actualizar lista de comprobación| Actualización de Skype Empresarial a Teams | Pasos básicos
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Siga este plan de acción acelerada de diez pasos para pasar de una configuración básica de Skype Empresarial a la configuración de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- seo-marvel-apr2020
- Teams-upgrade-guidance
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-in
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37cc9f3940eb08a4df092042c016b194b01c64e6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809090"
---
# <a name="upgrade-basic"></a>Actualización básica

<a name="about-upgrade-basic"></a>

Diseñada para organizaciones más pequeñas o que usan Skype Empresarial Online solo para mensajería instantánea (chat) y reuniones, la lista de comprobación de Upgrade Basic es un plan de acción acelerada que incluye actividades básicas, recomendaciones y recursos asociados para implementar correctamente un cambio de Skype Empresarial a Teams.

Estos diez sencillos pasos proporcionan todo lo que necesita para una actualización correcta. Están diseñados para completarse en aproximadamente 30 a 45 días, pero debe ajustar las fechas de finalización de las tareas según la programación de actualización de su organización.

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021. Transcurrido ese tiempo, el servicio de Skype Empresarial Online ya no será accesible ni compatible. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams.

¿Qué le pasa a Skype Empresarial después de la actualización? Después de la actualización de los usuarios a Teams (modo **solo Teams**):

- El cliente de Skype Empresarial está deshabilitado y todas las llamadas y chats van a Teams. Tenga en cuenta que esto no desinstalará el cliente en sus escritorios.
- Todas las reuniones de Skype Empresarial que se programaron antes de la actualización funcionan según lo previsto, pero todas las reuniones nuevas se programan en Teams. El complemento de Skype Empresarial ya no estará disponible en Outlook. 
- Si los usuarios intentan iniciar sesión en Skype Empresarial, el cliente les envía una notificación de que se les ha actualizado a Teams.
- Los usuarios necesitan desinstalar manualmente el cliente de Skype Empresarial en sus dispositivos móviles.

Consulta nuestras [preguntas más](https://aka.ms/SkypeToTeams-FAQ) frecuentes para preguntas adicionales sobre la actualización.

¿No está familiarizado con Teams? [Obtenga](https://products.office.com/microsoft-teams/group-chat-software) información sobre cómo Teams reúne conversaciones, reuniones, archivos, aplicaciones de Office e integraciones de terceros, proporcionando un único hub para el trabajo en equipo en Microsoft 365 y Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Paso 1. Notificar a las principales partes interesadas

*(Aproximadamente, de cuatro a seis semanas antes de la actualización)*

Los líderes sénior son responsables del éxito de la empresa; asegúrese de mantenerlos al día sobre los cambios tecnológicos. Como es posible que no todos los usuarios reciban o lean la notificación de idoneidad para la actualización, debe informar a las partes interesadas (por ejemplo, el director general, los profesionales de TI, el departamento de marketing y los responsables del departamento de soporte técnico) antes de empezar a planear la actualización.

**Recursos:**

- [Correo electrónico de ejemplo: comunicación entre partes interesadas](upgrade-emails-surveys.md#step-1-email)

[Volver al principio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Paso 2. Prepare a su organización para Teams

*(Aproximadamente, de cuatro a seis semanas antes de la actualización)*

Teams ofrece funciones compatibles con Skype Empresarial, como mensajería instantánea (chat) y reuniones, pero también puede hacer mucho más. Como un verdadero centro para el trabajo en equipo, Teams permite a los grupos de trabajo administrar proyectos, archivos, conversaciones y aplicaciones en una única ubicación. De forma predeterminada, Teams está activado para todas las organizaciones. Decida cómo su organización usará Teams y configurará su entorno para el éxito. 

> [!Note]
> Como cliente existente de Skype Empresarial, es probable que su infraestructura de red actual ya esté configurada para Teams. Para confirmar esto, puede seguir las instrucciones de "Planeación técnica completa" vinculadas a continuación (esto es opcional).

**Recursos:**

- [Información general sobre Microsoft Teams](Teams-overview.md)
- [Introducción a Microsoft Teams](get-started-with-teams-quick-start.md)

[Volver al principio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Paso 3. Conocer a los usuarios de Skype Empresarial

*(Aproximadamente cuatro semanas antes de la actualización)*

Es posible que los usuarios profundamente adoptados en Skype Empresarial necesiten algo más de tiempo o asistencia para realizar el cambio a Teams. Dedíme tiempo a revisar el uso actual de Skype Empresarial para identificar los usuarios principales que necesitan soporte técnico adicional y establecer una línea base de uso de la que pueda hacer un seguimiento con los números posteriores a la actualización.

**Recursos:**

- [Informes de Microsoft 365 en el centro de administración](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports)

[Volver al principio](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Paso 4. Notificar a los usuarios que actualizarán de Skype Empresarial a Teams

*(Aproximadamente dos o tres semanas antes de la actualización)*

Si proporciona suficiente aviso a sus usuarios, tendrá tiempo para familiarizarse con Teams sin afectar negativamente a su productividad, lo que resulta en una experiencia de usuario más positiva. Envíe una comunicación para decirles lo que cambia, por qué cambia y cómo pueden prepararse para ello.

> [!Note]
> Si es necesario, puede habilitar Teams para sus usuarios a través del Centro de administración de Microsoft 365 en este momento.

**Recursos:**

- [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md)
- [Correo electrónico de ejemplo: anuncio para los usuarios sobre Skype Empresarial](upgrade-emails-surveys.md#step-4-email)

[Volver al principio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Paso 5. Activar la notificación de actualización de usuario

*(Aproximadamente una semana antes de la actualización)*

Mantenga el impulso de la actualización habilitando la notificación de actualización de usuario a través del portal de administración, proporcionando una alerta visual en el cliente de Skype Empresarial de que los usuarios se están actualizando de Skype Empresarial a Teams.

**Recursos:**

- [Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Volver al principio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Paso 6. Recuerde a los usuarios que actualizarán de Skype Empresarial a Teams

*(Aproximadamente cinco días antes de la actualización)*

Los usuarios están ocupados con sus responsabilidades diarias. Recordarles la actualización pendiente le ayudará a garantizar que recuerden seguir los pasos que necesitan para prepararse para Teams. Este es el momento perfecto para recordar a los usuarios los aprendizajes disponibles y cómo empezar a usar Teams.

**Recursos:**

- [Correo electrónico de ejemplo: recordar a los usuarios que deben empezar a usar Teams](upgrade-emails-surveys.md#step-6-email)

[Volver al principio](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Paso 7. Actualice a los usuarios a Teams.

*(Upgrade Day)*

Hoy es el día en que su organización actualiza oficialmente a Teams como solución de comunicación y colaboración. En el Centro de administración de Microsoft Teams, active el cambio de actualización estableciendo el modo de coexistencia en **Solo equipos.** (En el centro de administración, ve a **Configuración para toda la organización**  >  **Actualización de Teams.** Los usuarios recibirán una notificación en su cliente de Skype Empresarial de que se les ha actualizado a Teams.

Le recomendamos que, después de actualizar a todos los usuarios, envíe un correo electrónico para darles la bienvenida a Teams.

**Recursos:**

- [Establecer configuración de actualización y coexistencia](setting-your-coexistence-and-upgrade-settings.md)
- [Correo electrónico de ejemplo: dar la bienvenida a los usuarios a Teams](upgrade-emails-surveys.md#step-7-email)

[Volver al principio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Paso 8. Supervisar el uso de Teams con la línea base

*(Aproximadamente una o dos semanas después de la actualización)*

Ajustarse a una nueva tecnología puede llevar algún tiempo. Compruebe el uso para comprobar que los usuarios usan Teams al mismo nivel (o superior) que con Skype Empresarial. Consulte a los usuarios que no están usando Teams en los niveles esperados.

**Recursos:**

- [Ver datos de uso](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Volver al principio](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Paso 9. Medir la satisfacción del usuario

*(Aproximadamente una o dos semanas después de la actualización)*

La satisfacción de los empleados puede influir en la productividad, la retención y, en última instancia, los resultados empresariales. Llegue a los usuarios para medir la opinión de los usuarios sobre la actualización y su satisfacción con Teams.

**Recursos:**

- [Correo electrónico de ejemplo: consulte a los usuarios y](upgrade-emails-surveys.md#step-9-email)las [encuestas de usuario](upgrade-emails-surveys.md#step-9-surveys)

[Volver al principio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Paso 10. Maximice su ROI con Teams

*(En curso)*

Una vez que los usuarios se sientan cómodos con la mensajería instantánea (chat) y las reuniones en Teams, anímelos a ampliar su caso de uso usando la colaboración de Teams y la integración de las aplicaciones, optimizando de verdad sus nuevas soluciones y maximizando un retorno de su inversión.

**Recursos:**

- [Correo electrónico de ejemplo: anime a los usuarios a explorar Teams aún más](upgrade-emails-surveys.md#step-10-email)

[Volver al principio](#about-upgrade-basic)
