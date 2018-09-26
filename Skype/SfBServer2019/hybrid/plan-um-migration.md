---
title: Planeación de Skype para migración Business Server y Exchange Server
author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skypeforbusiness-server-itpro
description: En este tema, se explica qué debe tener en cuenta cuando decida migrar su Skype existente para las implementaciones Business Server o Exchange Server a la versión más reciente o a Skype para profesionales Online o Exchange Online.
ms.openlocfilehash: 25d0e275110df57747679efec46a77571259a3d4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027259"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planeación de Skype para migración Business Server y Exchange Server

[!INCLUDE [disclaimer](../disclaimer.md)]

En este tema, se explica qué debe tener en cuenta cuando decida migrar su Skype existente para las implementaciones Business Server o Exchange Server a la versión más reciente o a Skype para profesionales Online o Exchange Online. ¿Qué se puede migrar y cuándo, depende en gran medida en lo que ya tiene configuradas en la organización. En la vista previa, nos centraremos en la compatibilidad con algunos escenarios específicos, con escenarios adicionales que se encuentre disponible en Disponibilidad General (GA).

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Cambios en Exchange 2019 y Skype las características de Business Server 2019

Con Exchange 2019 y Skype para Business Server 2019, estamos haciendo que algunos cambios a las características que se admiten.

### <a name="unified-messaging-support-in-exchange-2019"></a>Unified Messaging soporte en Exchange 2019

Mensajería unificada (UM) ha quedado obsoleto en Exchange 2019. Esto significa que Exchange 2019 ya no ofrece las siguientes características:

- Correo de voz
- Operador automático

Si ha implementado la función de mensajería unificada en Exchange 2013 o el servicio de mensajería unificada en Exchange 2016, y desea actualizar a Exchange 2019, debe migrar su correo de voz para el servicio de correo de voz de Microsoft en la nube en Office 365. Si va a migrar su correo de voz al correo de voz en la nube, eche un vistazo en la siguiente sección [Exchange 2013/Exchange 2016 y Skype para 2015 empresarial para Exchange 2019 y Skype para profesionales de 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) .
> [!IMPORTANT]
> Si los usuarios en sus servidores Exchange 2013 o Exchange 2016 tienen buzones habilitados para mensajería unificada, no se muevan a Exchange 2019 antes de actualizar su Skype para servidores empresariales a Skype para Business Server 2019 y mover los usuarios a ellos para evitar una interrupción del servicio de mensajería de voz.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Compatibilidad de PBX en Exchange 2019 y Skype para Business Server 2019

Correo de voz en la nube no proporciona funcionalidad de centrales de conmutación (PBX) de mensajería de voz. Si está usando la mensajería unificada de Exchange Server para sistemas PBX y desea actualizar a Exchange Server 2019, necesitará adoptar una de las tres opciones que aparecen en la entrada de blog [nueva fecha de suspensión de la compatibilidad con controladores de borde de sesión en Exchange Mensajería unificada Online](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) en el [blog del equipo de Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Soporte Online mensajería unificada de Exchange en Skype para Business Server 2019

Con Skype para Business Server 2019, nos estamos mover Online mensajería unificada de Exchange al correo de voz en la nube. Cuando un usuario se mueve a un Skype para servidor empresarial 2019, aquí automáticamente comiencen a usar en la nube de correo de voz cuando se configura para el correo de voz hospedado. Si actualmente usa Online mensajería unificada de Exchange, no es necesario hacer nada que no sea mover un usuario a Skype para Business Server 2019 empezar a usar el correo de voz en la nube. Sin embargo, hay algunos cambios en las funciones que necesita tener en cuenta:

- Para la vista previa, organizativa Auto Attendant (la sustitución de operador automático de UM Exchange Online) no está disponible. Operador automático de organizativa estará disponible en Georgia.
- Configuración de correo de voz de usuario en Outlook en el Web no se aplica al correo de voz en la nube.

## <a name="on-premises-um-migration-scenarios"></a>Escenarios de migración de mensajería unificada local

En la vista previa, estamos a cargo los siguientes escenarios que permiten migrar los usuarios a Exchange 2019 y al correo de voz en la nube. Fecha de disponibilidad general se podrán admitir escenarios adicionales que le permiten migrar desde versiones adicionales de Exchange y Skype para Business server. Proporcionaremos también características adicionales, como operador automático de organización.

- Exchange 2013/Exchange 2016 y Skype para Business Server 2015 para Exchange 2019 y Skype para Business Server 2019
- Skype para Business Server 2015 para Skype para Business Server 2019 con Exchange 2013/Exchange 2016

Los siguientes escenarios requieren que no hay configuraciones de PBX o SBC existen como parte de su implementación actual y se suponen que ha configurado en sus servidores de Exchange local de mensajería unificada. Cada una de estas soluciones también se da por supuesto que se haya decidido configurar una implementación híbrida entre su Skype local para servidores empresariales y Office 365. Para obtener más información acerca de Skype para las implementaciones híbridas de negocio, vea [Skype para soluciones híbridas de negocio](hybrid-solutions.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 y Skype para 2015 empresarial para Exchange 2019 y Skype para 2019 empresarial

En este escenario, va a migrar su existente de Exchange 2013, Exchange 2016 y Skype para servidores de negocio 2015 2019 de Exchange y Skype para profesionales de 2019.

Como se ha mencionado anteriormente en este tema, 2019 de Exchange ya no se incluye el servicio de mensajería unificada. Esto significa, para todos los buzones que desea mover a 2019 de Exchange, tiene que usar el correo de voz en la nube para reemplazar la funcionalidad que le ha proporcionado por el servicio de mensajería unificada. Cuando configura Skype para Business Server 2019 y una implementación híbrida entre él y Office 365, correo de voz en la nube reemplaza estos servicios de correo de voz de mensajería unificada de Exchange.

El orden en que se desplaza a los usuarios a Exchange 2019 y Skype para Business Server 2019 es esencial para garantizar que la funcionalidad de correo de voz sigue estando disponible para todos los usuarios. Donde se procesa el correo de voz también se determina por la que se encuentran el intercambio y Skype para buzones de profesionales y los usuarios. Eche un vistazo en la siguiente tabla para ver qué combinaciones de Exchange y Skype para Business Server son compatibles y donde se procesa el correo de voz.

| Buzón de correo en:            | Usuario que se encuentra en Skype para Business Server 2015 | Usuario que se encuentra en Skype para Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Mensajería unificada de Exchange                             | Correo de voz en la nube                          |
| Exchange 2019                  | No se admite                           | Correo de voz en la nube                          |

Antes de comenzar la migración a Skype para Business Server 2019 y 2019 de Exchange, tenga en cuenta lo siguiente:

- Correo de voz en la nube no es compatible con organizativa operador automático de vista previa. Si desea que mueve al correo de voz en la nube para continuar para que estén disponibles a través de operador automático de los buzones de correo, debe mantener al menos un servidor de Exchange 2013 o 2016 de Exchange que ejecuta el rol de mensajería unificada o servicio disponible.
- Debe configurar al menos un Skype para 2019 Business server **y** mover usuarios a ese servidor antes de mover sus buzones de correo a Exchange 2019. Si no lo hace, se producirá los buzones de correo que no puede recibir mensajes de correo de voz.
- Llamadas enviadas al correo de voz se transferirá a correo de voz en la nube donde se registrará. Después de la llamada ha finalizado, el mensaje de correo de voz se van a enviar al buzón de correo del destinatario en el servidor de Exchange 2019 local. Debe tener este tráfico de voz en cuenta al determinar si la conectividad a Internet es suficiente para admitir el correo de voz en la nube.

Estos son los pasos de alto nivel para llevar a cabo esta migración.

1. Instalar y configurar Skype para Business Server 2019 en un nuevo servidor.
2. Actualizar la configuración de implementación híbrida para incluir el nuevo Skype para servidor empresarial 2019.
3. Instale y configure Exchange Server 2019 en un nuevo servidor.
4. Mover usuarios desde su Skype para servidor empresarial 2015 a su Skype para servidor empresarial 2019.
5. Establecer la directiva de correo de voz hospedado para cada usuario que se ha movido a Skype para Business Server 2019 usar el correo de voz en la nube.
6. Mover buzones desde el servidor Exchange 2013 o 2016 de Exchange en el servidor de Exchange 2019.
7. Dé de baja su Skype para los servidores de 2015 empresarial después de que el último usuario se ha movido fuera de ellos.
8. Dé de baja los servidores de Exchange 2013 o 2016 de Exchange después de que se ha movido el buzón última fuera de ellos.

    > [!IMPORTANT]
    > Si confía en un operador automático, mantener al menos un Exchange 2013 o 2016 de Exchange que se está ejecutando y está disponible.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype para Business Server 2015 para Skype para Business Server 2019 con Exchange 2013/Exchange 2016

En este escenario, desea migrar su Skype existente para servidor empresarial 2015 a Skype para Business Server 2019 pero permanecen en Exchange 2013 o 2016 de Exchange.

Cuando Skype para Business Server 2015 y Skype para Business Server 2019 coexisten en la misma organización, funcionan sin ningún problema con la mensajería unificada de Exchange y correo de voz en la nube para asegurarse de que correo de voz se entrega correctamente a los buzones de Exchange. Si la mensajería unificada de Exchange o correo de voz en la nube procesa el correo de voz depende de si el usuario se encuentra en Skype para Business Server 2015 o Skype para Business Server 2019:

- Si un usuario se encuentra en Skype para Business Server 2015, mensajería unificada de Exchange procesará el mensaje de correo de voz.
- Si un usuario se encuentra en Skype para Business Server 2019, correo de voz en la nube procesará el mensaje de correo de voz.

Independientemente de si la mensajería unificada de Exchange o correo de voz en la nube procesa el mensaje de correo de voz, el mensaje se almacenará en el buzón de Exchange del usuario.

Antes de comenzar la migración a Skype para Business Server 2019, tenga en cuenta lo siguiente:

- Correo de voz en la nube no es compatible con organizativa operador automático de vista previa. Si desea que mueve al correo de voz en la nube para continuar para que estén disponibles a través de operador automático de los buzones de correo, debe mantener al menos un servidor de Exchange 2013 o 2016 de Exchange que ejecuta el rol de mensajería unificada o servicio disponible.
- Llamadas enviadas al correo de voz se transferirá a correo de voz en la nube donde se registrará. Después de la llamada ha finalizado, el mensaje de correo de voz se van a enviar al buzón de correo del destinatario en el servidor de Exchange local. Debe tener este tráfico de voz en cuenta al determinar si la conectividad a Internet es suficiente para admitir el correo de voz en la nube.

Estos son los pasos de alto nivel para llevar a cabo esta migración.

1. Instalar y configurar Skype para Business Server 2019 en un nuevo servidor.
2. Actualizar la configuración de implementación híbrida para incluir el nuevo Skype para servidor empresarial 2019.
3. Mover usuarios desde su Skype para servidor empresarial 2015 a su Skype para servidor empresarial 2019.
4. Establecer la directiva de correo de voz hospedado para cada usuario que se ha movido a Skype para Business Server 2019 usar el correo de voz en la nube.
5. Dé de baja su Skype para los servidores de 2015 empresarial después de que el último usuario se ha movido fuera de ellos.

    > [!IMPORTANT]
    > Si confía en un operador automático, mantener al menos un Exchange 2013 o 2016 de Exchange que se está ejecutando y está disponible.