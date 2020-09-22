---
title: 'Configurar las opciones de Audioconferencia: Microsoft Teams'
ms.reviewer: ''
description: Use estos recursos de implementación para ayudarle a implementar la audioconferencia como parte de la carga de trabajo de reuniones en Microsoft Teams.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom: seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90801c09a9dda27923fba49a3e8cbc2ef4f65e4e
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177350"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a>Más información sobre cómo implementar Audioconferencia en Microsoft Teams

La audioconferencia es la posibilidad de unirse a una reunión de Teams desde un teléfono normal y llamar desde una reunión a un número de teléfono. Asegúrese de revisar [Implementación reuniones](deploy-meetings-microsoft-teams-landing-page.md) como parte de la implementación de las audioconferencias en su organización.

## <a name="audio-conferencing-deployment-decisions"></a>Decisiones sobre la implementación de audioconferencias

Este artículo le ayudará a decidir si cambiar alguna opción de la configuración predeterminada de audioconferencias, en función del perfil y los requisitos empresariales de su organización, después le guiará con cada cambio. Hemos dividido las opciones en dos grupos, comenzando por el conjunto principal de [cambios que es más probable que realice](#core-deployment-decisions). El segundo grupo incluye las [opciones adicionales](#additional-deployment-decisions) que puede que quiera configurar, según las necesidades de su organización.

Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones. Los asistentes que se conectan por teléfono a la reunión no necesitan tener asignada ninguna licencia ni otra configuración. Llamar a reuniones resulta muy útil para usuarios que están de viaje y no puede asistir a una reunión a través del cliente de Skype Empresarial o la aplicación de Teams instalada en su portátil o su dispositivo móvil. 


## <a name="audio-conferencing-prerequisites"></a>Requisitos previos para las audioconferencias 

Antes de que pueda implementar audioconferencias para Teams, tenga en cuenta lo siguiente:

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Está disponible la audioconferencia para mi país o región?|Para averiguar si la audioconferencia está disponible en su país o región, vea [Disponibilidad de país y región para las audioconferencias y los planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).|
|¿Tienen los usuarios la licencia adecuada para las audioconferencias de Teams?|Las licencias de audioconferencia están disponibles como parte de la suscripción de Microsoft 365 y Office 365 E5, o como servicio complementario para los planes de suscripción de Microsoft 365 Empresa Estándar, E1 o E3. <ul><li>Para obtener y asignar licencias, consulte [Probar o comprar Audioconferencias en Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365) y [Asignar o quitar licencias para Aplicaciones de Microsoft 365 de negocios](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</li><li> Para obtener más información, lea las [Licencias de complementos de Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing). </li><li>Para ver las características de la nube que se incluyen en cada plan, vea los artículos [Opciones de licencia basadas en su plan](teams-add-on-licensing/office-365-business-premium.md).</li></ul>|
|¿Necesito comprar créditos de comunicaciones para los usuarios a los que se asignan las licencias de audioconferencias?|Para obtener más información, lea [¿Qué son los Créditos de comunicaciones?](what-are-communications-credits.md) y consulte la sección [Créditos de comunicaciones](#communications-credits) a continuación.|
|||


## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Una vez que cumpla con los requisitos previos de las audioconferencias, realice las tareas siguientes para configurar las audioconferencias para los usuarios.


### <a name="teams-administrators"></a>Administradores de Teams

Teams ofrece un conjunto de roles de administrador personalizados que pueden usarse para administrar Teams en su organización. Los roles proporcionan distintas funciones a los administradores. 

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿A quién se asignará el rol de Administrador de comunicaciones de Teams?|Para obtener más información sobre los roles de administrador de Teams, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md).|
|¿A quién se asignará el rol de Ingeniero de soporte en comunicaciones de Teams?|Para asignar roles de administrador, vea [asignar roles de administrador y de no administrador a los usuarios con Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|¿A quién se asignará el rol de Especialista de soporte en comunicaciones de Teams?||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>Puentes de conferencia y números de teléfono

Los puentes de conferencia permiten a los usuarios acceder a las reuniones por teléfono. Puede usar la configuración predeterminada para un puente de conferencias o cambiar los números de teléfono (gratuitos y de pago) y otras opciones, como el PIN o los idiomas que se usan.

Vea [Audioconferencias](audio-conferencing-in-office-365.md) para obtener más información.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Necesito agregar nuevos números de puente de conferencias?| Para agregar nuevos números, vea [Obtener números de teléfono del servicio](/microsoftteams/getting-service-phone-numbers).|
|¿Necesito modificar la configuración del puente?|Para modificar la configuración del puente, vea [Cambiar la configuración de un puente de audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).|
|¿Necesito hacer portabilidad de los números para usarlos con audioconferencia?|Para obtener información sobre la portabilidad de números de teléfono, lea [Transferir números de teléfono a Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).|
|||


### <a name="default-and-alternate-languages"></a>Idioma predeterminados y alternativos

Las audioconferencias de Teams le permiten configurar idiomas predeterminados y alternativos para un puente de conferencias.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Qué idiomas debo elegir para los saludos del operador automático? | Para elegir los idiomas, vea [Establecer los idiomas del operador automático para audioconferencias](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="conferencing-bridge-settings"></a>Configuración de puente de conferencias 

Después de configurar el puente de conferencias, incluyendo los idiomas predeterminados y alternativos, es necesario comprobar que las opciones de la configuración predeterminada, como las notificaciones de entrada y salida o la longitud del PIN, son las que desea usar. Si no es así, puede cambiarlas. 

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Los asistentes escucharán una notificación cuando un usuario se una o salga de una reunión? | Para cambiar esta configuración, vea [Cambiar la configuración de un puente de audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).|
|¿Cuál es la longitud mínima del PIN que usa un organizador para iniciar la reunión?||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>Configuración de número de teléfono de acceso telefónico para los usuarios que dirigen reuniones

Después de crear el puente de audioconferencias, debe configurar los números de pago o gratuitos que usarán los usuarios que dirigen las reuniones.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Qué números de puente de conferencias voy a asignar a cada usuario que dirija reuniones? | Para asignar un número de teléfono de acceso telefónico a un usuario, vea [Paso 7: Asignar números de teléfono de acceso telefónico para los usuarios que dirigen reuniones](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings). |
|||

### <a name="communications-credits"></a>Créditos de comunicaciones

Para proporcionar números de teléfono gratuitos para puentes de conferencia y admitir las conferencias por aceptación de llamada de números de teléfono internacionales, tendrá que configurar Créditos de comunicaciones para su organización. Obtenga más información sobre los Créditos de comunicaciones en [¿Que son los Créditos de comunicaciones?](what-are-communications-credits.md)

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Son necesarios los Créditos de comunicaciones para la implementación de audioconferencias? |Para saber si necesita configurar Créditos de comunicaciones, consulte [Configurar Créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).|
|Si son necesarios, ¿cuántos debería comprar?|Para determinar la cantidad de Créditos de comunicaciones, vea [Cantidad de fondos recomendada](what-are-communications-credits.md#recommended-funding-amounts).|
|¿Me interesa configurar una cantidad de recarga automática?|Para configurar una cantidad de recarga automática, vea [Configurar Créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).|
|||



## <a name="additional-deployment-decisions"></a>Decisiones de implementación adicionales

Puede que le interese cambiar esta configuración en función de las necesidades y la configuración de su organización.

### <a name="outbound-calling-restriction-policies"></a>Directivas de restricción de llamadas salientes 

Como administrador, puede usar los controles de llamadas salientes para restringir el tipo de audioconferencias y llamadas RTC del usuario final que pueden realizar los usuarios de su organización.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Voy a limitar el tipo de llamadas salientes permitidas? | Para restringir las llamadas, consulte [Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario](outbound-calling-restriction-policies.md)|
|||


### <a name="dial-plans"></a>Planes de marcado

Un plan de marcado, una característica del Sistema telefónico de Microsoft 365 u Office 365, es un conjunto de reglas de normalización con las que los números de teléfono que se marcan se traducen a un formato alternativo (normalmente, el formato E.164) para poder autorizar la llamada y enrutarla.

Para obtener más información acerca de los planes de marcado, vea [¿Qué son los planes de marcado?](what-are-dial-plans.md).

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Mi organización necesita un plan de marcado personalizado?|Para obtener ayuda para determinar si necesita un plan de marcado personalizado, vea [Planificar planes de marcado del espacio empresarial](what-are-dial-plans.md#planning-for-tenant-dial-plans). |
|¿Qué usuarios necesitan un plan de marcado personalizado y qué plan de marcado del espacio empresarial se va a asignar a cada usuario?|Para agregar usuarios a un plan de marcado personalizado con PowerShell, vea [Crear y administrar planes de marcado](create-and-manage-dial-plans.md).|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Solucionar problemas de calidad de las reuniones y llamadas 

Teams ofrece dos formas para supervisar y solucionar problemas de calidad de llamadas: [Análisis de llamadas y Panel de calidad de llamadas](monitor-call-quality-qos.md) Análisis de llamadas muestra información detallada sobre dispositivos, redes y conectividad relacionada con llamadas concretas y reuniones de cada usuario. Análisis de llamadas está diseñado para ayudar a los administradores y agentes de soporte técnico a solucionar problemas de calidad de llamada con llamadas específicas, mientras que el Panel de calidad de llamadas está diseñado para ayudar a los administradores y los ingenieros de red a optimizar una red. El panel de calidad de llamada cambia el enfoque de usuarios específicos y, en su lugar, analiza la información global de toda la organización de Teams. 

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Quién será responsable de la supervisión y solución de problemas de calidad de llamadas? | Consulte [Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md) para obtener información sobre los niveles de permisos necesarios para solucionar problemas de calidad de llamadas.|
|||


## <a name="next-steps"></a>Pasos siguientes
- [Impulsar la adopción](adopt-microsoft-teams-landing-page.md) de audioconferencias en su organización.
- [Implementar voz en la nube](cloud-voice-landing-page.md)
- Incluya aplicaciones destacadas, como Planner, en la implementación inicial de Teams. Agregue otras [aplicaciones, bots y conectores](deploy-apps-microsoft-teams-landing-page.md) a medida que impulsa la adopción de Teams.
