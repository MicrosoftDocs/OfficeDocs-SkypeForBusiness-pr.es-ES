---
title: 'Configurar las opciones de Audioconferencia: Microsoft Teams'
ms.reviewer: ''
description: Use estos recursos de implementación para ayudarle a implementar la audioconferencia como parte de la carga de trabajo de reuniones en Microsoft Teams.
ms.topic: article
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7fafebf61cdf7e5b13cfbb6aaf08d73afef6f436
ms.sourcegitcommit: 50ae550b738424b35df1636590831e6c124ca0c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2022
ms.locfileid: "68576446"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a>Más información sobre cómo implementar Audioconferencia en Microsoft Teams

La audioconferencia es la posibilidad de unirse a una reunión de Teams desde un teléfono normal y llamar desde una reunión a un número de teléfono. Asegúrese de revisar [Implementación reuniones](deploy-meetings-microsoft-teams-landing-page.md) como parte de la implementación de las audioconferencias en su organización.

## <a name="audio-conferencing-deployment-decisions"></a>Decisiones sobre la implementación de audioconferencias

Este artículo le ayudará a decidir si cambiar alguna opción de la configuración predeterminada de audioconferencias, en función del perfil y los requisitos empresariales de su organización, después le guiará con cada cambio. Hemos dividido las opciones en dos grupos, comenzando por el conjunto principal de [cambios que es más probable que realice](#core-deployment-decisions). El segundo grupo incluye las [opciones adicionales](#additional-deployment-decisions) que puede que quiera configurar, según las necesidades de su organización.

Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones. Los asistentes que se conectan por teléfono a la reunión no necesitan tener asignada ninguna licencia ni otra configuración. Llamar (llamar) a las reuniones es muy útil para los usuarios que se encuentran en la carretera y no pueden asistir a una reunión con la aplicación Teams en sus portátiles o dispositivos móviles.

## <a name="audio-conferencing-prerequisites"></a>Requisitos previos para las audioconferencias

Antes de que pueda implementar audioconferencias para Teams, tenga en cuenta lo siguiente:

|Pregúntese lo siguiente:|Action |
|------------|-------|
|¿Está disponible la audioconferencia para mi país o región?|Para averiguar si la audioconferencia está disponible en su país o región, vea [Disponibilidad de país y región para las audioconferencias y los planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).|
|¿Tienen los usuarios la licencia adecuada para las audioconferencias de Teams?|Las licencias de audioconferencia están disponibles como parte de la suscripción de Microsoft 365 y Office 365 E5, o como servicio complementario para los planes de suscripción de Microsoft 365 Empresa Estándar, E1 o E3. <ul><li>Para obtener y asignar licencias, consulte [Asignar o quitar licencias de Aplicaciones Microsoft 365 para negocios](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</li><li> Para obtener más información, lea las [Licencias de complementos de Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md). </li><li>Para ver las características de la nube que se incluyen en cada plan, vea los artículos [Opciones de licencia basadas en su plan](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</li></ul>|
|¿Necesito comprar créditos de comunicaciones para los usuarios a los que se asignan las licencias de audioconferencias?|Para obtener más información, lea [¿Qué son los Créditos de comunicaciones?](what-are-communications-credits.md) y consulte la sección [Créditos de comunicaciones](#communications-credits) a continuación.|
|||

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Una vez que cumpla con los requisitos previos de las audioconferencias, realice las tareas siguientes para configurar las audioconferencias para los usuarios.

### <a name="teams-administrators"></a>Administradores de Teams

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿A quién se asignará el rol de Administrador de comunicaciones de Teams?|Para obtener más información sobre los roles de administrador de Teams, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md).|
|¿A quién se asignará el rol de Ingeniero de soporte en comunicaciones de Teams?|Para asignar roles de administrador, vea [asignar roles de administrador y de no administrador a los usuarios con Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|¿A quién se asignará el rol de Especialista de soporte en comunicaciones de Teams?||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>Puentes de conferencia y números de teléfono

Conferencing bridges let people dial into meetings using a phone. You can use the default settings for a conferencing bridge or change the phone numbers (toll and toll-free) and other settings, such as the PIN or the languages that are used.

Vea [Audioconferencias](audio-conferencing-in-office-365.md) para obtener más información.

|Pregúntese lo siguiente:|Action |
|------------|-------|
|¿Necesito agregar nuevos números de puente de conferencias?| Para agregar nuevos números, vea [Obtener números de teléfono del servicio](./getting-service-phone-numbers.md).|
|¿Necesito modificar la configuración del puente?|Para modificar la configuración del puente, vea [Cambiar la configuración de un puente de audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).|
|¿Necesito hacer portabilidad de los números para usarlos con audioconferencia?|Para obtener información sobre la portabilidad de números de teléfono, lea [Transferir números de teléfono a Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).|
|||

### <a name="default-and-alternate-languages"></a>Idioma predeterminados y alternativos

Las audioconferencias de Teams le permiten configurar idiomas predeterminados y alternativos para un puente de conferencias.

|Pregúntese lo siguiente:|Action |
|------------|-------|
| ¿Qué idiomas debo elegir para los saludos del operador automático? | Para elegir idiomas, consulte [Establecer los idiomas del operador automático para audioconferencia en Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).|
|||

### <a name="conferencing-bridge-settings"></a>Configuración de puente de conferencias

After setting up your conferencing bridge, including default and alternate languages, you should verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use. If they're not, you can change them.

|Pregúntese lo siguiente:|Action |
|------------|-------|
| ¿Los asistentes escucharán una notificación cuando un usuario se una o salga de una reunión? | Para cambiar esta configuración, vea [Cambiar la configuración de un puente de audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).|
|¿Cuál es la longitud mínima del PIN que usa un organizador para iniciar la reunión?||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>Configuración de número de teléfono de acceso telefónico para los usuarios que dirigen reuniones

Después de crear el puente de audioconferencias, debe configurar los números de pago o gratuitos que usarán los usuarios que dirigen las reuniones.

|Pregúntese lo siguiente:|Action |
|------------|-------|
| ¿Qué números de puente de conferencias voy a asignar a cada usuario que dirija reuniones? | Para asignar un número de teléfono de acceso telefónico a un usuario, vea [Paso 7: Asignar números de teléfono de acceso telefónico para los usuarios que dirigen reuniones](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings). |
|||

### <a name="communications-credits"></a>Créditos de comunicaciones

Para proporcionar números de teléfono gratuitos para puentes de conferencia y admitir las conferencias por aceptación de llamada de números de teléfono internacionales, tendrá que configurar Créditos de comunicaciones para su organización. Obtenga más información sobre los Créditos de comunicaciones en [¿Que son los Créditos de comunicaciones?](what-are-communications-credits.md)

|Pregúntese lo siguiente:|Action |
|------------|-------|
|¿Son necesarios los Créditos de comunicaciones para la implementación de audioconferencias? |Para saber si necesita configurar Créditos de comunicaciones, consulte [Configurar Créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).|
|Si son necesarios, ¿cuántos debería comprar?|Para determinar la cantidad de Créditos de comunicaciones, vea [Cantidad de fondos recomendada](what-are-communications-credits.md#recommended-funding-amounts).|
|¿Me interesa configurar una cantidad de recarga automática?|Para configurar una cantidad de recarga automática, vea [Configurar Créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).|
|||

## <a name="additional-deployment-decisions"></a>Decisiones de implementación adicionales

Puede que le interese cambiar esta configuración en función de las necesidades y la configuración de su organización.

### <a name="outbound-calling-restriction-policies"></a>Directivas de restricción de llamadas salientes

Como administrador, puede usar los controles de llamadas salientes para restringir el tipo de audioconferencias y llamadas RTC del usuario final que pueden realizar los usuarios de su organización.

|Pregúntese lo siguiente:|Action |
|------------|-------|
| ¿Voy a limitar el tipo de llamadas salientes permitidas? | Para restringir las llamadas, consulte [Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario](outbound-calling-restriction-policies.md)|
|||

### <a name="dial-plans"></a>Planes de marcado

Un plan de marcado, una característica del Sistema telefónico de Microsoft 365 u Office 365, es un conjunto de reglas de normalización con las que los números de teléfono que se marcan se traducen a un formato alternativo (normalmente, el formato E.164) para poder autorizar la llamada y enrutarla.

Para obtener más información acerca de los planes de marcado, vea [¿Qué son los planes de marcado?](what-are-dial-plans.md).

|Pregúntese lo siguiente:|Action |
|------------|-------|
|¿Mi organización necesita un plan de marcado personalizado?|Para obtener ayuda para determinar si necesita un plan de marcado personalizado, vea [Planificar planes de marcado del espacio empresarial](what-are-dial-plans.md#planning-for-tenant-dial-plans). |
|¿Qué usuarios necesitan un plan de marcado personalizado y qué plan de marcado del espacio empresarial se va a asignar a cada usuario?|Para agregar usuarios a un plan de marcado personalizado con PowerShell, vea [Crear y administrar planes de marcado](create-and-manage-dial-plans.md).|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Solucionar problemas de calidad de las reuniones y llamadas

Teams ofrece dos formas para supervisar y solucionar problemas de calidad de llamadas: [Análisis de llamadas y Panel de calidad de llamadas](monitor-call-quality-qos.md) Análisis de llamadas muestra información detallada sobre dispositivos, redes y conectividad relacionada con llamadas concretas y reuniones de cada usuario. Análisis de llamadas está diseñado para ayudar a los administradores y agentes de soporte técnico a solucionar problemas de calidad de llamada con llamadas específicas, mientras que el Panel de calidad de llamadas está diseñado para ayudar a los administradores y los ingenieros de red a optimizar una red. El panel de calidad de llamada cambia el enfoque de usuarios específicos y, en su lugar, analiza la información global de toda la organización de Teams.

|Pregúntese lo siguiente:|Action |
|------------|-------|
| ¿Quién será responsable de la supervisión y solución de problemas de calidad de llamadas? | Consulte [Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md) para obtener información sobre los niveles de permisos necesarios para solucionar problemas de calidad de llamadas.|
|||

## <a name="next-steps"></a>Pasos siguientes

- [Impulsar la adopción](adopt-microsoft-teams-landing-page.md) de audioconferencias en su organización.
- [Implementar voz en la nube](cloud-voice-landing-page.md)
- Incluya aplicaciones destacadas, como Planner, en la implementación inicial de Teams. Agregue otras [aplicaciones de Teams](deploy-apps-microsoft-teams-landing-page.md) a medida que impulsa la adopción de Teams.
