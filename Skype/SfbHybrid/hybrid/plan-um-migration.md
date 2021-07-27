---
title: Plan para la migración de Skype Empresarial Server y Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: En este tema se trata lo que debe tener en cuenta al decidir migrar las implementaciones de Skype Empresarial Server o Exchange Server existentes a la versión más reciente o a Skype Empresarial Online o Exchange Online.
ms.openlocfilehash: 1972da1afbfb4d7b3236a5b6f03b904181cc1701
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509821"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Plan para la migración de Skype Empresarial Server y Exchange Server

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En este tema se trata lo que debe tener en cuenta al decidir migrar las implementaciones Skype Empresarial Server o Exchange Server a Exchange Online. Lo que puede migrar y cuándo dependerá en gran medida de lo que ya haya configurado en su organización.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Cambios de características en Exchange 2019 y Skype Empresarial Server 2019

Con Exchange 2019 y Skype Empresarial Server 2019, estamos realizando algunos cambios en las características compatibles.

### <a name="unified-messaging-support-in-exchange-2019"></a>Compatibilidad con mensajería unificada en Exchange 2019

La mensajería unificada (MU) ha quedado en desuso Exchange 2019. Esto significa que Exchange 2019 ya no ofrece las siguientes características:

- Correo de voz
- Operador automático

Si ha implementado el rol de mensajería unificada en Exchange 2013 o el servicio de mensajería unificada en Exchange 2016 y desea actualizar a Exchange 2019, deberá migrar el correo de voz al servicio de Correo de voz en la nube de Microsoft en Microsoft 365 o Office 365. Si desea migrar el correo de voz a Correo de voz en la nube, consulte las secciones [Exchange 2013/Exchange 2016 y Skype Empresarial 2015 Exchange 2019 y Skype Empresarial 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) a continuación.
> [!IMPORTANT]
> Si los usuarios de los servidores de Exchange 2013 o Exchange 2016 tienen buzones habilitados para mensajería unificada, no los mueva a Exchange 2019 antes de actualizar los servidores de Skype Empresarial Skype Empresarial Server Skype Empresarial Server 2019 y mover usuarios a ellos para evitar una interrupción de la mensajería de voz.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Compatibilidad con PBX en Exchange 2019 y Skype Empresarial Server 2019

Correo de voz en la nube no proporciona funcionalidad de mensajería de voz a exchanges de sucursal privados (PBX). Si usa la mensajería unificada de Exchange Server para PBX y desea actualizar Exchange Server Exchange Server 2019, deberá adoptar una de las tres [](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) opciones enumeradas en la entrada de blog Nueva fecha para la interrupción de la compatibilidad con controladores de borde de sesión en la mensajería unificada de Exchange Online en el blog del equipo de [Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online Compatibilidad con mensajería unificada en Skype Empresarial Server 2019

Con Skype Empresarial Server 2019, estamos pasando de la mensajería unificada Exchange Online a Correo de voz en la nube. Cuando un usuario se mueve a un servidor de Skype Empresarial 2019, empezará a usar automáticamente Correo de voz en la nube cuando esté configurado para correo de voz hospedado. Si actualmente usa la mensajería unificada Exchange Online, no necesita hacer otra cosa que mover un usuario a Skype Empresarial Server 2019 para empezar a usar Correo de voz en la nube. Sin embargo, hay algunos cambios en la funcionalidad que debe tener en cuenta:

- El Operador automático de la organización es el reemplazo del operador automático en Exchange Online mensajería unificada.
- La configuración del correo de voz del Outlook en la Web no se aplica a Correo de voz en la nube.

## <a name="on-premises-um-migration-scenarios"></a>Escenarios de migración de mensajería unificada local

Se admiten los siguientes escenarios que le permitirán migrar usuarios a Exchange 2019 y a Correo de voz en la nube.

- Exchange 2013/Exchange 2016 y Skype Empresarial Server 2015 a Exchange 2019 y Skype Empresarial Server 2019
- Skype Empresarial Server 2015 a Skype Empresarial Server 2019 con Exchange 2013/Exchange 2016

Los siguientes escenarios requieren que no existan configuraciones pbx o SBC como parte de la implementación actual y se supone que tiene la mensajería unificada configurada en los servidores Exchange locales. Cada una de estas soluciones también supone que ha decidido configurar una implementación híbrida entre los servidores Skype Empresarial locales y Microsoft 365 o Office 365. Para obtener más información Skype Empresarial implementaciones híbridas, vea [Plan hybrid connectivity](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 y Skype Empresarial 2015 a Exchange 2019 y Skype Empresarial 2019

En este escenario, desea migrar los servidores existentes de Exchange 2013, Exchange 2016 y Skype Empresarial 2015 Exchange 2019 y Skype Empresarial 2019.

Como se mencionó anteriormente en este tema, Exchange 2019 ya no incluye el servicio de mensajería unificada. Esto significa que, para los buzones que desea mover a Exchange 2019, debe usar Correo de voz en la nube para reemplazar la funcionalidad proporcionada por el servicio de mensajería unificada. Al configurar Skype Empresarial Server 2019 y una implementación híbrida entre él y Microsoft 365 o Office 365, Correo de voz en la nube reemplaza estos Exchange de correo de voz de mensajería unificada.

El orden en que mueves usuarios a Exchange 2019 y Skype Empresarial Server 2019 es fundamental para garantizar que la funcionalidad del correo de voz siga estando disponible para todos los usuarios. Donde se procesa el correo de voz también se determina por Exchange y Skype Empresarial buzones de correo y usuarios. Echa un vistazo a la tabla siguiente para ver qué combinaciones de Exchange y Skype Empresarial Server se admiten y dónde se procesa el correo de voz.

| Buzón ubicado en:            | Usuario ubicado en Skype Empresarial Server 2015 | Usuario ubicado en Skype Empresarial Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | UM de Exchange                             | UM de Exchange                              |
| Exchange 2019                  | No admitido                           | Correo de voz en la nube                          |

Antes de iniciar la migración a Skype Empresarial Server 2019 y Exchange 2019, tenga en cuenta lo siguiente:

- El correo de voz en la nube no admite Operador automático organización en GA. Si desea que los buzones movidos a Correo de voz en la nube sigan estando disponibles a través del operador automático, deberá mantener al menos un servidor de Exchange 2013 o Exchange 2016 que ejecute el rol o servicio de mensajería unificada disponible.
- Debe configurar al menos un servidor Skype Empresarial 2019 y mover usuarios a ese servidor antes de mover sus buzones a Exchange 2019.  Si no lo hace, esos buzones no podrán recibir mensajes de correo de voz.
- Las llamadas enviadas al correo de voz se transferirán Correo de voz en la nube donde se grabarán. Una vez finalizada la llamada, el mensaje de correo de voz se enviará al buzón del destinatario en el servidor Exchange 2019. Debe tener en cuenta este tráfico de voz al determinar si la conectividad a Internet es suficiente para admitir Correo de voz en la nube.

Estos son los pasos de alto nivel para completar esta migración.

1. Instale y configure Skype Empresarial Server 2019 en un nuevo servidor.
2. Actualice la configuración de implementación híbrida para incluir el nuevo Skype Empresarial 2019.
3. Instale y configure Exchange Server 2019 en un nuevo servidor.
4. Mueva usuarios del servidor Skype Empresarial 2015 al servidor Skype Empresarial 2019.
5. Establezca la directiva de correo de voz hospedado para cada usuario movido a Skype Empresarial Server 2019 para usar Correo de voz en la nube.
6. Mueva buzones de correo Exchange 2013 o Exchange 2016 al servidor Exchange 2019.
7. Retirar los servidores Skype Empresarial 2015 después de que el último usuario se haya movido de ellos.
8. Retirar los servidores Exchange 2013 o Exchange 2016 después de que se haya movido el último buzón de correo de ellos.

    > [!IMPORTANT]
    > Si confía en un operador automático, mantenga al menos un operador Exchange 2013 o Exchange 2016 en ejecución y disponible.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype Empresarial Server 2015 a Skype Empresarial Server 2019 con Exchange 2013/Exchange 2016

En este escenario, desea migrar el servidor de Skype Empresarial 2015 existente Skype Empresarial Server Skype Empresarial Server 2019, pero permanecer en Exchange 2013 o Exchange 2016.

Cuando Skype Empresarial Server 2015 y Skype Empresarial Server 2019 coexisten en la misma organización, trabajan sin problemas con la mensajería unificada y Correo de voz en la nube para garantizar que el correo de voz se entregue correctamente Exchange Exchange buzones de correo. Si Exchange um o Correo de voz en la nube el correo de voz depende de si el usuario se encuentra en Skype Empresarial Server 2015 o Skype Empresarial Server 2019:

- Si un usuario se encuentra en Skype Empresarial Server 2015, Exchange mensajería unificada procesará el mensaje de correo de voz.
- Si un usuario se encuentra en Skype Empresarial Server 2019, Correo de voz en la nube procesará el mensaje de correo de voz.

Independientemente de si Exchange um o Correo de voz en la nube procesa el mensaje de correo de voz, el mensaje se almacenará en el buzón de correo Exchange usuario.

Antes de iniciar la migración a Skype Empresarial Server 2019, tenga en cuenta lo siguiente:

- El correo de voz en la nube no admite Operador automático organización en GA. Si desea que los buzones movidos a Correo de voz en la nube sigan estando disponibles a través del operador automático, deberá mantener al menos un servidor de Exchange 2013 o Exchange 2016 que ejecute el rol o servicio de mensajería unificada disponible.
- Las llamadas enviadas al correo de voz se transferirán Correo de voz en la nube donde se grabarán. Una vez finalizada la llamada, el mensaje de correo de voz se enviará al buzón de correo del destinatario en el servidor Exchange local. Debe tener en cuenta este tráfico de voz al determinar si la conectividad a Internet es suficiente para admitir Correo de voz en la nube.

Estos son los pasos de alto nivel para completar esta migración.

1. Instale y configure Skype Empresarial Server 2019 en un nuevo servidor.
2. Actualice la configuración de implementación híbrida para incluir el nuevo Skype Empresarial 2019.
3. Mueva usuarios del servidor Skype Empresarial 2015 al servidor Skype Empresarial 2019.
4. Establezca la directiva de correo de voz hospedado para cada usuario movido a Skype Empresarial Server 2019 para usar Correo de voz en la nube.
5. Retirar los servidores Skype Empresarial 2015 después de que el último usuario se haya movido de ellos.

    > [!IMPORTANT]
    > Si confía en un operador automático, mantenga al menos un operador Exchange 2013 o Exchange 2016 en ejecución y disponible.
