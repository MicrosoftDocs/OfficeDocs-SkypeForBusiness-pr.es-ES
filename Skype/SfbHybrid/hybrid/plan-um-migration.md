---
title: Planeación de la migración de Skype empresarial Server y Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: Este tema cubre lo que debe tener en cuenta cuando decida migrar las implementaciones existentes de Skype empresarial Server o Exchange Server a la versión más reciente o a Skype empresarial online o Exchange Online.
ms.openlocfilehash: 864a777c1fcb483df7f3779e9b105c1af551748e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237475"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planeación de la migración de Skype empresarial Server y Exchange Server

Este tema cubre lo que debe tener en cuenta cuando decida migrar las implementaciones existentes de Skype empresarial Server o Exchange Server a la versión más reciente o a Skype empresarial online o Exchange Online. Qué puede migrar y cuándo, depende en gran medida de lo que ya ha configurado en su organización. Algunas características, como el operador automático de la organización, no están disponibles en la disponibilidad general (GA), pero estarán disponibles más adelante en 2018.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Cambios de características en Exchange 2019 y Skype empresarial Server 2019

Con Exchange 2019 y Skype empresarial Server 2019, estamos realizando algunos cambios en las características que admitimos.

### <a name="unified-messaging-support-in-exchange-2019"></a>Compatibilidad de mensajería unificada en Exchange 2019

La mensajería unificada (UM) está en desuso en Exchange 2019. Esto significa que Exchange 2019 ya no ofrece las siguientes características:

- Correo de voz
- Operador automático

Si ha implementado el rol de mensajería unificada en Exchange 2013 o el servicio de mensajería unificada en Exchange 2016 y desea actualizar a Exchange 2019, deberá migrar el correo de voz al servicio de correo de voz en la nube de Microsoft en Office 365. Si desea migrar el correo de voz al correo de voz de la nube, eche un vistazo a la sección [2015 de Exchange 2013/exchange 2016 y Skype empresarial a exchange 2019 y Skype empresarial 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) a continuación.
> [!IMPORTANT]
> Si los usuarios de los servidores Exchange 2013 o Exchange 2016 tienen buzones habilitados para mensajería unificada, no los mueva a Exchange 2019 antes de actualizar los servidores de Skype empresarial a Skype empresarial Server 2019 y mover a los usuarios a ellos para evitar una interrupción de la mensajería de voz.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Compatibilidad con PBX en Exchange 2019 y Skype empresarial Server 2019

El correo de voz de nube no proporciona la funcionalidad de mensajería de voz a las centrales de conmutación (PBX). Si usa la mensajería unificada de Exchange Server para las PBX y desea actualizar a Exchange Server 2019, deberá adoptar una de las tres opciones enumeradas en la nueva fecha de entrada de blog [para la interrupción de la compatibilidad con los controladores de borde de sesión de Exchange. Mensajería unificada en línea](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) en el [blog del equipo de Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Soporte técnico de mensajería unificada de Exchange online en Skype empresarial Server 2019

Con Skype empresarial Server 2019, estamos cambiando de la mensajería unificada de Exchange Online al correo de voz de la nube. Cuando un usuario se mueve a un servidor de Skype empresarial 2019, se iniciará automáticamente con el correo de voz de nube cuando se configure para el correo de voz hospedado. Si actualmente usa la mensajería unificada de Exchange Online, no tiene que hacer nada más que mover un usuario a Skype empresarial Server 2019 para empezar a usar el correo de voz en la nube. Sin embargo, hay algunos cambios en la funcionalidad que debe tener en cuenta:

- El operador automático de la organización (el reemplazo del operador automático en la mensajería unificada de Exchange Online) no está disponible en disponibilidad general, pero estará disponible más adelante en 2018.
- La configuración del correo de voz de usuario en Outlook en la web no se aplica al correo de voz de nube.

## <a name="on-premises-um-migration-scenarios"></a>Escenarios de migración de mensajería unificada locales

Se admiten los siguientes escenarios que le permitirán migrar usuarios a Exchange 2019 y al correo de voz de la nube. Más adelante en 2018, se proporcionarán escenarios adicionales que le permitirán migrar desde versiones adicionales de Exchange y Skype empresarial Server. También proporcionaremos características adicionales, como operador automático de organización.

- Exchange 2013/Exchange 2016 y Skype empresarial Server 2015 a Exchange 2019 y Skype empresarial Server 2019
- Skype empresarial Server 2015 a Skype empresarial Server 2019 con Exchange 2013/Exchange 2016

Los siguientes escenarios requieren que no exista ninguna configuración de PBX o SBC como parte de la implementación actual y asuma que la mensajería unificada está configurada en los servidores de Exchange locales. Cada una de estas soluciones también presupone que ha decidido configurar una implementación híbrida entre sus servidores locales de Skype empresarial y Office 365. Para obtener más información acerca de las implementaciones híbridas de Skype empresarial, consulte [plan Hybrid Connectivity](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 y Skype empresarial 2015 a Exchange 2019 y Skype empresarial 2019

En este escenario, desea migrar los servidores Exchange 2013, Exchange 2016 y Skype empresarial 2015 existentes a Exchange 2019 y Skype empresarial 2019.

Como se mencionó anteriormente en este tema, Exchange 2019 ya no incluye el servicio de mensajería unificada. Esto significa que, para los buzones que desee mover a Exchange 2019, debe usar el correo de voz de nube para reemplazar la funcionalidad proporcionada por el servicio de mensajería unificada. Cuando configure Skype empresarial Server 2019 y una implementación híbrida entre ti y Office 365, el correo de voz de nube reemplaza estos servicios de correo de voz de mensajería unificada de Exchange.

El orden en que se mueven los usuarios a Exchange 2019 y Skype empresarial Server 2019 es fundamental para garantizar que la funcionalidad de correo de voz permanezca disponible para todos los usuarios. Dónde se procesa el correo de voz también se determina por el lugar donde se encuentran los buzones y usuarios de Exchange y Skype empresarial. Eche un vistazo a la tabla siguiente para ver qué combinaciones de Exchange y Skype empresarial Server son compatibles y dónde se procesa el correo de voz.

| Buzón ubicado en:            | Usuario ubicado en Skype empresarial Server 2015 | Usuario ubicado en Skype empresarial Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | UM de Exchange                             | UM de Exchange                              |
| Exchange 2019                  | No compatible                           | Correo de voz de nube                          |

Antes de iniciar la migración a Skype empresarial Server 2019 y Exchange 2019, tenga en cuenta lo siguiente:

- El correo de voz de nube no admite el operador automático de la organización en GA. Si desea que los buzones que se mueven al correo de voz de la nube sigan estando disponibles a través del operador automático, tendrá que mantener al menos un servidor de Exchange 2013 o Exchange 2016 que ejecute el rol o servicio de mensajería unificada disponible.
- Debe configurar al menos un servidor de Skype empresarial 2019 **y** mover los usuarios a ese servidor antes de mover sus buzones a Exchange 2019. Si no lo hace, los buzones no podrán recibir mensajes de correo de voz.
- Las llamadas enviadas al correo de voz se transferirán al correo de voz de la nube, donde se registrarán. Una vez finalizada la llamada, el mensaje de correo de voz se enviará al buzón de correo del destinatario en el servidor local de Exchange 2019. Debe tener en cuenta este tráfico de voz para determinar si la conectividad a Internet es suficiente para admitir el correo de voz de la nube.

Estos son los pasos de alto nivel para completar esta migración.

1. Instale y configure Skype empresarial Server 2019 en un nuevo servidor.
2. Actualice la configuración de implementación híbrida para incluir el nuevo servidor de Skype empresarial 2019.
3. Instale y Configure Exchange Server 2019 en un nuevo servidor.
4. Mueva los usuarios de su servidor de Skype empresarial 2015 a su servidor de 2019 de Skype empresarial.
5. Establezca la Directiva de correo de voz hospedado para cada usuario que se movió a Skype empresarial Server 2019 para usar el correo de voz de nube.
6. Mueva los buzones del servidor de Exchange 2013 o Exchange 2016 a su servidor de Exchange 2019.
7. Retire sus servidores de Skype empresarial 2015 una vez que el último usuario se haya desplazado.
8. Retire los servidores de Exchange 2013 o Exchange 2016 una vez que se haya movido el último buzón.

    > [!IMPORTANT]
    > Si confía en un operador automático, mantenga al menos un Exchange 2013 o Exchange 2016 en ejecución y disponible.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype empresarial Server 2015 a Skype empresarial Server 2019 con Exchange 2013/Exchange 2016

En este escenario, desea migrar su servidor de Skype empresarial 2015 existente a Skype empresarial Server 2019, pero sigue en Exchange 2013 o Exchange 2016.

Cuando Skype empresarial Server 2015 y Skype empresarial Server 2019 coexisten en la misma organización, trabajan de forma transparente con la mensajería unificada de Exchange y el correo de voz de la nube para asegurarse de que el correo de voz se entregue correctamente a los buzones de Exchange. Si la mensajería unificada de Exchange o el correo de voz de la nube procesa el correo de voz depende de si el usuario se encuentra en Skype empresarial Server 2015 o en Skype empresarial Server 2019:

- Si un usuario se encuentra en Skype empresarial Server 2015, la mensajería unificada de Exchange procesará el mensaje de correo de voz.
- Si un usuario se encuentra en Skype empresarial Server 2019, el correo de voz de la nube procesará el mensaje de correo de voz.

Independientemente de si la mensajería unificada de Exchange o el correo de voz de la nube procesan el mensaje de correo de voz, el mensaje se almacena en el buzón de Exchange del usuario.

Antes de iniciar la migración a Skype empresarial Server 2019, tenga en cuenta lo siguiente:

- El correo de voz de nube no admite el operador automático de la organización en GA. Si desea que los buzones que se mueven al correo de voz de la nube sigan estando disponibles a través del operador automático, tendrá que mantener al menos un servidor de Exchange 2013 o Exchange 2016 que ejecute el rol o servicio de mensajería unificada disponible.
- Las llamadas enviadas al correo de voz se transferirán al correo de voz de la nube, donde se registrarán. Una vez finalizada la llamada, el mensaje de correo de voz se enviará al buzón de correo del destinatario en el servidor de Exchange local. Debe tener en cuenta este tráfico de voz para determinar si la conectividad a Internet es suficiente para admitir el correo de voz de la nube.

Estos son los pasos de alto nivel para completar esta migración.

1. Instale y configure Skype empresarial Server 2019 en un nuevo servidor.
2. Actualice la configuración de implementación híbrida para incluir el nuevo servidor de Skype empresarial 2019.
3. Mueva los usuarios de su servidor de Skype empresarial 2015 a su servidor de 2019 de Skype empresarial.
4. Establezca la Directiva de correo de voz hospedado para cada usuario que se movió a Skype empresarial Server 2019 para usar el correo de voz de nube.
5. Retire sus servidores de Skype empresarial 2015 una vez que el último usuario se haya desplazado.

    > [!IMPORTANT]
    > Si confía en un operador automático, mantenga al menos un Exchange 2013 o Exchange 2016 en ejecución y disponible.
